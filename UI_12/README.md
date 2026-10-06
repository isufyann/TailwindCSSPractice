# Important Data Reference

## UI_12 Tailwind CSS — Dark Mode

```
@import "tailwindcss";
@custom-variant dark (&:where(.dark, .dark *));
className="dark"
```
--- 

**Important**

Don't make every dark-mode text pure white.

Use levels:

```
Primary:
dark:text-white

Secondary:
dark:text-gray-300

Muted:
dark:text-gray-400

Very muted:
dark:text-gray-500
```

**This creates hierarchy.**

**Light/Dark Color Consistency**

This is one of the most important concepts.

Don't randomly select colors.

Create a consistent mapping.

--- 

For example:

|UI|  Light| Dark|
|----|------|-----|
|Page|	bg-gray-100|	dark:bg-slate-950|
|Navbar|	bg-white|	dark:bg-slate-900|
|Sidebar|	bg-white	dark:bg-slate-900|
|Card|	bg-white|	dark:bg-slate-900|
|Card border|	border-gray-200|	dark:border-slate-800|
|Primary text|	text-gray-900|	dark:text-white|
|Secondary text|	text-gray-600|	dark:text-gray-300|
|Muted text|	text-gray-500|	dark:text-gray-400|
|Input|	bg-white|	dark:bg-slate-800|
|Input border|	border-gray-300|	dark:border-gray-600|
|Hover|	bg-gray-100|	dark:bg-slate-800|


This gives the application a consistent visual system.

--- 


### How set inner button of light dark

```
const [dark, setDark] = useState(false);

  function toggleTheme() {
    const newTheme = !dark;
    setDark(newTheme);
    document.documentElement.classList.toggle(
      "dark",
      newTheme
    );
  }
```



# UI_12 Tailwind CSS — Dark Mode

Dark mode is very common in modern applications:

* Dashboards
* Admin panels
* SaaS applications
* Developer tools
* Documentation websites
* Chat applications
* Mobile/web apps 

The main Tailwind concept is:

```
Light mode
    ↓
normal classes

Dark mode

    ↓
dark:* classes
```

For example:

```<div className="bg-white text-gray-900 dark:bg-gray-900 dark:text-white">

Hello World
</div>
```

### Light mode:

```
Background → white
Text       → gray-900
Dark mode:
Background → gray-900
Text       → white
```

---

## 1. Understand Dark Mode

Tailwind's dark mode allows you to provide an alternative design when the application is using a dark theme.

The basic pattern is:

normal-class

dark:dark-mode-class

Example:

```
<h1 className="text-gray-900 dark:text-white">
  Dashboard
</h1>
```

The important part is:
```
text-gray-900
     ↓
Light mode

dark:text-white
     ↓
Dark mode
```

Another example:

```
<div className="bg-white dark:bg-gray-900">
  Content
</div>
```

---

## 2. How dark: Works

Suppose you write:
```
<div className="bg-white dark:bg-slate-900">
  Dashboard
</div>
```

Tailwind effectively gives you two states:

```
LIGHT
─────
bg-white


DARK
────
dark:bg-slate-900
```

You don't need JavaScript just to change the background.

Tailwind handles the CSS state.

---

3. Configure Dark Mode
Since your project uses Tailwind CSS v4, your setup is slightly different from older Tailwind tutorials.
Your globals.css already has:
@import "tailwindcss";
For a manual theme switcher, you can define the dark variant using a class:
@import "tailwindcss";

@custom-variant dark (&:where(.dark, .dark *));
Now Tailwind's:
dark:bg-slate-900
dark:text-white
will activate when a parent has:
class="dark"
For example:
<html class="dark">
Everything inside can respond to dark:.
________________________________________
4. Automatic vs Manual Dark Mode
There are two common approaches.
System preference
The user's operating system determines the theme.
Windows → Dark
Mac → Dark
Browser → Dark
Manual toggle
The user chooses:
☀ Light
🌙 Dark
For a real dashboard, manual switching is usually better because the user has control.
We'll build a manual switcher.
________________________________________
5. Using dark:
The syntax is extremely simple:
<div className="bg-white dark:bg-black">
Text:
<p className="text-gray-700 dark:text-gray-300">
Border:
<div className="border-gray-200 dark:border-gray-700">
Card:
<div className="bg-white dark:bg-slate-800">
Button:
<button className="
  bg-blue-600
  dark:bg-blue-500
">
________________________________________
6. Dark Backgrounds
Light background:
bg-white
Dark background:
dark:bg-slate-900
Example:
<div className="
  min-h-screen
  bg-gray-100
  dark:bg-slate-950
