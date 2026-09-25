# Tailwind CSS — UI-01 Fundamentals

## Install Tailwind CSS in a Project

### 1. Create a Next.js Project

```bash
npx create-next-app@latest tailwind-project
```

Run the development server:

```bash
npm run dev
```

Open:

```text
http://localhost:3000
```

For creating a new Next.js project:

```bash
npx create-next-app@latest
```

---

# Configure Tailwind CSS

## Configure Tailwind CSS in an Existing Next.js Project

If Tailwind CSS is already installed, configure it like this.

### 1. `postcss.config.mjs`

```js
const config = {
  plugins: {
    "@tailwindcss/postcss": {},
  },
};

export default config;
```

### 2. `src/app/globals.css`

```css
@import "tailwindcss";
```

### 3. Test Tailwind in `src/app/page.js`

```jsx
export default function Home() {
  return (
    <h1 className="text-4xl font-bold text-blue-500">
      Tailwind CSS
    </h1>
  );
}
```

### 4. Start the Project

```bash
npm run dev
```

This is the basic **Tailwind CSS v4 configuration** for Next.js.

---

## Install Tailwind CSS in an Existing Next.js Project

For an existing Next.js project, install Tailwind CSS with:

```bash
npm install tailwindcss @tailwindcss/postcss
```

Then create or update `postcss.config.mjs`:

```js
const config = {
  plugins: {
    "@tailwindcss/postcss": {},
  },
};

export default config;
```

In `globals.css`, add:

```css
@import "tailwindcss";
```

Then run:

```bash
npm run dev
```

### Important

For a new Next.js project, you normally don't need to separately run:

```bash
npm install tailwindcss
```

---

# Utility-First CSS

Utility-first CSS means styling your HTML directly using small, single-purpose CSS classes.

Tailwind CSS is based on this approach.

---

## Traditional CSS

In traditional CSS, you might create a reusable `.card` class:

```css
.card {
  background-color: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 10px gray;
}
```

Then use it like this:

```html
<div class="card">
  Hello
</div>
```

---

## Tailwind / Utility-First CSS

Instead of creating a `.card` class, we combine small utility classes:

```jsx
<div className="bg-white p-5 rounded-lg shadow-lg">
  Hello
</div>
```

Each class performs one main job.

| Tailwind Class   | Purpose          |
| ---------------- | ---------------- |
| `bg-white`       | Background color |
| `p-5`            | Padding          |
| `rounded-lg`     | Border radius    |
| `shadow-lg`      | Shadow           |
| `text-blue-500`  | Text color       |
| `text-2xl`       | Font size        |
| `font-bold`      | Font weight      |
| `mt-4`           | Margin top       |
| `flex`           | Flexbox          |
| `items-center`   | Align items      |
| `justify-center` | Justify content  |

---

# Example: Tailwind Button

```jsx
<button className="bg-blue-500 text-white px-6 py-3 rounded-lg font-bold">
  Get Started
</button>
```

### Break It Down

| Class         | Meaning            |
| ------------- | ------------------ |
| `bg-blue-500` | Blue background    |
| `text-white`  | White text         |
| `px-6`        | Horizontal padding |
| `py-3`        | Vertical padding   |
| `rounded-lg`  | Rounded corners    |
| `font-bold`   | Bold text          |

---

# Combine Utility Classes

You don't usually need to create a new CSS class for every component.

Instead, combine existing utility classes to create the design.

Tailwind CSS provides many core utility classes.

---

# Apply Colors

```jsx
<p className="text-blue-500">
  Blue Text
</p>

<p className="text-red-500">
  Red Text
</p>

<p className="text-green-500">
  Green Text
</p>

<p className="text-gray-700">
  Gray Text
</p>
```

---

# Apply Background Colors

```jsx
<div className="bg-blue-500">
  Blue Background
</div>
```

---

# Apply Border Colors

First, add a border:

```jsx
<div className="border border-red-500">
  Red Border
</div>
```

We can also control border thickness:

```text
border
border-2
border-4
border-6
```

---

# Set Font Sizes

Use:

```text
text-*
```

Common examples:

```text
text-sm
text-base
text-lg
text-xl
text-2xl
```

Example:

```jsx
<h1 className="text-2xl">
  Tailwind CSS
</h1>
```

---

# Set Font Weights

Use:

```text
font-*
```

Common examples:

```text
font-light
font-normal
font-medium
font-semibold
font-bold
font-extrabold
```

Example:

```jsx
<h1 className="font-bold">
  Tailwind CSS
</h1>
```

---

# Set Line Heights

Use:

```text
leading-*
```

Common examples:

```text
leading-none
leading-tight
leading-normal
leading-relaxed
leading-loose
```

You can also use numeric values:

```text
leading-1
leading-2
leading-3
leading-4
leading-5
leading-6
```

Example:

```jsx
<p className="leading-6">
  Learn Tailwind CSS.
</p>
```

---

# Set Letter Spacing

Use:

```text
tracking-*
```

Common examples:

```text
tracking-tight
tracking-normal
tracking-wide
tracking-widest
```

Example:

```jsx
<p className="tracking-wide">
  Tailwind CSS
</p>
```

---

# Set Element Width

Use:

```text
w-*
```

Examples:

```text
w-20
w-40
w-64
w-auto
w-full
w-screen
w-1/2
w-1/3
w-2/3
w-14
```

Example:

```jsx
<div className="w-full">
  Full Width
</div>
```

---

# Set Element Height

Use:

```text
h-*
```

Examples:

```text
h-20
h-40
h-64
h-auto
h-full
h-screen
```

Example:

```jsx
<div className="h-screen">
  Full Screen Height
</div>
```

