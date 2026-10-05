# UI-11 Tailwind CSS — Forms & Validation States

Forms are one of the most important things to learn in Tailwind because almost every real application has:

```
Login forms
Registration forms
Search forms
Contact forms
Checkout forms
Profile forms
Admin forms
```

**We'll learn each utility and then build a complete registration form with validation-state UI.**

## 1. Input Styling

A basic input:

```
<input
  type="text"
  className="
    w-full
    rounded-lg
    border
    border-gray-300
    px-4
    py-3
    text-gray-900
    outline-none
"
/>
```

Important classes

```
w-full              → full width
rounded-lg          → rounded corners
border              → border
border-gray-300     → border color
px-4                → horizontal padding
py-3                → vertical padding
text-gray-900       → text color
outline-none        → removes browser outline
```

A more professional input:

```
<input
  type="text"
  placeholder="Enter your name"
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
    outline-none
    transition
    focus:border-blue-500
    focus:ring-2
    focus:ring-blue-100
  "
/>
```

## 2. Select Styling

A <select> can be styled similarly.

```
<select
  className="
    w-full
    rounded-lg
    border
    border-gray-300
    bg-white
    px-4
    py-3
    text-gray-700
    outline-none
    focus:border-blue-500
    focus:ring-2
    focus:ring-blue-100
  "
>
  <option value="">Select country</option>
  <option>Pakistan</option>
  <option>India</option>
  <option>United Kingdom</option>
</select>
```

Important

For a select:

bg-white

helps maintain a consistent background.

## 3. Checkbox Styling

Basic checkbox:

```
<input
  type="checkbox"
  className="h-4 w-4"
/>
```

A better version:

```
<input
  type="checkbox"
  className="
    h-4
    w-4
    rounded
    border-gray-300
    text-blue-600
    focus:ring-2
    focus:ring-blue-500
  "
/>
```

Example:

```
<div className="flex items-center gap-2">
  <input
    type="checkbox"
    id="terms"
    className="h-4 w-4 rounded border-gray-300 text-blue-600"
  />

  <label
    htmlFor="terms"
    className="text-sm text-gray-600"
  >
    I agree to the terms and conditions.
  </label>
</div>
```

## 4. Radio Styling

Radio buttons are useful when the user must choose one option.

```
<div className="flex items-center gap-2">
  <input
    type="radio"
    name="gender"
    value="male"
    className="h-4 w-4 text-blue-600"
  />

  <label>Male</label>
</div>
```

Multiple options:

```
<div className="space-y-3">

  <label className="flex items-center gap-2">
    <input
      type="radio"
      name="accountType"
      value="personal"
      className="h-4 w-4 text-blue-600"
    />
    Personal
  </label>

  <label className="flex items-center gap-2">
    <input
      type="radio"
      name="accountType"
      value="business"
      className="h-4 w-4 text-blue-600"
    />
    Business
  </label>

</div>
```

Important

Both radio buttons have:

```name="accountType"```

```Therefore only one can be selected.```

## 5. Textarea Styling

Textarea:

```
<textarea
  placeholder="Write something..."
  rows={5}
  className="
    w-full
    resize-none
    rounded-lg
    border
    border-gray-300
    px-4
    py-3
    outline-none
    focus:border-blue-500
    focus:ring-2
    focus:ring-blue-100
  "
/>
```

resize-none

Prevents the user from resizing the textarea.

You can also use:

```
resize-y → vertical resize
resize-x → horizontal resize
resize   → both directions
```

## 6. Placeholder Styling

Tailwind provides:

```placeholder:*```

Example:

```
<input
  placeholder="Enter your email"
  className="
    placeholder:text-gray-400
  "
/>
```

Other examples:

```
placeholder:text-gray-400
placeholder:text-sm
placeholder:italic
```

You can combine them:

```
<input
  placeholder="Enter your email"
  className="
    placeholder:text-sm
    placeholder:text-gray-400
  "
/>
```

## 7. Focus Styling

Focus means the user is currently interacting with the input.

Example:

```
<input
  className="
    border
    border-gray-300
    focus:border-blue-500
    focus:ring-2
    focus:ring-blue-100
    focus:outline-none
  "
/>
```