">
This is a very common application layout.
Good dark backgrounds
Instead of always using pure black:
bg-black
modern interfaces often use:
bg-slate-950
bg-slate-900
bg-gray-950
bg-zinc-950
For example:
<main className="bg-slate-100 dark:bg-slate-950">
________________________________________
7. Dark Text
Light mode:
text-gray-900
Dark mode:
dark:text-white
Example:
<h1 className="
  text-2xl
  font-bold
  text-gray-900
  dark:text-white
">
  Dashboard
</h1>
For secondary text:
<p className="
  text-gray-600
  dark:text-gray-400
">
  Welcome back.
</p>
Important
Don't make every dark-mode text pure white.
Use levels:
Primary:
dark:text-white

Secondary:
dark:text-gray-300

Muted:
dark:text-gray-400

Very muted:
dark:text-gray-500
This creates hierarchy.
________________________________________
8. Dark Borders
Light:
border-gray-200
Dark:
dark:border-gray-700
Example:
<div className="
  border
  border-gray-200
  dark:border-gray-700
">
Another example:
<input className="
  border
  border-gray-300
  dark:border-gray-600
">
________________________________________
9. Dark Cards
A card might be:
<div className="
  rounded-xl
  bg-white
  p-6
  shadow
  dark:bg-slate-800
">
But remember the border:
<div className="
  rounded-xl
  border
  border-gray-200
  bg-white
  p-6
  shadow-sm

  dark:border-slate-700
  dark:bg-slate-800
">
This creates:
LIGHT
┌─────────────────────┐
│ White card          │
│                     │
│ Content             │
└─────────────────────┘


DARK
┌─────────────────────┐
│ Dark card           │
│                     │
│ Content             │
└─────────────────────┘
________________________________________
10. Dark Forms
Forms require more than changing the page background.
Input:
<input
  className="
    w-full
    rounded-lg
    border
    border-gray-300
    bg-white
    px-4
    py-3
    text-gray-900
    placeholder:text-gray-400

    focus:border-blue-500
    focus:ring-2
    focus:ring-blue-100

    dark:border-gray-600
    dark:bg-gray-800
    dark:text-white
    dark:placeholder:text-gray-500

    dark:focus:border-blue-400
    dark:focus:ring-blue-900
  "
/>
Notice that we changed:
Background
Text
Placeholder
Border
Focus border
Focus ring
That's what creates a proper dark-mode form.
________________________________________
11. Dark Select
<select className="
  w-full
  rounded-lg
  border
  border-gray-300
  bg-white
  px-4
  py-3
  text-gray-900

  dark:border-gray-600
  dark:bg-gray-800
  dark:text-white
">
  <option>Select country</option>
  <option>Pakistan</option>
  <option>United Kingdom</option>
</select>
________________________________________
12. Dark Checkbox
<input
  type="checkbox"
  className="
    h-4
    w-4
    rounded
    border-gray-300
    text-blue-600

    dark:border-gray-600
"
/>
________________________________________
13. Dark Navigation
A dashboard navbar:
<nav className="
  border-b
  border-gray-200
  bg-white

  dark:border-gray-800
  dark:bg-slate-900
">
Navigation text:
<a className="
  text-gray-600
  hover:text-gray-900

  dark:text-gray-300
  dark:hover:text-white
">
  Dashboard
</a>
Navigation becomes:
LIGHT
Navbar → white
Text   → gray


DARK
Navbar → slate-900
Text   → gray-300
________________________________________
14. Dark Sidebar
<aside className="
  border-r
  border-gray-200
  bg-white

  dark:border-gray-800
  dark:bg-slate-900
">
Sidebar link:
<a className="
  flex
  items-center
  rounded-lg
  px-4
  py-3
  text-gray-600

  hover:bg-gray-100

  dark:text-gray-300
  dark:hover:bg-slate-800
">
  Dashboard
</a>
Active link:
<a className="
  bg-blue-50
  text-blue-600

  dark:bg-blue-950
  dark:text-blue-400
">
  Dashboard
</a>
________________________________________
15. Dark Dashboard
A dashboard normally has several layers:
Page
 ↓
Navbar
 ↓
Sidebar + Content
 ↓
Cards
 ↓
Tables
 ↓
Forms
Each layer should have its own dark-mode colors.
Example:
<main className="
  min-h-screen
  bg-gray-100
  dark:bg-slate-950
">
Card:
<div className="
  bg-white
  dark:bg-slate-900