---

# Minimum and Maximum Width

## Minimum Width

Use:

```text
min-w-*
```

Examples:

```text
min-w-20
min-w-40
min-w-64
```

## Maximum Width

Use:

```text
max-w-*
```

Examples:

```text
max-w-20
max-w-lg
max-w-xl
max-w-2xl
max-w-3xl
max-w-4xl
max-w-5xl
max-w-6xl
max-w-7xl
```

A commonly used layout is:

```jsx
<div className="max-w-7xl mx-auto">
  Content
</div>
```

### Explanation

```text
max-w-7xl → Maximum width
mx-auto   → Center horizontally
```

---

# Minimum and Maximum Height

## Minimum Height

```text
min-h-screen
```

Example:

```jsx
<div className="min-h-screen">
  Content
</div>
```

## Maximum Height

```text
max-h-96
```

Example:

```jsx
<div className="max-h-96 overflow-auto">
  Content
</div>
```

`overflow-auto` allows scrolling when the content exceeds the maximum height.

---

# Apply Padding

Padding controls the space **inside** an element.

## All Sides

```text
p-4
```

## Horizontal Padding

```text
px-4
```

Left + right.

## Vertical Padding

```text
py-4
```

Top + bottom.

## Individual Sides

```text
pt-4
pb-4
pl-4
pr-4
```

| Class  | Meaning      |
| ------ | ------------ |
| `p-4`  | All sides    |
| `px-4` | Left + right |
| `py-4` | Top + bottom |
| `pt-4` | Top          |
| `pb-4` | Bottom       |
| `pl-4` | Left         |
| `pr-4` | Right        |

Example:

```jsx
<div className="p-4">
  Content
</div>
```

---

# Apply Margin

Margin controls the space **outside** an element.

```jsx
<div className="m-4">
  Content
</div>
```

Common margin utilities:

| Class  | Meaning      |
| ------ | ------------ |
| `m-4`  | All sides    |
| `mx-4` | Left + right |
| `my-4` | Top + bottom |
| `mt-4` | Top          |
| `mb-4` | Bottom       |
| `ml-4` | Left         |
| `mr-4` | Right        |

---

## Center an Element

```jsx
<div className="mx-auto">
  Centered
</div>
```

`mx-auto` applies automatic horizontal margins.

---

# Understand the Spacing Scale

The Tailwind spacing system is very important.

Classes such as:

```text
p-4
m-4
mt-4
gap-4
px-6
py-3
```

use Tailwind's spacing scale.

The number represents a predefined spacing value.

For example:

```text
p-2
p-4
p-6
p-8
```

The larger the value, the larger the spacing.

---

# Arbitrary Values

Sometimes Tailwind's predefined values aren't enough.

You can provide your own value using square brackets:

```text
[]
```

Example:

```jsx
<div className="w-[420px]">
  Custom Width
</div>
```

You can use arbitrary values with many utility classes.

### Custom Height

```jsx
<div className="h-[300px]">
  Custom Height
</div>
```

### Custom Margin

```jsx
<div className="mt-[35px]">
  Custom Margin
</div>
```

### Custom Padding

```jsx
<div className="p-[25px]">
  Custom Padding
</div>
```

---

# Combine Multiple Utilities Correctly

Example:

```jsx
<div className="w-80 bg-white p-6 rounded-xl shadow-lg">

  <h2 className="text-2xl font-bold text-gray-800">
    Tailwind CSS
  </h2>

  <p className="mt-3 text-gray-600 leading-6">
    Learn Tailwind CSS utility classes.
  </p>

  <button className="mt-5 bg-blue-500 px-6 py-3 text-white font-semibold rounded-lg">
    Learn More
  </button>

</div>
```

### Understanding the Example

The outer `div` uses:

```text
w-80
bg-white
p-6
rounded-xl
shadow-lg
```

The heading uses:

```text
text-2xl
font-bold
text-gray-800
```

The paragraph uses:

```text
mt-3
text-gray-600
leading-6
```

The button uses:

```text
mt-5
bg-blue-500
px-6
py-3
text-white
font-semibold
rounded-lg
```

---

# The Main Concept

Don't think:

> "I need to create a `.card` CSS class."

Think:

> "What properties does my card need?"

For example:

```text
Width
Background
Padding
Border radius
Shadow
Text color
Font size
Font weight
```

Then combine the appropriate Tailwind utilities.

---

# Core Utilities Covered So Far

Try to use the utilities in this order:

```text
text
↓
bg
↓
border
↓
font
↓
leading
↓
tracking
↓
w
↓
h
↓
p
↓
m
↓
rounded
↓
shadow
```

---

# Practice Task

## Create a Profile Card

Create a profile card using only the Tailwind utilities covered in this lesson.

Your profile card should contain:

* Profile image
* Name
* Job title
* Short description
* Button
* Background
* Padding
* Rounded corners
* Shadow
* Proper text sizes
* Proper spacing

Example structure:

```jsx
<div className="...">

  <img
    src="..."
    alt="Profile"
    className="..."
  />

  <h2 className="...">
    Muhammad Sufyan
  </h2>

  <p className="...">
    Full Stack Developer
  </p>

  <p className="...">
    Learning React, Next.js, Node.js and Tailwind CSS.
  </p>

  <button className="...">
    View Profile
  </button>

</div>
```

Try to build the card yourself before looking at a solution.

---

# UI-02 — Layout Mastery

## Next Topic

**Understand the CSS Box Model through Tailwind CSS.**

Topics to learn next:

* Box model
* Content
* Padding
* Border
* Margin
* Width and height
* `box-sizing`
* Spacing
* Flexbox
* Grid
* Positioning
* Responsi
