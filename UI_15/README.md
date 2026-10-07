# UI-15 — Tailwind with Next.js

## 1. App Router Styling

With modern Next.js, your application commonly looks like:

```
src/
└── app/
    ├── layout.js
    ├── page.js
    ├── globals.css
    │
    ├── dashboard/
    │   ├── layout.js
    │   └── page.js
    │
    ├── login/
    │   └── page.js
    │
    ├── loading.js
    ├── error.js
    └── not-found.js
```

Your global Tailwind CSS is normally imported in the root layout:

```
import "./globals.css";

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  );
}
```

Then individual pages can directly use Tailwind:

```
export default function Home() {
  return (
    <main className="min-h-screen bg-gray-50 p-6">
      <h1 className="text-4xl font-bold text-gray-900">
        Welcome
      </h1>
    </main>
  );
}
```

## 2. Server Component Styling

By default, files in the App Router are Server Components.

For example:

// app/page.js

```
export default function Home() {
  return (
    <main className="min-h-screen bg-gray-100 p-8">
      <h1 className="text-4xl font-bold">
        SaaS Dashboard
      </h1>
    </main>
  );
}
```

You don't need:

```"use client";```

just to use Tailwind classes.

Important concept

Tailwind styling works the same way:

```<div className="rounded-xl bg-white p-6 shadow">```

Whether the component is rendered on the server or client doesn't change how you write the Tailwind classes.

## 3. Client Component Styling

You need "use client" when you need client-side features such as:

```
useState
useEffect
click interactions
browser APIs
interactive menus
modals
dropdowns
```

Example:

```"use client";

import { useState } from "react";

export default function Counter() {
  const [count, setCount] = useState(0);

  return (
    <button
      onClick={() => setCount(count + 1)}
      className="rounded-lg bg-blue-600 px-4 py-2 text-white hover:bg-blue-700"
    >
      Count: {count}
    </button>
  );
}
```

The important distinction is:

```
Server Component
    ↓
Can use Tailwind
    ↓
No useState / onClick

Client Component
    ↓
Can use Tailwind
    ↓
Can use useState / onClick / browser APIs

Tailwind itself does not require "use client".
```

## 4. Layout Styling

A layout is useful for UI that should remain consistent across multiple pages.

For example:

// app/dashboard/layout.js

```
export default function DashboardLayout({ children }) {
  return (
    <div className="min-h-screen bg-gray-100">
      <div className="flex">
        <aside className="hidden w-64 border-r bg-white md:block">
          Sidebar
        </aside>

        <main className="flex-1">
          {children}
        </main>
      </div>
    </div>
  );
}
```

Now:

/dashboard
/dashboard/users
/dashboard/settings

can all use the same dashboard layout.

## 5. Page Styling

Your page focuses on the actual content.

// app/dashboard/page.js

```
export default function DashboardPage() {
  return (
    <section className="p-4 md:p-8">
      <h1 className="text-2xl font-bold text-gray-900 md:text-3xl">
        Dashboard
      </h1>

      <p className="mt-2 text-gray-600">
        Welcome back to your dashboard.
      </p>
    </section>
  );
}
```

Notice the responsive typography:

```text-2xl
md:text-3xl
```

## 6. Responsive Next.js Navbar

Create:

```
components/
└── Navbar.jsx
```

Because the mobile menu needs state:

```
"use client";

import { useState } from "react";

export default function Navbar() {
  const [open, setOpen] = useState(false);

  return (
    <nav className="border-b bg-white">
      <div className="mx-auto flex max-w-7xl items-center justify-between px-4 py-4">
        <h1 className="text-xl font-bold text-blue-600">
          SaaSApp
        </h1>

        <div className="hidden gap-6 md:flex">
          <a href="#" className="hover:text-blue-600">
            Home
          </a>

          <a href="#" className="hover:text-blue-600">
            Pricing
          </a>

          <a href="#" className="hover:text-blue-600">
            Contact
          </a>
        </div>

        <button
          onClick={() => setOpen(!open)}
          className="rounded-lg border px-3 py-2 md:hidden"
        >
          ☰
        </button>
      </div>

      {open && (
        <div className="border-t px-4 py-4 md:hidden">
          <div className="flex flex-col gap-4">
            <a href="#">Home</a>
            <a href="#">Pricing</a>
            <a href="#">Contact</a>
          </div>
        </div>
      )}
    </nav>
  );
}
```

Key responsive utilities:

```
hidden
md:flex
md:hidden
```

## 7. Dashboard Layout