">
Card border:
border-gray-200
dark:border-slate-800
Card heading:
text-gray-900
dark:text-white
Card description:
text-gray-600
dark:text-gray-400
________________________________________
16. Light/Dark Color Consistency
This is one of the most important concepts.
Don't randomly select colors.
Create a consistent mapping.
For example:
UI	Light	Dark
Page	bg-gray-100	dark:bg-slate-950
Navbar	bg-white	dark:bg-slate-900
Sidebar	bg-white	dark:bg-slate-900
Card	bg-white	dark:bg-slate-900
Card border	border-gray-200	dark:border-slate-800
Primary text	text-gray-900	dark:text-white
Secondary text	text-gray-600	dark:text-gray-300
Muted text	text-gray-500	dark:text-gray-400
Input	bg-white	dark:bg-slate-800
Input border	border-gray-300	dark:border-gray-600
Hover	bg-gray-100	dark:bg-slate-800
This gives the application a consistent visual system.
________________________________________
17. Don't Do This
Avoid:
<div className="
  bg-white
  dark:bg-black
  text-gray-900
  dark:text-white
  border-gray-200
  dark:border-white
">
The pure white border can be too strong.
Instead:
<div className="
  bg-white
  dark:bg-slate-900

  text-gray-900
  dark:text-white

  border-gray-200
  dark:border-slate-800
">
Dark mode usually works better with dark neutral shades, rather than everything becoming black/white.
________________________________________
18. Dark Mode Toggle
Now let's create a theme switch.
Because we're using React/Next.js, the component needs client-side state.
"use client";

import { useState } from "react";

export default function ThemeToggle() {
  const [dark, setDark] = useState(false);

  function toggleTheme() {
    setDark(!dark);
  }

  return (
    <button onClick={toggleTheme}>
      {dark ? "☀️ Light" : "🌙 Dark"}
    </button>
  );
}
But changing React state alone doesn't add the .dark class to the page.
We need:
document.documentElement.classList.toggle("dark");
So:
"use client";

import { useState } from "react";

export default function ThemeToggle() {
  const [dark, setDark] = useState(false);

  function toggleTheme() {
    const newTheme = !dark;

    setDark(newTheme);

    document.documentElement.classList.toggle(
      "dark",
      newTheme
    );
  }

  return (
    <button
      onClick={toggleTheme}
      className="
        rounded-lg
        border
        border-gray-300
        px-4
        py-2
        dark:border-gray-700
      "
    >
      {dark ? "☀️ Light" : "🌙 Dark"}
    </button>
  );
}
Now:
Click Dark
    ↓
<html class="dark">
    ↓
dark:* utilities activate
________________________________________
19. Build: Light/Dark Dashboard
Now let's combine everything.
The dashboard will contain:
┌─────────────────────────────────────────────┐
│ Logo             Search       🌙            │
├──────────────┬──────────────────────────────┤
│ Dashboard    │                              │
│ Analytics    │ Welcome Back                 │
│ Customers    │                              │
│ Settings     │ ┌──────┐ ┌──────┐ ┌──────┐ │
│              │ │Sales │ │Users │ │Orders│ │
│              │ └──────┘ └──────┘ └──────┘ │
│              │                              │
│              │ Recent Activity              │
│              │ ┌──────────────────────────┐ │
│              │ │ User   Action   Date     │ │
│              │ └──────────────────────────┘ │
└──────────────┴──────────────────────────────┘
globals.css
@import "tailwindcss";

@custom-variant dark (&:where(.dark, .dark *));
________________________________________
app/page.jsx
"use client";

import { useState } from "react";

