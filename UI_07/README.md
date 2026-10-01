# 7 Tailwind CSS — Positioning UI-07

This is an important Tailwind topic because positioning is used for **navbars, badges, dropdowns, modals, floating buttons, notifications, and dashboards.**


### Tailwind CSS Positioning — relative, absolute, fixed, sticky

These four utilities are extremely important when building navbars, badges, dropdowns, modals, floating buttons, dashboards, tooltips, and cards.

**The easiest way to understand them is:**

|Tailwind|	CSS|	Main purpose|
|--------|--------------------|
|relative|	position: relative|	Creates a positioning reference|
|absolute|	position: absolute|	Positions an element relative to a positioned parent|
|fixed|	position: fixed|	Fixes an element to the viewport|
|sticky|	position: sticky|	Sticks an element while scrolling|




The main idea is:

```
relative
   ↓
Creates a positioning reference
   ↓
absolute
   ↓
Positions an element inside that reference
```
--- 

## 1. relative

relative makes an element a positioning reference for absolutely positioned children.

```
<div className="relative">
  <div className="absolute top-0 right-0">
    Badge
  </div>
</div>
```

Think:

```Parent → relative
   │
   └── Child → absolute
```

**Important**

relative normally doesn't visibly move the element.
Its main purpose is to establish a reference point.

--- 

## 2. absolute

absolute removes an element from the normal document flow and positions it relative to the nearest relative ancestor.
```
<div className="relative h-40 bg-gray-200">

  <div className="absolute top-4 right-4 bg-red-500 text-white p-2">
    Badge
  </div>

</div>
```

The badge is positioned relative to the parent.

--- 

## 3. fixed

fixed positions an element relative to the browser viewport.

It stays in the same screen position while scrolling.
```
<button className="
  fixed
  bottom-6
  right-6
  bg-blue-600
  text-white
  p-4
  rounded-full
">
  🔔
</button>
```

Example:

Browser screen
```
┌────────────────────────────┐
│                            │
│         Website            │
│                            │
│                            │
│                    🔔      │ ← fixed
└────────────────────────────┘
```

Common uses:
* Floating buttons 
* Chat buttons 
* Notification buttons 
* Back-to-top buttons 

--- 

## 4. Sticky

sticky behaves like a normal element until it reaches a specified position, then it sticks while scrolling.

```
<nav className="
  sticky
  top-0
  bg-white
  shadow
  z-50
">
  Navbar
</nav>
```

Think:

```
Normal
   ↓
Scroll
   ↓
Reaches top
   ↓
Sticks to top
```

Very useful for:
*  Navigation 
* Dashboard sidebars 
* Table headers 
* Section headings \

--- 


## 5. inset-*

inset-* controls *top + right + bottom + left together.*


For example:
```
<div className="absolute inset-0">
  Overlay
</div>
```

This means:

```
top: 0
right: 0
bottom: 0
left: 0
```
So it fills its positioned parent.

Another example:
```
<div className="absolute inset-4">
  Content
</div>
```
Approximately:
```
top: 1rem
right: 1rem
bottom: 1rem
left: 1rem
```

--- 

## 6. top-*

Controls the top position.

```
<div className="absolute top-0">
<div className="absolute top-4">
<div className="absolute top-10">
```
Example:
```
<div className="relative h-40 bg-gray-200">

  <div className="absolute top-4 left-4">
    Top Left
  </div>

</div>
```
## 7. right-*

Controls the right position.

```
<div className="absolute right-0">
<div className="absolute right-4">
Example:
<div className="relative">

  <span className="
    absolute
    top-2
    right-2
    bg-red-500
    text-white
    rounded-full
    px-2
  ">
    3
  </span>

</div>
```

--- 


## 8. bottom-*

Controls the bottom position.

```
<div className="absolute bottom-4 right-4">
  Bottom Right
</div>
This is commonly used for floating buttons.
<button className="
  fixed
  bottom-6
  right-6
  rounded-full
  bg-blue-600
  p-4
  text-white
">
  +
</button>
```

--- 

## 9. left-*

Controls the left position.

```
<div className="absolute left-4 top-4">
  Top Left
</div>
```

You can combine positioning utilities:

```
absolute top-4 left-4
or:
absolute bottom-6 right-6
```

--- 

## 10. z-*

z-* controls the *stacking order* of elements.

For example:


```
<div className="relative z-10">
  Content
</div>

```

Higher z-index generally appears above lower ones.

```
z-50  → highest
z-40
z-30
z-20
z-10
z-0
```

Example:

```
<nav className="sticky top-0 z-50">
```

This helps ensure the navbar appears above normal page content.

--- 


## 11. Layered Components

You can combine:

```
relative
absolute
z-*
```

to create layers.

Example:

```
<div className="relative">

  <img
    src="/image.jpg"
    className="w-full"
  />

  <div className="
    absolute
    inset-0
    bg-black/40
  />

  <h2 className="
    absolute
    bottom-6
    left-6
    z-10
    text-3xl
    font-bold
    text-white
  ">
    Dashboard
  </h2>

</div>
```
Structure:

```
Parent → relative
    │
    ├── Image
    │
    ├── Overlay → absolute inset-0
    │
    └── Heading → absolute + z-10
```

--- 

## 12. Absolute Badges

This is a very common UI pattern.

```
<div className="relative">

  <div className="
    bg-white
    p-6
    rounded-xl
    shadow
  ">
    <h2>Pro Plan</h2>
  </div>

  <span className="
    absolute
    -top-3
    right-4
    bg-blue-600
    text-white
    px-3
    py-1
    rounded-full
    text-sm
  ">
    Popular
  </span>

</div>
```

Notice:

```
relative
   ↓
absolute
   ↓
-top-3
right-4
-top-3 moves the badge slightly outside the card.
```
--- 


## 13. Floating Buttons

A floating button usually uses fixed.

```
<button className="
  fixed
  bottom-6
  right-6
  z-50
  h-14
  w-14
  rounded-full
  bg-blue-600
  text-white
  text-xl
  shadow-lg
  hover:bg-blue-700
">
  +
</button>
```

Because it is:

```fixed bottom-6 right-6```

it remains near the bottom-right corner while scrolling.

--- 

## 14. Sticky Navigation

Example:

```
<nav className="
  sticky
  top-0
  z-50
  bg-white
  border-b
  border-gray-200
">
  <div className="
    max-w-7xl
    mx-auto
    px-6
    py-4
    flex
    justify-between
  ">
    <h1 className="font-bold text-xl">
      My Dashboard
    </h1>

    <button className="text-gray-600">
      Profile
    </button>
  </div>
</nav>
```

The important part is:
``` sticky top-0 z-50```

--- 

## 15. Modal Positioning

A modal normally uses:

```
fixed
inset-0
Example:
<div className="
  fixed
  inset-0
  bg-black/50
  flex
  items-center
  justify-center
  z-50
">

  <div className="
    bg-white
    rounded-xl
    p-8
    w-full
    max-w-md
  ">
    <h2 className="text-2xl font-bold">
      Confirm Action
    </h2>

    <p className="mt-2 text-gray-600">
      Are you sure you want to continue?
    </p>

    <button className="
      mt-6
      bg-blue-600
      text-white
      px-5
      py-2
      rounded-lg
    ">
      Confirm
    </button>

  </div>

</div>
```

**Why fixed inset-0?**

```
fixed
  ↓
Attach to browser viewport

inset-0
  ↓
Cover entire viewport

flex items-center justify-center
  ↓
Place modal in center
```

## Build: Dashboard

Now let's combine everything into a practical dashboard.


**Dashboard.jsx**