A typical SaaS dashboard:

┌─────────────────────────────────────────────┐
│ Navbar                                      │
├──────────────┬──────────────────────────────┤
│              │                              │
│ Sidebar      │ Dashboard                    │
│              │                              │
│ Dashboard    │ ┌──────┐ ┌──────┐ ┌──────┐ │
│ Users        │ │Users │ │Sales │ │Orders│ │
│ Analytics    │ └──────┘ └──────┘ └──────┘ │
│ Settings     │                              │
│              │ Recent Activity              │
│              │                              │
└──────────────┴──────────────────────────────┘

Example:

export default function DashboardLayout({ children }) {
  return (
    <div className="min-h-screen bg-gray-100">
      <div className="flex">
        <aside className="hidden min-h-screen w-64 border-r bg-white p-5 lg:block">
          <h2 className="mb-6 text-xl font-bold">
            SaaSApp
          </h2>

          <nav className="space-y-2">
            <a className="block rounded-lg bg-gray-100 px-4 py-2">
              Dashboard
            </a>

            <a className="block rounded-lg px-4 py-2 hover:bg-gray-100">
              Users
            </a>

            <a className="block rounded-lg px-4 py-2 hover:bg-gray-100">
              Analytics
            </a>

            <a className="block rounded-lg px-4 py-2 hover:bg-gray-100">
              Settings
            </a>
          </nav>
        </aside>

        <main className="flex-1 p-4 md:p-8">
          {children}
        </main>
      </div>
    </div>
  );
}
8. Dashboard Cards

Use the reusable Card concept from your previous module:

<div className="grid grid-cols-1 gap-5 sm:grid-cols-2 xl:grid-cols-4">
  <div className="rounded-xl bg-white p-6 shadow-sm">
    <p className="text-sm text-gray-500">
      Total Users
    </p>

    <h2 className="mt-2 text-3xl font-bold">
      12,540
    </h2>
  </div>

  <div className="rounded-xl bg-white p-6 shadow-sm">
    <p className="text-sm text-gray-500">
      Revenue
    </p>

    <h2 className="mt-2 text-3xl font-bold">
      $24,500
    </h2>
  </div>
</div>

Responsive layout:

Mobile       1 column
Small        2 columns
Large        4 columns
9. Authentication UI

Create:

app/
└── login/
    └── page.js

Example:

export default function LoginPage() {
  return (
    <main className="flex min-h-screen items-center justify-center bg-gray-100 px-4">
      <div className="w-full max-w-md rounded-2xl bg-white p-6 shadow-lg sm:p-8">
        <h1 className="text-2xl font-bold">
          Welcome Back
        </h1>

        <p className="mt-2 text-gray-500">
          Login to your account.
        </p>

        <form className="mt-6 space-y-4">
          <input
            type="email"
            placeholder="Email"
            className="w-full rounded-lg border px-4 py-3 outline-none focus:border-blue-500"
          />

          <input
            type="password"
            placeholder="Password"
            className="w-full rounded-lg border px-4 py-3 outline-none focus:border-blue-500"
          />

          <button className="w-full rounded-lg bg-blue-600 py-3 font-medium text-white hover:bg-blue-700">
            Login
          </button>
        </form>
      </div>
    </main>
  );
}

This is authentication UI, not authentication logic.

Later, you can connect this UI with your NextAuth/Auth.js knowledge.

10. Loading UI

Next.js App Router provides a special:

loading.js

Example:

// app/dashboard/loading.js

export default function Loading() {
  return (
    <div className="flex min-h-[400px] items-center justify-center">
      <div className="h-10 w-10 animate-spin rounded-full border-4 border-gray-300 border-t-blue-600" />
    </div>
  );
}

When the dashboard is loading, Next.js can automatically show this UI.

11. Error UI

Create:

app/
└── error.js

Because error UI needs client-side behavior:

"use client";

export default function Error({ reset }) {
  return (
    <div className="flex min-h-screen items-center justify-center px-4">
      <div className="text-center">
        <h1 className="text-3xl font-bold text-red-600">
          Something went wrong
        </h1>

        <p className="mt-2 text-gray-600">
          We couldn't load this page.
        </p>

        <button
          onClick={() => reset()}
          className="mt-5 rounded-lg bg-blue-600 px-5 py-2 text-white"
        >
          Try Again
        </button>
      </div>
    </div>
  );
}
12. Not-found UI

Next.js supports:

not-found.js

Example:

export default function NotFound() {
  return (
    <main className="flex min-h-screen items-center justify-center px-4">
      <div className="text-center">
        <p className="text-7xl font-bold text-gray-900">
          404
        </p>

        <h1 className="mt-4 text-2xl font-bold">
          Page Not Found
        </h1>

        <p className="mt-2 text-gray-500">
          The page you're looking for doesn't exist.
        </p>

        <a
          href="/"
          className="mt-6 inline-block rounded-lg bg-blue-600 px-5 py-2 text-white"
        >
          Go Home
        </a>
      </div>
    </main>
  );
}
13. SEO-Friendly Responsive Layouts

Your layout should consider:

Semantic HTML

Instead of:

<div>
  <div>Navbar</div>
  <div>Content</div>
</div>

prefer:

<header>
  Navbar
</header>

<main>
  Content
</main>

<footer>
  Footer
</footer>
Metadata

In Next.js App Router:

export const metadata = {
  title: "SaaS Dashboard",
  description: "Modern SaaS dashboard built with Next.js",
};

Then:

export default function Home() {
  return (
    <main className="min-h-screen bg-gray-50">
      <h1 className="text-4xl font-bold">
        SaaS Dashboard
      </h1>
    </main>
  );
}

Good SEO + responsive UI means thinking about both:

SEO
├── title
├── description
├── semantic HTML
├── proper headings
└── meaningful content

Responsive
├── mobile
├── tablet
├── desktop
├── flexible widths
└── responsive spacing
14. Recommended Project Structure

For your complete project, I'd structure it like this:

src/
└── app/
    │
    ├── layout.js
    ├── page.js
    ├── globals.css
    │
    ├── login/
    │   └── page.js
    │
    ├── dashboard/
    │   ├── layout.js
    │   ├── page.js
    │   │
    │   ├── users/
    │   │   └── page.js
    │   │
    │   ├── analytics/
    │   │   └── page.js
    │   │
    │   └── settings/
    │       └── page.js
    │
    ├── loading.js
    ├── error.js
    └── not-found.js
    │
    └── components/
        ├── Navbar.jsx
        ├── Sidebar.jsx
        ├── Button.jsx
        ├── Card.jsx
        ├── Modal.jsx
        ├── Input.jsx
        ├── Badge.jsx
        ├── Alert.jsx
        └── Loading.jsx

One correction I'd make to that structure: if you're using the src/app App Router, keep shared components in:

src/
├── app/
└── components/

rather than putting components inside app.

So the cleaner final structure is:

src/
├── app/
│   ├── layout.js
│   ├── page.js
│   ├── globals.css
│   ├── login/
│   ├── dashboard/
│   ├── loading.js
│   ├── error.js
│   └── not-found.js
│
└── components/
    ├── Navbar.jsx
    ├── Sidebar.jsx
    ├── Button.jsx
    ├── Card.jsx
    ├── Modal.jsx
    ├── Input.jsx
    ├── Badge.jsx
    ├── Alert.jsx
    └── Loading.jsx
🚀 Final Build: Complete Next.js SaaS Dashboard

For your project, build something like:

                    SaaS APP
                       │
                 ┌─────┴─────┐
                 │   Navbar  │
                 └─────┬─────┘
                       │
        ┌──────────────┴──────────────┐
        │                             │
    Sidebar                       Dashboard
        │                             │
   Dashboard                    ┌─────┴─────┐
   Users                         │   Cards   │
   Analytics                     └─────┬─────┘
   Settings                           │
                                Recent Users
                                      │
                                  Activity
Pages
/                   → Landing page
/login              → Login
/dashboard          → Dashboard
/dashboard/users    → Users
/dashboard/analytics → Analytics
/dashboard/settings → Settings
Components
Navbar
Sidebar
Button
Card
Modal
Input
Badge
Alert
Loading
Next.js features
App Router
Server Components
Client Components
Layouts
loading.js
error.js
not-found.js
Metadata / SEO
Responsive design
Tailwind features
Flexbox
Grid
Responsive breakpoints
Typography
Colors
Borders
Radius
Shadows
Hover
Focus
Conditional classes
Dark mode later

The big progression from your previous module is:

Tailwind
   ↓
Tailwind + React
   ↓
Reusable Components
   ↓
Tailwind + Next.js
   ↓
App Router
   ↓
Layouts + Pages
   ↓
Server / Client Components
   ↓
Loading / Error / Not Found
   ↓
Responsive SaaS Dashboard

This is a very important module for you because it moves you from "I know Tailwind classes" to "I can actually build a professional Next.js application with Tailwind."
