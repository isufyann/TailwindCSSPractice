# UI-13 — Tailwind + React

## 1. Conditional Classes

Conditional classes mean applying Tailwind classes based on a condition.

```
function Button({ isActive }) {
  return (
    <button
      className={`px-4 py-2 rounded ${
        isActive
          ? "bg-blue-600 text-white"
          : "bg-gray-200 text-gray-800"
      }`}
    >
      Button
    </button>
  );
}
```

Usage:

```
<Button isActive={true} />
```

If isActive is true:

```bg-blue-600 text-white```

If false:

```bg-gray-200 text-gray-800```

Better approach with multiple conditions
function Button({ variant, disabled }) {
  return (
    <button
      className={`
        px-4 py-2 rounded-lg font-medium
        ${variant === "primary" ? "bg-blue-600 text-white" : ""}
        ${variant === "danger" ? "bg-red-600 text-white" : ""}
        ${disabled ? "opacity-50 cursor-not-allowed" : ""}
      `}
    >
      Submit
    </button>
  );
}
2. Dynamic Classes

Dynamic classes allow a component to receive styling through props.

function Badge({ color }) {
  return (
    <span className={`px-3 py-1 rounded-full ${color}`}>
      Badge
    </span>
  );
}

Usage:

<Badge color="bg-green-100 text-green-700" />
<Badge color="bg-red-100 text-red-700" />
Important Tailwind point

Avoid constructing Tailwind class names like:

<div className={`bg-${color}-500`}>

This can cause problems because Tailwind needs to detect class names during the build process.

Prefer complete class names:

const colors = {
  blue: "bg-blue-500",
  red: "bg-red-500",
  green: "bg-green-500",
};

<div className={colors[color]}>
3. Reusable Components

Instead of writing:

<button className="bg-blue-600 text-white px-4 py-2 rounded">
  Login
</button>

<button className="bg-blue-600 text-white px-4 py-2 rounded">
  Register
</button>

Create one component:

function Button({ children }) {
  return (
    <button className="bg-blue-600 text-white px-4 py-2 rounded-lg">
      {children}
    </button>
  );
}

Then:

<Button>Login</Button>
<Button>Register</Button>

This is the main idea:

Repeated UI
    ↓
React Component
    ↓
Props
    ↓
Reusable UI
4. Button Component

A good reusable Button should support variants and sizes.

function Button({
  children,
  variant = "primary",
  size = "md",
}) {
  const variants = {
    primary: "bg-blue-600 text-white hover:bg-blue-700",
    secondary: "bg-gray-200 text-gray-900 hover:bg-gray-300",
    danger: "bg-red-600 text-white hover:bg-red-700",
  };

  const sizes = {
    sm: "px-3 py-1.5 text-sm",
    md: "px-4 py-2",
    lg: "px-6 py-3 text-lg",
  };

  return (
    <button
      className={`
        rounded-lg font-medium
        ${variants[variant]}
        ${sizes[size]}
      `}
    >
      {children}
    </button>
  );
}

Usage:

<Button>Login</Button>

<Button variant="secondary">
  Cancel
</Button>

<Button variant="danger" size="lg">
  Delete
</Button>
5. Card Component
function Card({ title, children }) {
  return (
    <div className="rounded-xl border border-gray-200 bg-white p-6 shadow-sm">
      <h2 className="mb-3 text-xl font-bold">
        {title}
      </h2>

      <div className="text-gray-600">
        {children}
      </div>
    </div>
  );
}

Usage:

<Card title="Profile">
  <p>Welcome to your profile.</p>
</Card>
6. Modal Component

A modal is usually controlled by state.

import { useState } from "react";

function Modal() {
  const [open, setOpen] = useState(false);

  return (
    <>
      <button
        onClick={() => setOpen(true)}
        className="rounded-lg bg-blue-600 px-4 py-2 text-white"
      >
        Open Modal
      </button>

      {open && (
        <div className="fixed inset-0 flex items-center justify-center bg-black/50">
          <div className="w-full max-w-md rounded-xl bg-white p-6">
            <h2 className="mb-4 text-xl font-bold">
              Confirm Action
            </h2>

            <p className="mb-5 text-gray-600">
              Are you sure you want to continue?
            </p>

            <button
              onClick={() => setOpen(false)}
              className="rounded-lg bg-gray-900 px-4 py-2 text-white"
            >
              Close
            </button>
          </div>
        </div>
      )}
    </>
  );
}

Important Tailwind concepts here:

fixed
inset-0
flex
items-center
justify-center
bg-black/50
max-w-md
7. Navbar Component
function Navbar() {
  return (
    <nav className="border-b bg-white px-6 py-4">
      <div className="mx-auto flex max-w-7xl items-center justify-between">
        <h1 className="text-xl font-bold text-blue-600">
          MyApp
        </h1>

        <div className="flex gap-6">
          <a href="#" className="hover:text-blue-600">
            Home
          </a>

          <a href="#" className="hover:text-blue-600">
            About
          </a>

          <a href="#" className="hover:text-blue-600">
            Contact
          </a>
        </div>
      </div>
    </nav>
  );
}
8. Sidebar Component
function Sidebar() {
  return (
    <aside className="w-64 min-h-screen border-r bg-gray-50 p-4">
      <h2 className="mb-6 text-lg font-bold">
        Dashboard
      </h2>

      <nav className="space-y-2">
        <a
          href="#"
          className="block rounded-lg px-4 py-2 hover:bg-gray-200"
        >
          Home
        </a>

        <a
          href="#"
          className="block rounded-lg px-4 py-2 hover:bg-gray-200"
        >
          Users
        </a>

        <a
          href="#"
          className="block rounded-lg px-4 py-2 hover:bg-gray-200"
        >
          Settings
        </a>
      </nav>
    </aside>
  );
}
9. Form Components

Create reusable input components.

function Input({ label, type = "text", placeholder }) {
  return (
    <div className="mb-4">
      <label className="mb-2 block text-sm font-medium">
        {label}
      </label>

      <input
        type={type}
        placeholder={placeholder}
        className="
          w-full rounded-lg border border-gray-300
          px-4 py-2
          outline-none
          focus:border-blue-500
          focus:ring-2
          focus:ring-blue-200
        "
      />
    </div>
  );
}

Usage:

<Input
  label="Email"
  type="email"
  placeholder="Enter email"
/>

<Input
  label="Password"
  type="password"
  placeholder="Enter password"
/>
10. Badge Component
function Badge({ status }) {
  const styles = {
    success: "bg-green-100 text-green-700",
    warning: "bg-yellow-100 text-yellow-700",
    danger: "bg-red-100 text-red-700",
    info: "bg-blue-100 text-blue-700",
  };

  return (
    <span
      className={`rounded-full px-3 py-1 text-sm font-medium ${styles[status]}`}
    >
      {status}
    </span>
  );
}

Usage:

<Badge status="success" />
<Badge status="warning" />
<Badge status="danger" />
11. Alert Component
function Alert({ type = "info", children }) {
  const styles = {
    info: "bg-blue-100 text-blue-800",
    success: "bg-green-100 text-green-800",
    warning: "bg-yellow-100 text-yellow-800",
    error: "bg-red-100 text-red-800",
  };

  return (
    <div className={`rounded-lg p-4 ${styles[type]}`}>
      {children}
    </div>
  );
}

Usage:

<Alert type="success">
  Account created successfully.
</Alert>

<Alert type="error">
  Something went wrong.
</Alert>
12. Loading Component

Simple spinner:

function Loading() {
  return (
    <div className="flex items-center justify-center p-6">
      <div className="h-8 w-8 animate-spin rounded-full border-4 border-gray-300 border-t-blue-600" />
    </div>
  );
}

The important Tailwind utility is:

animate-spin
13. Responsive Component Architecture

Your components should work on:

Mobile
   ↓
Tablet
   ↓
Desktop

For example:

function Layout() {
  return (
    <div className="flex flex-col md:flex-row">
      <Sidebar />

      <main className="flex-1 p-4 md:p-8">
        Content
      </main>
    </div>
  );
}

Here:

flex-col       → mobile
md:flex-row    → desktop
p-4            → mobile
md:p-8         → desktop

Another example:

<div className="grid grid-cols-1 gap-6 sm:grid-cols-2 lg:grid-cols-3">
  <Card />
  <Card />
  <Card />
</div>

Result:

Mobile       1 column
Tablet       2 columns
Desktop      3 columns
14. Recommended Project Structure

For your React + Tailwind project, start organizing components like this:

src/
│
├── components/
│   ├── Button.jsx
│   ├── Card.jsx
│   ├── Modal.jsx
│   ├── Navbar.jsx
│   ├── Sidebar.jsx
│   ├── Input.jsx
│   ├── Badge.jsx
│   ├── Alert.jsx
│   └── Loading.jsx
│
├── pages/
│   └── Dashboard.jsx
│
├── App.jsx
└── main.jsx

Then:

import Button from "./components/Button";
import Card from "./components/Card";
import Badge from "./components/Badge";

This is the transition you're learning:

Tailwind CSS
      ↓
React JSX
      ↓
Props
      ↓
Conditional classes
      ↓
Reusable components
      ↓
Component architecture
      ↓
UI Library
Final Build: Reusable React UI Component Library

Build a small dashboard using all of the components:

App
│
├── Navbar
│
├── Layout
│   ├── Sidebar
│   │
│   └── Main
│       ├── Card
│       ├── Card
│       ├── Badge
│       ├── Alert
│       ├── Button
│       ├── Form
│       │   ├── Input
│       │   └── Button
│       │
│       └── Modal
│
└── Loading
Your final UI should demonstrate
✅ Conditional classes
✅ Dynamic classes
✅ Props
✅ Reusable components
✅ Button variants
✅ Card variants
✅ Modal open/close
✅ Responsive navbar
✅ Responsive sidebar
✅ Form inputs
✅ Badges
✅ Alerts
✅ Loading state
✅ Mobile/tablet/desktop layouts

Most important lesson: don't think of Tailwind as just "writing lots of classes." In React, you're learning to turn those classes into small, reusable UI building blocks.
