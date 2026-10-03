# Tailwind CSS — State & Interaction UI_09

This is where Tailwind becomes interactive. You can change styles depending on what the user is doing: hovering, focusing, clicking, checking a checkbox, disabling a button, etc.

The basic pattern is:

```
state:utility
```

For example:

```
hover:bg-blue-700
```

means:

Apply bg-blue-700 when the user hovers over the element.

## 1. hover:

Used when the mouse is over an element.

```
<button className="
  bg-blue-600
  hover:bg-blue-700
  text-white
  px-5
  py-2
  rounded-lg
">
  Login
</button>
```

Normal:

```Blue 600```

Hover:

```Blue 700```

You can also change text:

```
<a className="text-gray-600 hover:text-blue-600">
  Home
</a>
```

## 2. focus:

Used when an element receives keyboard/mouse focus.

Very common with inputs.

```
<input
  className="
    border
    border-gray-300
    rounded-lg
    px-4
    py-2
    focus:border-blue-500
    focus:ring-2
    focus:ring-blue-200
    outline-none
  "
/>
```

When the input is selected:

Normal
```border-gray-300

       ↓ focus

Focused
border-blue-500
ring-blue-200
```

## 3. active:

active: applies while the element is being pressed/clicked.

```
<button className="
  bg-blue-600
  hover:bg-blue-700
  active:bg-blue-800
  text-white
  px-5
  py-2
  rounded-lg
">
  Click Me
</button>
```

States:

```
Normal → blue-600
Hover  → blue-700
Press  → blue-800
```

You can also create a small press effect:

```
<button className="
  transition
  active:scale-95
">
  Click
</button>
```

## 4. visited:

Used for links that the user has already visited.

```
<a
  href="/about"
  className="
    text-blue-600
    visited:text-purple-600
  "
>
  About
</a>
```

You will mostly see visited: with <a> elements.

## 5. disabled:

Used when an input or button is disabled.

```
<button
  disabled
  className="
    bg-blue-600
    text-white
    px-5
    py-2
    rounded-lg
    disabled:bg-gray-400
    disabled:cursor-not-allowed
    disabled:opacity-60
  "
>
  Login
</button>
```

You can make disabled elements visually obvious:

```
Normal
──────
Blue button

Disabled
────────
Gray + lower opacity + no-click cursor
```

A very useful pattern is:

```
disabled:opacity-50
disabled:cursor-not-allowed
```

## 6. checked:

Used with checkboxes and radio buttons.

```
<input
  type="checkbox"
  className="
    h-5
    w-5
    accent-blue-600
"
/>
```

For a more Tailwind-controlled style:

```
<input
  type="checkbox"
  className="
    appearance-none
    h-5
    w-5
    rounded
    border
    border-gray-300
    checked:bg-blue-600
    checked:border-blue-600
"
/>
```

The important class is:

checked:bg-blue-600

## 7. group-hover:

This is very important.

Sometimes you want to hover over a parent and change the child.

First add:

group

to the parent.

Then use:

group-hover:

on the child.

```
<div className="group p-6 border rounded-xl">

  <h2 className="
    text-gray-900
    group-hover:text-blue-600
  ">
    Product
  </h2>

  <p className="
    text-gray-600
    group-hover:text-gray-900
  ">
    Learn more about this product.
  </p>

</div>
```

When the user hovers anywhere over the card:

```
Card hover
    ↓
Heading changes
    ↓
Description changes
```

This is extremely useful for cards.

## 8. group-focus:

Same concept, but based on the parent being focused.

```
<div className="group">

  <button className="
    group-focus:text-blue-600
  ">
    Focus Me
  </button>

</div>
```

For practical UI, you'll often see group-focus-within: when an element inside the group receives focus.

Example:

```
<div className="group border rounded-lg p-4">

  <input
    className="
      outline-none
      group-focus-within:border-blue-500
    "
    placeholder="Enter your name"
  />

</div>
```

When the input gets focus, the parent can react.

## 9. peer

peer lets one element affect another sibling element.

Example:

```
<div>

  <input
    type="checkbox"
    className="peer"
  />

  <span className="
    peer-checked:text-blue-600
  ">
    Accept Terms
  </span>

</div>
```

Here:

```
checkbox
   ↓
  peer
   ↓
span reacts
```

The checkbox must come before the element that uses peer-*.

## 10. peer-*

You can use different states with a peer.

For example:

```
<input
  type="checkbox"
  className="peer"
/>

<span className="
  text-gray-500
  peer-checked:text-green-600
">
  Accepted
</span>
```

Other examples:

```
peer-hover:
peer-focus:
peer-checked:
peer-disabled:
peer-invalid:
```
**Very useful example — floating label**

```
<div className="relative">

  <input
    type="text"
    placeholder=" "
    className="
      peer
      w-full
      border
      rounded-lg
      px-4
      py-3
      outline-none
      focus:border-blue-600
    "
  />

  <label className="
    absolute
    left-4
    top-3
    bg-white
    px-1
    text-gray-500
    transition-all

    peer-focus:-top-2
    peer-focus:text-sm
    peer-focus:text-blue-600

    peer-placeholder-shown:top-3
    peer-placeholder-shown:text-base
  ">
    Email
  </label>

</div>
```

