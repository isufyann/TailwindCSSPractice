# Responsive Design with Tailwind CSS

We will cover **mobile, tablet, laptop, and large screens**.

The most important concept is **mobile-first design**.

---

## 1. Understand Mobile-First Design

Tailwind is **mobile-first**.

You write the mobile design first:

```jsx
<div className="text-xl">
```

Then add larger-screen changes:

```jsx
<div className="text-xl md:text-3xl lg:text-5xl">
```

Meaning:

| Screen | Style |
|---|---|
| Mobile | `text-xl` |
| `md` screen | `text-3xl` |
| `lg` screen | `text-5xl` |

Think:

```text
Mobile
   ↓
Tablet
   ↓
Laptop
   ↓
Desktop
```

You don't normally write:

```text
desktop first → then fix mobile
```

Instead:

```text
mobile first → enhance for larger screens
```

---

## 2. `sm:`

`sm:` applies a utility at the **small breakpoint and above**.

Example:

```jsx
<div className="text-xl sm:text-2xl">
  Hello
</div>
```

Meaning:

| Screen | Style |
|---|---|
| Mobile | `text-xl` |
| `sm` and above | `text-2xl` |

> **Important:** `sm:` does **not** mean "mobile."

It means:

> Apply this utility when the viewport reaches the `sm` breakpoint or larger.

---

## 3. `md:`

`md:` applies styles at the medium breakpoint and above.

```jsx
<h1 className="text-2xl md:text-4xl">
  Welcome
</h1>
```

Meaning:

| Screen | Style |
|---|---|
| Mobile | `text-2xl` |
| `md+` | `text-4xl` |

Very common for tablet/desktop adjustments.

---

## 4. `lg:`

`lg:` applies styles at the large breakpoint and above.

```jsx
<div className="p-4 lg:p-10">
```

Meaning:

| Screen | Style |
|---|---|
| Mobile | `p-4` |
| `lg+` | `p-10` |

---

## 5. `xl:`

`xl:` applies styles at extra-large screens.

```jsx
<h1 className="text-3xl xl:text-6xl">
```

Meaning:

| Screen | Style |
|---|---|
| Mobile | `text-3xl` |
| `xl+` | `text-6xl` |

---

## 6. `2xl:`

`2xl:` is for very large screens.

```jsx
<div className="max-w-full 2xl:max-w-7xl">
```

You can use it when you want a layout to become wider or more spacious on very large displays.

---

## Tailwind Breakpoint Mental Model

A typical responsive chain looks like:

| Breakpoint | Meaning |
|---|---|
| Base | Mobile |
| `sm:` | Small |
| `md:` | Medium |
| `lg:` | Large |
| `xl:` | Extra large |
| `2xl:` | Very large |

For example:

```jsx
<div className="
  text-xl
  sm:text-2xl
  md:text-3xl
  lg:text-4xl
  xl:text-5xl
  2xl:text-6xl
">
  Responsive Heading
</div>
```

---

## 7. Change Typography Responsively

You can change:

- Font size
- Font weight
- Line height
- Letter spacing

Example:

```jsx
<h1 className="text-3xl font-bold md:text-5xl lg:text-6xl">
  Build Your Future
</h1>
```

Result:

| Screen | Size |
|---|---|
| Mobile | `3xl` |
| Tablet | `5xl` |
| Desktop | `6xl` |

### Responsive Paragraph

```jsx
<p className="text-sm leading-6 md:text-base md:leading-7 lg:text-lg">
  Learn full stack development with modern technologies.
</p>
```

---

## 8. Change Spacing Responsively

You can change padding:

```jsx
<section className="p-4 md:p-8 lg:p-16">
```

Meaning:

| Screen | Padding |
|---|---|
| Mobile | `16px` |
| `md` | Larger |
| `lg` | Much larger |

### Change Margin

```jsx
<div className="mt-4 md:mt-8 lg:mt-12">
```

### Change Gap

```jsx
<div className="flex gap-3 md:gap-6 lg:gap-8">
```

This allows your design to breathe more on larger screens.