```
"use client";

import { useState } from "react";

export default function Dashboard() {

  const [showModal, setShowModal] = useState(false);

  return (
    <div className="min-h-screen bg-slate-100">

      {/* ================= NAVBAR ================= */}

      <nav className="
        sticky
        top-0
        z-40
        bg-white
        border-b
        border-slate-200
      ">
        <div className="
          max-w-7xl
          mx-auto
          px-6
          py-4
          flex
          items-center
          justify-between
        ">

          <h1 className="
            text-xl
            font-bold
            text-slate-900
          ">
            MyDashboard
          </h1>

          <div className="flex items-center gap-6">

            <a
              href="#"
              className="text-slate-600 hover:text-blue-600"
            >
              Dashboard
            </a>

            <a
              href="#"
              className="text-slate-600 hover:text-blue-600"
            >
              Reports
            </a>

            <button className="
              bg-blue-600
              text-white
              px-4
              py-2
              rounded-lg
              hover:bg-blue-700
            ">
              Profile
            </button>

          </div>

        </div>
      </nav>


      {/* ================= MAIN ================= */}

      <main className="
        max-w-7xl
        mx-auto
        px-6
        py-10
      ">

        {/* Header */}

        <div className="mb-8">

          <h2 className="
            text-3xl
            font-bold
            text-slate-900
          ">
            Dashboard
          </h2>

          <p className="
            mt-2
            text-slate-600
          ">
            Welcome back! Here is your overview.
          </p>

        </div>


        {/* ================= CARDS ================= */}

        <div className="
          grid
          md:grid-cols-3
          gap-6
        ">


          {/* Card 1 */}

          <div className="
            relative
            bg-white
            p-6
            rounded-xl
            shadow-sm
            border
            border-slate-200
          ">

            <span className="
              absolute
              top-4
              right-4
              bg-green-100
              text-green-700
              px-2
              py-1
              rounded-full
              text-xs
            ">
              +12%
            </span>

            <p className="text-slate-500">
              Revenue
            </p>

            <h3 className="
              mt-2
              text-3xl
              font-bold
              text-slate-900
            ">
              $24,500
            </h3>

          </div>


          {/* Card 2 */}

          <div className="
            relative
            bg-white
            p-6
            rounded-xl
            shadow-sm
            border
            border-slate-200
          ">

            <span className="
              absolute
              top-4
              right-4
              bg-blue-100
              text-blue-700
              px-2
              py-1
              rounded-full
              text-xs
            ">
              New
            </span>

            <p className="text-slate-500">
              Users
            </p>

            <h3 className="
              mt-2
              text-3xl
              font-bold
              text-slate-900
            ">
              12,540
            </h3>

          </div>


          {/* Card 3 */}

          <div className="
            bg-white
            p-6
            rounded-xl
            shadow-sm
            border
            border-slate-200
          ">

            <p className="text-slate-500">
              Orders
            </p>

            <h3 className="
              mt-2
              text-3xl
              font-bold
              text-slate-900
            ">
              1,240
            </h3>

          </div>

        </div>


        {/* ================= CONTENT ================= */}

        <div className="
          mt-8
          bg-white
          rounded-xl
          border
          border-slate-200
          p-8
          min-h-[600px]
        ">

          <h2 className="
            text-2xl
            font-bold
            text-slate-900
          ">
            Recent Activity
          </h2>

          <div className="
            mt-6
            space-y-4
          ">

            <div className="border-b pb-4">
              New user registered
            </div>

            <div className="border-b pb-4">
              New order received
            </div>

            <div className="border-b pb-4">
              Payment completed
            </div>

            <div className="border-b pb-4">
              Report generated
            </div>

          </div>

          {/* Open Modal */}

          <button
            onClick={() => setShowModal(true)}
            className="
              mt-8
              bg-blue-600
              text-white
              px-5
              py-3
              rounded-lg
              hover:bg-blue-700
            "
          >
            Open Modal
          </button>

        </div>

      </main>


      {/* ================= FLOATING BUTTON ================= */}

      <button className="
        fixed
        bottom-6
        right-6
        z-40
        w-14
        h-14
        rounded-full
        bg-blue-600
        text-white
        text-xl
        shadow-lg
        hover:bg-blue-700
      ">
        🔔
      </button>


      {/* ================= MODAL ================= */}

      {showModal && (

        <div className="
          fixed
          inset-0
          z-50
          bg-black/50
          flex
          items-center
          justify-center
          p-6
        ">

          <div className="
            bg-white
            w-full
            max-w-md
            rounded-2xl
            p-8
            shadow-2xl
          ">

            <h2 className="
              text-2xl
              font-bold
              text-slate-900
            ">
              Dashboard Modal
            </h2>

            <p className="
              mt-3
              text-slate-600
            ">
              This modal is positioned using
              fixed and inset-0.
            </p>

            <div className="
              mt-6
              flex
              justify-end
              gap-3
            ">

              <button
                onClick={() => setShowModal(false)}
                className="
                  px-4
                  py-2
                  rounded-lg
                  border
                  border-slate-300
                  text-slate-700
                "
              >
                Cancel
              </button>

              <button
                onClick={() => setShowModal(false)}
                className="
                  px-4
                  py-2
                  rounded-lg
                  bg-blue-600
                  text-white
                  hover:bg-blue-700
                "
              >
                Confirm
              </button>

            </div>

          </div>

        </div>

      )}

    </div>
  );
}

```

**Positioning Cheat Sheet**
|Tailwind|Purpose|
|-------------|-----------|
|relative|Create positioning reference|
|absolute|Position relative to ancestor|
|fixed| Position relative to viewport|
|inset-0|Top/right/bottom/left=0|
|top-4|Move from top|
|Right-4|Move from right|
|bottom-4|Move from bottom|
|left-4|Move from left|
|z-50|High stacking layer|
|-top-3|Negative top position|

**Remember this pattern**

```
<div className="relative">

  <div className="absolute top-0 right-0">
    Badge
  </div>

</div>
```

For viewport-level elements:

```
<div className="fixed bottom-6 right-6">
  Floating Button
</div>
For sticky elements:
<nav className="sticky top-0 z-50">
  Navbar
</nav>
For modals:
<div className="fixed inset-0 z-50">
  Modal
</div>
```

These four patterns will cover a *large part of real-world Tailwind positioning.^