export default function Dashboard() {
  const [dark, setDark] = useState(false);

  function toggleTheme() {
    const newTheme = !dark;

    setDark(newTheme);

    document.documentElement.classList.toggle(
      "dark",
      newTheme
    );
  }

  const stats = [
    {
      title: "Total Sales",
      value: "$24,560",
      change: "+12.5%",
    },
    {
      title: "Customers",
      value: "1,248",
      change: "+8.2%",
    },
    {
      title: "Orders",
      value: "856",
      change: "+5.4%",
    },
  ];

  return (
    <div className="
      min-h-screen
      bg-gray-100
      text-gray-900
      transition-colors
      duration-300

      dark:bg-slate-950
      dark:text-white
    ">

      {/* Navbar */}

      <header className="
        sticky
        top-0
        z-50
        border-b
        border-gray-200
        bg-white/90
        backdrop-blur

        dark:border-slate-800
        dark:bg-slate-900/90
      ">

        <div className="
          flex
          h-16
          items-center
          justify-between
          px-6
        ">

          <h1 className="
            text-xl
            font-bold
            text-gray-900
            dark:text-white
          ">
            MyDashboard
          </h1>


          <div className="flex items-center gap-4">

            <button
              onClick={toggleTheme}
              className="
                rounded-lg
                border
                border-gray-300
                bg-white
                px-4
                py-2
                text-sm
                font-medium
                text-gray-700
                transition

                hover:bg-gray-100

                dark:border-slate-700
                dark:bg-slate-800
                dark:text-gray-200
                dark:hover:bg-slate-700
              "
            >
              {dark ? "☀️ Light" : "🌙 Dark"}
            </button>

            <div className="
              flex
              h-9
              w-9
              items-center
              justify-center
              rounded-full
              bg-blue-600
              font-semibold
              text-white
            ">
              JD
            </div>

          </div>

        </div>

      </header>


      <div className="flex">

        {/* Sidebar */}

        <aside className="
          hidden
          min-h-[calc(100vh-4rem)]
          w-64
          border-r
          border-gray-200
          bg-white
          p-4

          dark:border-slate-800
          dark:bg-slate-900

          md:block
        ">

          <nav className="space-y-2">

            <a
              href="#"
              className="
                block
                rounded-lg
                bg-blue-50
                px-4
                py-3
                font-medium
                text-blue-600

                dark:bg-blue-950
                dark:text-blue-400
              "
            >
              Dashboard
            </a>

            <a
              href="#"
              className="
                block
                rounded-lg
                px-4
                py-3
                text-gray-600
                transition

                hover:bg-gray-100

                dark:text-gray-300
                dark:hover:bg-slate-800
              "
            >
              Analytics
            </a>

            <a
              href="#"
              className="
                block
                rounded-lg
                px-4
                py-3
                text-gray-600
                transition

                hover:bg-gray-100

                dark:text-gray-300
                dark:hover:bg-slate-800
              "
            >
              Customers
            </a>

            <a
              href="#"
              className="
                block
                rounded-lg
                px-4
                py-3
                text-gray-600
                transition

                hover:bg-gray-100

                dark:text-gray-300
                dark:hover:bg-slate-800
              "
            >
              Settings
            </a>

          </nav>

        </aside>


        {/* Main Content */}

        <main className="
          flex-1
          p-6
          md:p-8
        ">

          {/* Heading */}

          <div className="mb-8">

            <h2 className="
              text-3xl
              font-bold
              text-gray-900
              dark:text-white
            ">
              Welcome back, John
            </h2>

            <p className="
              mt-2
              text-gray-600
              dark:text-gray-400
            ">
              Here's what's happening with your business.
            </p>

          </div>


          {/* Stats */}

          <div className="
            grid
            gap-5
            sm:grid-cols-2
            lg:grid-cols-3
          ">

            {stats.map((stat) => (
              <div
                key={stat.title}
                className="
                  rounded-xl
                  border
                  border-gray-200
                  bg-white
                  p-6
                  shadow-sm
                  transition-all
                  duration-300

                  hover:-translate-y-1
                  hover:shadow-lg

                  dark:border-slate-800
                  dark:bg-slate-900
                  dark:hover:border-slate-700
                "
              >

                <p className="
                  text-sm
                  font-medium
                  text-gray-500
                  dark:text-gray-400
                ">
                  {stat.title}
                </p>

                <div className="
                  mt-3
                  flex
                  items-end
                  justify-between
                ">

                  <p className="
                    text-3xl
                    font-bold
                    text-gray-900
                    dark:text-white
                  ">
                    {stat.value}
                  </p>

                  <span className="
                    rounded-full
                    bg-green-100
                    px-2
                    py-1
                    text-xs
                    font-medium
                    text-green-700

                    dark:bg-green-950
                    dark:text-green-400
                  ">
                    {stat.change}
                  </span>

                </div>

              </div>
            ))}

          </div>


          {/* Recent Activity */}

          <div className="
            mt-8
            overflow-hidden
            rounded-xl
            border
            border-gray-200
            bg-white
            shadow-sm

            dark:border-slate-800
            dark:bg-slate-900
          ">

            <div className="
              border-b
              border-gray-200
              px-6
              py-5

              dark:border-slate-800
            ">

              <h3 className="
                font-semibold
                text-gray-900
                dark:text-white
              ">
                Recent Activity
              </h3>

            </div>


            <div className="overflow-x-auto">

              <table className="w-full text-left">

                <thead className="
                  bg-gray-50
                  dark:bg-slate-800
                ">

                  <tr>

                    <th className="
                      px-6
                      py-4
                      text-sm
                      font-semibold
                      text-gray-700

                      dark:text-gray-300
                    ">
                      User
                    </th>

                    <th className="
                      px-6
                      py-4
                      text-sm
                      font-semibold
                      text-gray-700

                      dark:text-gray-300
                    ">
                      Action
                    </th>

                    <th className="
                      px-6
                      py-4
                      text-sm
                      font-semibold
                      text-gray-700

                      dark:text-gray-300
                    ">
                      Date
                    </th>

                  </tr>

                </thead>


                <tbody className="
                  divide-y
                  divide-gray-200

                  dark:divide-slate-800
                ">

                  <tr className="
                    transition
                    hover:bg-gray-50
                    dark:hover:bg-slate-800/50
                  ">

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-900
                      dark:text-gray-200
                    ">
                      Sarah
                    </td>

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-600
                      dark:text-gray-400
                    ">
                      Created a new order
                    </td>

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-500
                      dark:text-gray-500
                    ">
                      Today
                    </td>

                  </tr>


                  <tr className="
                    transition
                    hover:bg-gray-50
                    dark:hover:bg-slate-800/50
                  ">

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-900
                      dark:text-gray-200
                    ">
                      Michael
                    </td>

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-600
                      dark:text-gray-400
                    ">
                      Updated profile
                    </td>

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-500
                      dark:text-gray-500
                    ">
                      Yesterday
                    </td>

                  </tr>


                  <tr className="
                    transition
                    hover:bg-gray-50
                    dark:hover:bg-slate-800/50
                  ">

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-900
                      dark:text-gray-200
                    ">
                      David
                    </td>

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-600
                      dark:text-gray-400
                    ">
                      Completed payment
                    </td>

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-500
                      dark:text-gray-500
                    ">
                      2 days ago
                    </td>

                  </tr>

                </tbody>

              </table>

            </div>

          </div>

        </main>

      </div>

    </div>
  );
}
________________________________________
20. How the Dashboard Theme Works
The important part is this:
document.documentElement.classList.toggle(
  "dark",
  newTheme
);
It changes the HTML element:
Light
<html>
Dark
<html class="dark">
Then Tailwind sees:
<div class="dark:bg-slate-950">
and activates the dark style.
The flow is:
User clicks 🌙
       ↓