Normal:

border-gray-300

When clicked:

```
border-blue-500
ring-blue-100
Professional focus state
className="
  rounded-lg
  border
  border-gray-300
  px-4
  py-3
  outline-none
  transition
  focus:border-blue-500
  focus:ring-2
  focus:ring-blue-100
"
```

This gives the user clear visual feedback.

## 8. Error States

Suppose the email is invalid.

Normal input:

```
<input
  className="
    border
    border-gray-300
    rounded-lg
"
/>
```

Error input:

```
<input
  className="
    border
    border-red-500
    rounded-lg
    focus:border-red-500
    focus:ring-2
    focus:ring-red-100
"
/>
```

Then display an error message:

```
<p className="mt-1 text-sm text-red-600">
  Please enter a valid email address.
</p>
```

Complete error field

```
<div>
  <label className="mb-2 block text-sm font-medium">
    Email
  </label>

  <input
    type="email"
    className="
      w-full
      rounded-lg
      border
      border-red-500
      px-4
      py-3
      outline-none
      focus:ring-2
      focus:ring-red-100
    "
  />

  <p className="mt-1 text-sm text-red-600">
    Please enter a valid email address.
  </p>
</div>
```

## 9. Success States

You can also show that an input is valid.

```
<input
  className="
    w-full
    rounded-lg
    border
    border-green-500
    px-4
    py-3
    outline-none
    focus:ring-2
    focus:ring-green-100
"
/>
```

Success message:

```
<p className="mt-1 text-sm text-green-600">
  Email address is valid.
</p>
```

State comparison

```
Normal
border-gray-300

Focus
border-blue-500

Error
border-red-500

Success
border-green-500

Disabled
bg-gray-100
cursor-not-allowed
```

## 10. Disabled States

Disabled input:

```
<input
  disabled
  className="
    w-full
    rounded-lg
    border
    border-gray-300
    bg-gray-100
    px-4
    py-3
    text-gray-500
    disabled:cursor-not-allowed
    disabled:opacity-60
  "
/>
```

The disabled: variant allows you to style an element when it has the disabled attribute.

Button example:

```
<button
  disabled
  className="
    rounded-lg
    bg-blue-600
    px-6
    py-3
    text-white
    disabled:cursor-not-allowed
    disabled:opacity-50
  "
>
  Create Account
</button>
```

## 11. Form Layouts

Vertical form

Most common:

```
<form className="space-y-5">

  <div>
    <label>Name</label>
    <input className="w-full" />
  </div>

  <div>
    <label>Email</label>
    <input className="w-full" />
  </div>

  <div>
    <label>Password</label>
    <input className="w-full" />
  </div>

</form>
```

space-y-5 automatically adds vertical spacing between the children.

## 12. Two-Column Form

Use Grid:

```<form className="grid gap-5 md:grid-cols-2">```

```
  <div>
    <label>First Name</label>
    <input className="w-full" />
  </div>

  <div>
    <label>Last Name</label>
    <input className="w-full" />
  </div>

</form>
```

Mobile:

```
First Name
Last Name
```

Desktop:

```First Name       Last Name```

## 13. Full-Width Fields

**Some fields should occupy the entire row.**

Use:

```md:col-span-2```

Example:


```
<form className="grid gap-5 md:grid-cols-2">

  <input />

  <input />

  <textarea className="md:col-span-2" />

  <button className="md:col-span-2">
    Submit
  </button>

</form>
```

## 14. Responsive Forms

Tailwind follows a mobile-first approach.

Example:

```
<form className="
  grid
  grid-cols-1
  gap-5
  md:grid-cols-2
">
```

Meaning:

```
Mobile
↓
1 column

Desktop
↓
2 columns
```

Another example:

```
<div className="
  flex
  flex-col
  gap-4
  md:flex-row
">
```

Mobile:
```
[First Name]
[Last Name]
```

Desktop:

```[First Name] [Last Name]```


## 15. Registration Form — Complete Project

Now let's combine everything.

This example includes:

```
First name
Last name
Email
Password
Confirm password
Country
Account type
Bio
Terms checkbox
Error states
Success states
Disabled button
Responsive layout
Focus states
Placeholder styling
```