This is a common modern form pattern.

## 11. Focus-visible States

focus-visible: is especially useful for keyboard accessibility.

```
<button className="
  bg-blue-600
  text-white
  px-5
  py-2
  rounded-lg
  focus-visible:outline-none
  focus-visible:ring-4
  focus-visible:ring-blue-300
">
  Login
</button>
```

Difference:

```
focus:
    Applies whenever element receives focus.

focus-visible:
    Applies when the focus indication should be
    visibly shown, especially for keyboard navigation.

```

For accessible buttons, this is a useful pattern:

```
focus-visible:outline-none
focus-visible:ring-4
focus-visible:ring-blue-300
```

## 12. Button Interaction States

A professional button often has several states:

```
<button className="
  bg-blue-600
  hover:bg-blue-700
  active:bg-blue-800
  focus-visible:outline-none
  focus-visible:ring-4
  focus-visible:ring-blue-300
  disabled:bg-gray-400
  disabled:cursor-not-allowed
  disabled:opacity-50
  transition
">
  Login
</button>
```

Think:
```

                 ┌── hover
                 │
Normal ──────────┼── active
                 │
                 ├── focus
                 │
                 └── disabled
```

## 13. Form Interaction States

Forms can use several useful states:

```
focus
focus-visible
disabled
invalid
required
placeholder
```

Example:

```
<input
  type="email"
  required
  className="
    border
    border-gray-300
    rounded-lg
    px-4
    py-3

    focus:border-blue-500
    focus:ring-2
    focus:ring-blue-200

    invalid:border-red-500
    invalid:ring-red-200

    disabled:bg-gray-100
    disabled:cursor-not-allowed
  "
/>
```

For validation:

```
Valid
─────
Normal border

Invalid
───────
Red border

Focused
───────
Blue ring
```

## 14. Card Hover Effects

This is where group becomes very useful.

```
<div className="
  group
  rounded-2xl
  border
  border-gray-200
  p-6
  transition
  duration-300
  hover:-translate-y-1
  hover:shadow-xl
">

  <div className="
    h-12
    w-12
    rounded-lg
    bg-blue-100
    text-blue-600
    flex
    items-center
    justify-center
    transition
    group-hover:bg-blue-600
    group-hover:text-white
  ">
    AI
  </div>

  <h2 className="
    mt-5
    text-xl
    font-bold
    text-gray-900
    group-hover:text-blue-600
  ">
    AI Development
  </h2>

  <p className="
    mt-2
    text-gray-600
  ">
    Build intelligent applications.
  </p>

</div>
```

**The entire card reacts to hover.**


# Build: Interactive Login Form

**Now let's combine these concepts into a realistic React + Tailwind login form.**

This example includes:

```
hover:
focus:
active:
disabled:
checked:
group
group-hover:
peer
peer-checked:
focus-visible:
Error state
Loading/disabled state
Form validation
```

**LoginForm.jsx**