---

## 9. Change Layout Responsively

This is one of the most useful techniques.

Suppose you have two columns.

### On Mobile

```text
Image
Text
```

### On Desktop

```text
Image    Text
```

Use:

```jsx
<div className="flex flex-col lg:flex-row">
  <div>Image</div>
  <div>Text</div>
</div>
```

Meaning:

```text
Mobile  → flex-col
Desktop → flex-row
```

---

## 10. Hide / Show Elements Responsively

Use `hidden` and responsive utilities.

### Hide on Mobile, Show on Desktop

```jsx
<div className="hidden md:block">
  Desktop Menu
</div>
```

Meaning:

```text
Mobile → hidden
md+    → visible
```

### Show on Mobile, Hide on Desktop

```jsx
<div className="block md:hidden">
  Mobile Menu
</div>
```

Meaning:

```text
Mobile → visible
md+    → hidden
```

This is very useful for navigation.

---

## 11. Change Grid Columns Responsively

This is probably one of the most common patterns you'll use.

```jsx
<div className="grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-3">
```

Meaning:

```text
Mobile  → 1 column
Tablet  → 2 columns
Desktop → 3 columns
```

Example:

```jsx
<div className="grid grid-cols-1 gap-6 sm:grid-cols-2 lg:grid-cols-3">
  <div>Card 1</div>
  <div>Card 2</div>
  <div>Card 3</div>
  <div>Card 4</div>
  <div>Card 5</div>
  <div>Card 6</div>
</div>
```

### Visual

#### Mobile

```text
┌───────────┐
│ Card 1    │
├───────────┤
│ Card 2    │
├───────────┤
│ Card 3    │
└───────────┘
```

#### Tablet

```text
┌────────┬────────┐
│ Card 1 │ Card 2 │
├────────┼────────┤
│ Card 3 │ Card 4 │
└────────┴────────┘
```

#### Desktop

```text
┌────────┬────────┬────────┐
│ Card 1 │ Card 2 │ Card 3 │
├────────┼────────┼────────┤
│ Card 4 │ Card 5 │ Card 6 │
└────────┴────────┴────────┘
```

---

## 12. Change Flex Direction Responsively

Very common:

```jsx
<div className="flex flex-col md:flex-row">
  <div>Left</div>
  <div>Right</div>
</div>
```

### Mobile

```text
Left
Right
```

### Desktop

```text
Left    Right
```

You can also do:

```jsx
<div className="flex flex-col-reverse md:flex-row">
```

---

## 13. Build Mobile Navigation

A common approach is:

```jsx
<nav className="flex items-center justify-between p-4">

  <div className="text-2xl font-bold">
    MyLogo
  </div>

  <div className="hidden md:flex gap-6">
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Services</a>
    <a href="#">Contact</a>
  </div>

  <button className="md:hidden">
    ☰
  </button>

</nav>
```

### Mobile

```text
┌──────────────────────────┐
│ MyLogo              ☰    │
└──────────────────────────┘
```

### Desktop

```text
┌────────────────────────────────────┐
│ MyLogo   Home About Services Contact│
└────────────────────────────────────┘
```

### Important

Tailwind only handles the **visual responsive behavior** here.

For a real mobile menu that opens/closes, you'll later use **React state**:

```jsx
const [open, setOpen] = useState(false);
```

---

## 14. Build Responsive Cards

Example:

```jsx
<div className="grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-3">

  <div className="rounded-xl p-6 shadow-lg">

    <h2 className="text-xl font-bold md:text-2xl">
      React
    </h2>

    <p className="mt-3 text-sm md:text-base">
      Learn React for modern web applications.
    </p>

    <button className="mt-5 rounded-lg bg-blue-500 px-4 py-2 text-white">
      Learn More
    </button>

  </div>

</div>
```

The card automatically adapts to screen size.

---

## 15. Build Responsive Tables

Tables can become difficult on mobile because they need horizontal space.

A simple solution is horizontal scrolling:

```jsx
<div className="overflow-x-auto">

  <table className="min-w-full">

    <thead>
      <tr>
        <th className="p-4 text-left">Name</th>
        <th className="p-4 text-left">Email</th>
        <th className="p-4 text-left">Role</th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <td className="p-4">Ali</td>
        <td className="p-4">ali@example.com</td>
        <td className="p-4">Developer</td>
      </tr>
    </tbody>

  </table>

</div>
```

The important class is:

```text
overflow-x-auto
```

On a small screen, the user can scroll horizontally instead of the table breaking the page.

---

## 16. Build Responsive Hero Sections

A common hero section:

```jsx
<section className="px-4 py-12 md:px-8 md:py-20 lg:px-16 lg:py-28">

  <div className="mx-auto flex max-w-7xl flex-col items-center gap-10 lg:flex-row">

    <div className="text-center lg:w-1/2 lg:text-left">

      <h1 className="text-4xl font-bold md:text-5xl lg:text-6xl">
        Build Modern Websites
      </h1>

      <p className="mt-5 text-base leading-7 md:text-lg">
        Create beautiful and responsive websites with Tailwind CSS.
      </p>

      <button className="mt-6 rounded-lg bg-blue-600 px-6 py-3 text-white">
        Get Started
      </button>

    </div>

    <div className="w-full lg:w-1/2">
      Image
    </div>

  </div>

</section>
```

### Mobile

```text
Heading
   ↓
Paragraph
   ↓
Button
   ↓
Image
```

### Desktop

```text
┌─────────────────┬─────────────────┐
│                 │                 │
│ Heading         │                 │
│ Paragraph       │     Image       │
│ Button          │                 │
│                 │                 │
└─────────────────┴─────────────────┘
```

---

# 🧠 Most Important Rule

Tailwind responsive classes are **min-width based**.

For example:

```jsx
<div className="text-xl md:text-4xl">
```

means:

```text
             md
              ↓

text-xl ──────┬──────── text-4xl ─────────→
              │
           larger
          screens
```

The `text-xl` is the **base/mobile style**.

`md:text-4xl` says:

> From `md` size upward, change the text to `text-4xl`.

---

# Real-World Example

Here's a complete responsive section using almost everything you've learned:

```jsx
<section className="px-4 py-10 sm:px-6 md:px-10 md:py-16 lg:px-16 lg:py-24">

  <div className="mx-auto flex max-w-7xl flex-col items-center gap-10 lg:flex-row">

    <div className="w-full text-center lg:w-1/2 lg:text-left">

      <h1 className="text-3xl font-bold sm:text-4xl md:text-5xl lg:text-6xl">
        Learn Full Stack Development
      </h1>

      <p className="mt-4 text-sm leading-6 sm:text-base md:text-lg">
        Learn React, Next.js, Node.js and modern web development.
      </p>

      <div className="mt-6 flex flex-col gap-3 sm:flex-row sm:justify-center lg:justify-start">

        <button className="rounded-lg bg-blue-600 px-6 py-3 text-white">
          Get Started
        </button>

        <button className="rounded-lg border border-gray-300 px-6 py-3">
          Learn More
        </button>

      </div>

    </div>

    <div className="w-full lg:w-1/2">

      <div className="h-64 rounded-xl bg-gray-200 sm:h-80 lg:h-96">
        Hero Image
      </div>

    </div>

  </div>

</section>
```

Notice the pattern:

```text
Base  → Mobile
sm:   → Small
md:   → Medium
lg:   → Large
xl:   → Extra Large
2xl:  → Very Large
```

## Your Responsive-Design Formula

For most projects, you'll frequently write patterns like:

```text
grid-cols-1 md:grid-cols-2 lg:grid-cols-3
```

```text
flex-col lg:flex-row
```

```text
text-3xl md:text-5xl lg:text-6xl
```

```text
p-4 md:p-8 lg:p-16
```

```text
hidden md:block
```

```text
block md:hidden
```

If you become comfortable with these patterns, you'll be able to build **responsive React/Next.js interfaces without writing separate CSS for every screen size**.