toggleTheme()
       ↓
setDark(true)
       ↓
<html class="dark">
       ↓
Tailwind dark: variants activate
       ↓
Dashboard becomes dark
________________________________________

  
## 21. The Most Important Pattern

For almost every component, think in pairs:

```
bg-white dark:bg-slate-900
text-gray-900 dark:text-white
text-gray-600 dark:text-gray-400
border-gray-200 dark:border-slate-800
hover:bg-gray-100 dark:hover:bg-slate-800
bg-blue-50 dark:bg-blue-950
```

This is the basic language of Tailwind dark mode.
  
---

## 22. Dark Mode Checklist

When converting an existing page to dark mode, don't only change the main background.

Check:

```
☑ Page background
☑ Navbar
☑ Sidebar
☑ Cards
☑ Headings
☑ Paragraphs
☑ Borders
☑ Buttons
☑ Inputs
☑ Selects
☑ Textareas
☑ Placeholder
☑ Focus states
☑ Hover states
☑ Tables
☑ Badges
☑ Alerts
☑ Modals
☑ Dropdowns
```

A good dark-mode design is not simply "make everything black."

The goal is to preserve the same visual hierarchy:

```
LIGHT                       DARK

Page                        Page
gray-100        ↔           slate-950

Card                        Card
white           ↔           slate-900

Secondary text              Secondary text
gray-600        ↔           gray-400

Border                      Border
gray-200        ↔           slate-800

Primary text                Primary text
gray-900        ↔           white
Final mental model
```

```
                 DARK MODE
                     │
          ┌──────────┴──────────┐
          ↓                     ↓
       LIGHT                  DARK
          │                     │
     bg-white              dark:bg-slate-900
     text-gray-900         dark:text-white
     border-gray-200       dark:border-slate-800
     bg-gray-100           dark:bg-slate-950
          │                     │
          └──────────┬──────────┘
                     ↓
              SAME UI / SAME
              VISUAL HIERARCHY
```

**Once you understand this pattern, you can take almost any Tailwind component you've already built—navbar, form, pricing cards, documentation page, or dashboard—and add a professional dark theme without rebuilding the component from scratch.**