**app/page.jsx**


```
"use client";

import { useState } from "react";

export default function RegisterPage() {
  const [form, setForm] = useState({
    firstName: "",
    lastName: "",
    email: "",
    password: "",
    confirmPassword: "",
    country: "",
    accountType: "",
    bio: "",
    terms: false,
  });

  const [errors, setErrors] = useState({});

  function handleChange(e) {
    const { name, value, type, checked } = e.target;

    setForm({
      ...form,
      [name]: type === "checkbox" ? checked : value,
    });
  }

  function validateForm() {
    const newErrors = {};

    if (!form.firstName.trim()) {
      newErrors.firstName = "First name is required.";
    }

    if (!form.lastName.trim()) {
      newErrors.lastName = "Last name is required.";
    }

    if (!form.email.trim()) {
      newErrors.email = "Email is required.";
    } else if (!form.email.includes("@")) {
      newErrors.email = "Enter a valid email address.";
    }

    if (!form.password) {
      newErrors.password = "Password is required.";
    } else if (form.password.length < 8) {
      newErrors.password =
        "Password must contain at least 8 characters.";
    }

    if (form.password !== form.confirmPassword) {
      newErrors.confirmPassword =
        "Passwords do not match.";
    }

    if (!form.country) {
      newErrors.country = "Please select your country.";
    }

    if (!form.accountType) {
      newErrors.accountType =
        "Please select an account type.";
    }

    if (!form.terms) {
      newErrors.terms =
        "You must accept the terms and conditions.";
    }

    return newErrors;
  }

  function handleSubmit(e) {
    e.preventDefault();

    const validationErrors = validateForm();

    setErrors(validationErrors);

    if (Object.keys(validationErrors).length === 0) {
      alert("Registration successful!");
    }
  }

  const inputBase = `
    w-full
    rounded-lg
    border
    px-4
    py-3
    outline-none
    transition
    placeholder:text-gray-400
  `;

  function inputClass(field) {
    if (errors[field]) {
      return `${inputBase}
        border-red-500
        focus:border-red-500
        focus:ring-2
        focus:ring-red-100
      `;
    }

    if (form[field]) {
      return `${inputBase}
        border-green-500
        focus:border-green-500
        focus:ring-2
        focus:ring-green-100
      `;
    }

    return `${inputBase}
      border-gray-300
      focus:border-blue-500
      focus:ring-2
      focus:ring-blue-100
    `;
  }

  return (
    <main className="min-h-screen bg-gray-100 px-4 py-10">

      <div className="mx-auto max-w-3xl">

        <div className="mb-8 text-center">
          <h1 className="text-3xl font-bold text-gray-900">
            Create Your Account
          </h1>

          <p className="mt-2 text-gray-600">
            Register to get started.
          </p>
        </div>

        <form
          onSubmit={handleSubmit}
          className="
            rounded-2xl
            bg-white
            p-6
            shadow-lg
            md:p-8
          "
        >

          {/* Name */}

          <div className="grid gap-5 md:grid-cols-2">

            <div>
              <label
                htmlFor="firstName"
                className="mb-2 block text-sm font-medium text-gray-700"
              >
                First Name
              </label>

              <input
                id="firstName"
                name="firstName"
                value={form.firstName}
                onChange={handleChange}
                placeholder="John"
                className={inputClass("firstName")}
              />

              {errors.firstName && (
                <p className="mt-1 text-sm text-red-600">
                  {errors.firstName}
                </p>
              )}
            </div>


            <div>
              <label
                htmlFor="lastName"
                className="mb-2 block text-sm font-medium text-gray-700"
              >
                Last Name
              </label>

              <input
                id="lastName"
                name="lastName"
                value={form.lastName}
                onChange={handleChange}
                placeholder="Doe"
                className={inputClass("lastName")}
              />

              {errors.lastName && (
                <p className="mt-1 text-sm text-red-600">
                  {errors.lastName}
                </p>
              )}
            </div>

          </div>


          {/* Email */}

          <div className="mt-5">

            <label
              htmlFor="email"
              className="mb-2 block text-sm font-medium text-gray-700"
            >
              Email Address
            </label>

            <input
              id="email"
              name="email"
              type="email"
              value={form.email}
              onChange={handleChange}
              placeholder="john@example.com"
              className={inputClass("email")}
            />

            {errors.email && (
              <p className="mt-1 text-sm text-red-600">
                {errors.email}
              </p>
            )}

            {!errors.email && form.email && (
              <p className="mt-1 text-sm text-green-600">
                Email looks good.
              </p>
            )}

          </div>


          {/* Password */}

          <div className="mt-5">

            <label
              htmlFor="password"
              className="mb-2 block text-sm font-medium text-gray-700"
            >
              Password
            </label>

            <input
              id="password"
              name="password"
              type="password"
              value={form.password}
              onChange={handleChange}
              placeholder="Enter your password"
              className={inputClass("password")}
            />

            {errors.password && (
              <p className="mt-1 text-sm text-red-600">
                {errors.password}
              </p>
            )}

          </div>


          {/* Confirm Password */}

          <div className="mt-5">

            <label
              htmlFor="confirmPassword"
              className="mb-2 block text-sm font-medium text-gray-700"
            >
              Confirm Password
            </label>

            <input
              id="confirmPassword"
              name="confirmPassword"
              type="password"
              value={form.confirmPassword}
              onChange={handleChange}
              placeholder="Confirm your password"
              className={inputClass("confirmPassword")}
            />

            {errors.confirmPassword && (
              <p className="mt-1 text-sm text-red-600">
                {errors.confirmPassword}
              </p>
            )}

            {!errors.confirmPassword &&
              form.confirmPassword &&
              form.password === form.confirmPassword && (
                <p className="mt-1 text-sm text-green-600">
                  Passwords match.
                </p>
              )}

          </div>


          {/* Country */}

          <div className="mt-5">

            <label
              htmlFor="country"
              className="mb-2 block text-sm font-medium text-gray-700"
            >
              Country
            </label>

            <select
              id="country"
              name="country"
              value={form.country}
              onChange={handleChange}
              className={inputClass("country")}
            >
              <option value="">
                Select your country
              </option>

              <option value="Pakistan">
                Pakistan
              </option>

              <option value="India">
                India
              </option>

              <option value="UK">
                United Kingdom
              </option>

              <option value="USA">
                United States
              </option>
            </select>

            {errors.country && (
              <p className="mt-1 text-sm text-red-600">
                {errors.country}
              </p>
            )}

          </div>


          {/* Account Type */}

          <div className="mt-6">

            <p className="mb-3 text-sm font-medium text-gray-700">
              Account Type
            </p>

            <div className="space-y-3">

              <label className="flex items-center gap-3">
                <input
                  type="radio"
                  name="accountType"
                  value="personal"
                  checked={form.accountType === "personal"}
                  onChange={handleChange}
                  className="h-4 w-4 text-blue-600"
                />

                <span className="text-sm text-gray-700">
                  Personal
                </span>
              </label>


              <label className="flex items-center gap-3">
                <input
                  type="radio"
                  name="accountType"
                  value="business"
                  checked={form.accountType === "business"}
                  onChange={handleChange}
                  className="h-4 w-4 text-blue-600"
                />

                <span className="text-sm text-gray-700">
                  Business
                </span>
              </label>

            </div>

            {errors.accountType && (
              <p className="mt-1 text-sm text-red-600">
                {errors.accountType}
              </p>
            )}

          </div>


          {/* Bio */}

          <div className="mt-5">

            <label
              htmlFor="bio"
              className="mb-2 block text-sm font-medium text-gray-700"
            >
              Bio
            </label>

            <textarea
              id="bio"
              name="bio"
              rows={4}
              value={form.bio}
              onChange={handleChange}
              placeholder="Tell us a little about yourself..."
              className="
                w-full
                resize-none
                rounded-lg
                border
                border-gray-300
                px-4
                py-3
                outline-none
                transition
                placeholder:text-gray-400
                focus:border-blue-500
                focus:ring-2
                focus:ring-blue-100
              "
            />

          </div>


          {/* Terms */}

          <div className="mt-6">

            <label className="flex items-start gap-3">

              <input
                type="checkbox"
                name="terms"
                checked={form.terms}
                onChange={handleChange}
                className="
                  mt-1
                  h-4
                  w-4
                  rounded
                  border-gray-300
                  text-blue-600
                "
              />

              <span className="text-sm text-gray-600">
                I agree to the terms and conditions.
              </span>

            </label>

            {errors.terms && (
              <p className="mt-1 text-sm text-red-600">
                {errors.terms}
              </p>
            )}

          </div>


          {/* Submit */}

          <button
            type="submit"
            className="
              mt-8
              w-full
              rounded-lg
              bg-blue-600
              px-6
              py-3
              font-semibold
              text-white
              transition
              hover:bg-blue-700
              active:scale-[0.98]
              focus:outline-none
              focus:ring-2
              focus:ring-blue-500
              focus:ring-offset-2
              disabled:cursor-not-allowed
              disabled:opacity-50
            "
          >
            Create Account
          </button>

        </form>

      </div>

    </main>
  );
}
```