```
"use client";

import { useState } from "react";

export default function LoginForm() {

  const [email, setEmail] = useState("");
  const [password, setPassword] = useState("");

  const [remember, setRemember] = useState(false);

  const [error, setError] = useState("");

  const [loading, setLoading] = useState(false);


  const handleSubmit = (e) => {

    e.preventDefault();

    setError("");

    // Simple validation

    if (!email || !password) {
      setError("Please enter your email and password.");
      return;
    }

    if (!email.includes("@")) {
      setError("Please enter a valid email address.");
      return;
    }

    setLoading(true);

    // Simulate API request

    setTimeout(() => {
      setLoading(false);
      alert("Login successful!");
    }, 1500);
  };


  return (
    <div className="
      min-h-screen
      bg-slate-100
      flex
      items-center
      justify-center
      px-6
    ">

      <div className="
        w-full
        max-w-md
        rounded-2xl
        bg-white
        p-8
        shadow-xl
        border
        border-slate-200
      ">

        {/* Header */}

        <div className="text-center">

          <h1 className="
            text-3xl
            font-bold
            text-slate-900
          ">
            Welcome Back
          </h1>

          <p className="
            mt-2
            text-slate-500
          ">
            Login to your account
          </p>

        </div>


        {/* Error Message */}

        {error && (

          <div className="
            mt-6
            rounded-lg
            border
            border-red-200
            bg-red-50
            px-4
            py-3
            text-sm
            text-red-700
          ">
            {error}
          </div>

        )}


        {/* Form */}

        <form
          onSubmit={handleSubmit}
          className="mt-8 space-y-5"
        >

          {/* Email */}

          <div className="group">

            <label
              htmlFor="email"
              className="
                block
                mb-2
                text-sm
                font-medium
                text-slate-700
                group-focus-within:text-blue-600
              "
            >
              Email Address
            </label>

            <input
              id="email"
              type="email"
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              placeholder="you@example.com"
              disabled={loading}
              className="
                w-full
                rounded-lg
                border
                border-slate-300
                px-4
                py-3
                text-slate-900
                outline-none
                transition

                placeholder:text-slate-400

                hover:border-slate-400

                focus:border-blue-500
                focus:ring-4
                focus:ring-blue-100

                disabled:bg-slate-100
                disabled:text-slate-400
                disabled:cursor-not-allowed
              "
            />

          </div>


          {/* Password */}

          <div className="group">

            <label
              htmlFor="password"
              className="
                block
                mb-2
                text-sm
                font-medium
                text-slate-700
                group-focus-within:text-blue-600
              "
            >
              Password
            </label>

            <input
              id="password"
              type="password"
              value={password}
              onChange={(e) => setPassword(e.target.value)}
              placeholder="••••••••"
              disabled={loading}
              className="
                w-full
                rounded-lg
                border
                border-slate-300
                px-4
                py-3
                text-slate-900
                outline-none
                transition

                hover:border-slate-400

                focus:border-blue-500
                focus:ring-4
                focus:ring-blue-100

                disabled:bg-slate-100
                disabled:text-slate-400
                disabled:cursor-not-allowed
              "
            />

          </div>


          {/* Remember Me */}

          <div className="
            flex
            items-center
            justify-between
          ">

            <label className="
              flex
              items-center
              gap-3
              cursor-pointer
            ">

              <input
                type="checkbox"
                checked={remember}
                onChange={(e) => setRemember(e.target.checked)}
                disabled={loading}
                className="
                  peer
                  h-5
                  w-5
                  cursor-pointer
                  rounded
                  border-slate-300
                  accent-blue-600

                  disabled:cursor-not-allowed
                "
              />

              <span className="
                text-sm
                text-slate-600
                peer-checked:text-blue-600
              ">
                Remember me
              </span>

            </label>


            <a
              href="#"
              className="
                text-sm
                font-medium
                text-blue-600
                hover:text-blue-700
                visited:text-purple-600
              "
            >
              Forgot password?
            </a>

          </div>


          {/* Login Button */}

          <button
            type="submit"
            disabled={loading}
            className="
              group
              w-full
              rounded-lg
              bg-blue-600
              py-3
              font-semibold
              text-white
              transition

              hover:bg-blue-700

              active:bg-blue-800
              active:scale-[0.98]

              focus-visible:outline-none
              focus-visible:ring-4
              focus-visible:ring-blue-300

              disabled:bg-slate-400
              disabled:cursor-not-allowed
              disabled:opacity-60
            "
          >

            {loading ? (
              "Logging in..."
            ) : (
              "Login"
            )}

          </button>


          {/* Register */}

          <p className="
            text-center
            text-sm
            text-slate-500
          ">

            Don't have an account?

            <a
              href="#"
              className="
                ml-1
                font-medium
                text-blue-600
                hover:text-blue-700
              "
            >
              Create account
            </a>

          </p>

        </form>

      </div>

    </div>
  );
}
```

**page.jsx**

```
import LoginForm from "./components/LoginForm";

export default function Home() {
  return <LoginForm />;
}
🧠 How the States Work in This Project
Email input
Normal
border-slate-300

       ↓

Hover
hover:border-slate-400

       ↓

Focus
focus:border-blue-500
focus:ring-4
focus:ring-blue-100

       ↓

Disabled
disabled:bg-slate-100
disabled:cursor-not-allowed
Login button
Normal
bg-blue-600

       ↓

Hover
hover:bg-blue-700

       ↓

Press
active:bg-blue-800
active:scale-[0.98]

       ↓

Keyboard focus
focus-visible:ring-4

       ↓

Loading
disabled:bg-slate-400
disabled:opacity-60
Checkbox
Unchecked
text-slate-600

       ↓

Checked
peer-checked:text-blue-600
```

## State Cheat Sheet

|State|	Example|	Use|
|-----|----------|----------|
|hover:|	hover:bg-blue-700|	Mouse hover|
|focus:|    	focus:ring-2|	Element receives focus|
|active:|	active:scale-95|	While pressing|
|visited:|	visited:text-purple-600|	Visited links|
|disabled:|	disabled:opacity-50|	Disabled controls|
|checked:|	checked:bg-blue-600|	Checkbox/radio|
|group|	group|	Parent state controller|
|group-hover:|	group-hover:text-blue-600|	Child reacts to parent hover|
|group-focus:|	group-focus:text-blue-600|	Child reacts to parent focus|
|peer|	peer|	Sibling state controller|
|peer-checked:|	peer-checked:text-blue-600|	Sibling reacts to checked|
|focus-visible:|	focus-visible:ring-4|	Keyboard-visible focus|


## The 3 patterns to remember

*1. Element itself changes*

```
<button className="hover:bg-blue-700">```

*2. Parent controls child*
```
<div className="group">
  <span className="group-hover:text-blue-600">
```

**3. Sibling controls sibling**
```
<input className="peer" />

<span className="peer-checked:text-blue-600">```


**These three patterns cover a huge amount of interactive Tailwind UI development.**