## 16. Understand the Validation Flow

**The important part isn't just the UI. Understand how the validation works.**

When the user clicks:

```
Create Account
       ↓
handleSubmit()
       ↓
validateForm()
       ↓
Check fields
       ↓
Create errors object
       ↓
setErrors()
       ↓
React re-renders
       ↓
Show error UI
```

For example:

```
if (!form.firstName.trim()) {
  newErrors.firstName = "First name is required.";
}

If first name is empty:

errors = {
  firstName: "First name is required."
}

Then React displays:

{errors.firstName && (
  <p className="text-red-600">
    {errors.firstName}
  </p>
)}
```

## 17. The Three Main Form States

You should memorize this pattern.

```
Normal
border-gray-300
Error
border-red-500
focus:border-red-500
focus:ring-red-100
Success
border-green-500
focus:border-green-500
focus:ring-green-100
```


So your UI communicates:

```
┌─────────────────────────┐
│                         │
│ Normal                  │
│ border-gray             │
│                         │
└─────────────────────────┘
```

```
┌─────────────────────────┐
│                         │
│ Error                   │
│ border-red              │
│ ❌ Error message         │
│                         │
└─────────────────────────┘
```

```
┌─────────────────────────┐
│                         │
│ Success                 │
│ border-green            │
│ ✓ Valid                 │
│                         │
└─────────────────────────┘
```

## 18. Important Tailwind Form Variants

These are worth remembering:

```
focus:
focus-visible:
disabled:
checked:
placeholder:
hover:
active:
```

Examples:

```
<input className="
  focus:border-blue-500
  focus:ring-2
" />
<button className="
  disabled:opacity-50
  disabled:cursor-not-allowed
">
<input
  type="checkbox"
  className="
    checked:bg-blue-600
"
/>
<input className="
  placeholder:text-gray-400
" />
```

## 19. What You Should Be Able to Build After This Lesson

You should now be able to create:

```
✓ Login Form
✓ Registration Form
✓ Contact Form
✓ Search Form
✓ Checkout Form
✓ Profile Form
✓ Admin Form
✓ Multi-column Forms
✓ Responsive Forms
✓ Error UI
✓ Success UI
✓ Disabled UI
✓ Focus UI
```

And the most important mental model is:

```
                 FORM
                   │
        ┌──────────┼──────────┐
        ↓          ↓          ↓
      INPUT      SELECT     TEXTAREA
        │          │          │
        └──────────┼──────────┘
                   ↓
                STATES
                   │
       ┌───────────┼───────────┐
       ↓           ↓           ↓
     NORMAL       ERROR      SUCCESS
       │           │           │
       ↓           ↓           ↓
    gray        red         green
```

**This lesson gives you the Tailwind foundation for real-world form UI. The next step is to combine these with React form handling, validation, and eventually a backend/API so the registration form actually creates a user account.**



## Important Tailwind utilities

```
border
rounded
px / py
w-full
bg-*
text-*
placeholder:*
focus:*
focus:ring-*
focus:border-*
disabled:*
```

## Professional Focus state

```
className="
  rounded-lg
  border
  border-gray-300
  px-4
  py-3
  outline-none
  transition
  focus:border-blue-500
  focus:ring-2
  focus:ring-blue-100
  ```

---
