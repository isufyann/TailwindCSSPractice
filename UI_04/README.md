# Tailwind CSS — Typography Mastery

Typography controls how your text **looks, feels, and behaves**. These utilities are used constantly in React/Next.js projects.

---

## 1. Font Family

Tailwind provides font-family utilities.

```jsx
<p className="font-sans">Sans Serif</p>
<p className="font-serif">Serif</p>
<p className="font-mono">Monospace</p>
```

Common:

```text
font-sans
font-serif
font-mono
```

---

## 2. Font Size

Use `text-*`.

```jsx
<p className="text-sm">Small</p>
<p className="text-base">Normal</p>
<p className="text-lg">Large</p>
<p className="text-xl">XL</p>
<p className="text-2xl">2XL</p>
<p className="text-4xl">4XL</p>
<p className="text-6xl">6XL</p>
```

For a heading:

```jsx
<h1 className="text-4xl">
  Welcome
</h1>
```

---

## 3. Font Weight

Use `font-*`.

```jsx
<p className="font-light">Light</p>
<p className="font-normal">Normal</p>
<p className="font-medium">Medium</p>
<p className="font-semibold">Semi Bold</p>
<p className="font-bold">Bold</p>
<p className="font-extrabold">Extra Bold</p>
```

Very common:

```jsx
<h1 className="font-bold">
  My Website
</h1>
```

---

## 4. Line Height

Use `leading-*`.

```jsx
<p className="leading-none">Text</p>
<p className="leading-normal">Text</p>
<p className="leading-relaxed">Text</p>
<p className="leading-loose">Text</p>
```

You can use numeric values:

```jsx
<p className="leading-7">
  This is a paragraph with comfortable line spacing.
</p>
```

For paragraphs, something like:

```jsx
<p className="text-lg leading-8">
```

often produces easier-to-read text.

---

## 5. Letter Spacing

Use `tracking-*`.

```jsx
<p className="tracking-tighter">Tighter</p>
<p className="tracking-normal">Normal</p>
<p className="tracking-wide">Wide</p>
<p className="tracking-widest">Widest</p>
```

Example:

```jsx
<h1 className="tracking-wide">
  WELCOME
</h1>
```

---

## 6. Text Alignment

Use:

```text
text-left
text-center
text-right
text-justify
```

Examples:

```jsx
<h1 className="text-center">
  Welcome
</h1>
```

```jsx
<p className="text-left">
  Paragraph
</p>
```

Responsive alignment:

```jsx
<h1 className="text-center lg:text-left">
  Responsive Heading
</h1>
```

Meaning:

```text
Mobile  → center
Desktop → left
```

---

## 7. Text Decoration

Use:

```text
underline
overline
line-through
no-underline
```

Examples:

```jsx
<p className="underline">
  Underlined text
</p>
```

```jsx
<p className="line-through">
  Old Price
</p>
```

For links:

```jsx
<a href="#" className="underline">
  Read More
</a>
```

Remove decoration:

```jsx
<a href="#" className="no-underline">
  Home
</a>
```

---

## 8. Text Transformation

Change the capitalization using:

```text
uppercase
lowercase
capitalize
normal-case
```

Examples:

```jsx
<p className="uppercase">
  hello world
</p>
```

Result:

```text
HELLO WORLD
```

```jsx
<p className="lowercase">
  HELLO WORLD
</p>
```

Result:

```text
hello world
```

```jsx
<p className="capitalize">
  hello world
</p>
```

Result:

```text
Hello World
```

---

## 9. Text Truncation

Sometimes text is too long for its container.

Use:

```jsx
<p className="truncate">
  This is a very long piece of text that will be truncated when it doesn't fit inside the available width.
</p>
```

`truncate` typically combines the behavior needed to display:

```text
This is a very long piece of text...
```

You'll usually want a constrained width:

```jsx
<p className="w-64 truncate">
  This is a very long piece of text that cannot fit.
</p>
```

---

## 10. `line-clamp`

`line-clamp` limits text to a specific number of lines.

For example:

```jsx
<p className="line-clamp-2">
  This is a long description that should only display two lines
  and then hide the remaining content from the user.
</p>
```

Result conceptually:

```text
This is a long description that should
only display two lines and then...
```

Other examples:

```text
line-clamp-1
line-clamp-2
line-clamp-3
line-clamp-4
```

Very useful for **cards**:

```jsx
<div className="w-80">
  <h2 className="text-xl font-bold">
    Product Name
  </h2>

  <p className="mt-2 line-clamp-3 text-gray-600">
    Long product description...
  </p>
</div>
```

---

## 11. Gradient Text

You can create attractive gradient text using a background gradient and clipping.

```jsx
<h1 className="bg-gradient-to-r from-blue-500 to-purple-600 bg-clip-text text-5xl font-bold text-transparent">
  Tailwind CSS
</h1>
```

Break it down:

```text
bg-gradient-to-r
        ↓
gradient goes left → right

from-blue-500
        ↓
starting color

to-purple-600
        ↓
ending color

bg-clip-text
        ↓
background is clipped to text

text-transparent
        ↓
makes the actual text transparent
```

This technique is commonly used for modern hero headings.

---

## 12. Responsive Typography

You can change typography at different screen sizes.

```jsx
<h1 className="text-3xl font-bold sm:text-4xl md:text-5xl lg:text-6xl">
  Build Your Future
</h1>
```

Meaning:

```text
Mobile → 3xl
sm     → 4xl
md     → 5xl
lg     → 6xl
```

You can also change line height:

```jsx
<p className="text-base leading-6 md:text-lg md:leading-8">
  Learn modern web development.
</p>
```

And alignment:

```jsx
<h1 className="text-center lg:text-left">
  Welcome
</h1>
```

---

## 13. Custom Google Fonts

For a Next.js project, a good approach is using `next/font/google`.

Example:

```jsx
import { Inter } from "next/font/google";

const inter = Inter({
  subsets: ["latin"],
});

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body className={inter.className}>
        {children}
      </body>
    </html>
  );
}
```

Now your application uses the **Inter** Google Font.

You can also use another font:

```jsx
import { Poppins } from "next/font/google";

const poppins = Poppins({
  subsets: ["latin"],
  weight: ["400", "600", "700"],
});
```

Then:

```jsx
<body className={poppins.className}>
```

### Why use `next/font`?

It integrates the font into your Next.js application rather than relying on a separate Google Fonts `<link>`.

---

## 14. Heading Hierarchy

Good websites don't make every heading the same size.

Use semantic HTML:

```html
<h1>Page Title</h1>

<h2>Section Title</h2>

<h3>Subsection Title</h3>

<h4>Small Heading</h4>
```

Then style them:

```jsx
<h1 className="text-4xl font-bold md:text-6xl">
  Full Stack Development
</h1>

<h2 className="mt-10 text-3xl font-bold">
  Learn React
</h2>

<h3 className="mt-6 text-2xl font-semibold">
  Components
</h3>
```

Think of the hierarchy as:

```text
H1
│
├── H2
│   ├── H3
│   └── H3
│
└── H2
    └── H3
```

### Important

Don't use `<h1>` simply because you want large text.

For example, this:

```jsx
<h1 className="text-6xl">
  Welcome
</h1>
```

is both:

- semantically an H1
- visually large

But if you only need visual size without a heading, use:

```jsx
<p className="text-6xl font-bold">
  Welcome
</p>
```

---

# 🔥 Complete Typography Example

Here's how these concepts come together in a real hero section:

```jsx
<section className="px-4 py-16 text-center md:px-8 lg:text-left">
  <h1 className="bg-gradient-to-r from-blue-500 to-purple-600 bg-clip-text text-4xl font-extrabold tracking-tight text-transparent sm:text-5xl md:text-6xl">
    Become a Full Stack Developer
  </h1>

  <h2 className="mt-4 text-2xl font-semibold leading-tight text-gray-800 md:text-3xl">
    Learn React, Next.js and Node.js
  </h2>

  <p className="mx-auto mt-6 max-w-2xl text-base leading-7 text-gray-600 md:text-lg lg:mx-0">
    Build modern, responsive and professional web applications using
    modern full stack technologies.
  </p>

  <a
    href="#"
    className="mt-6 inline-block font-semibold text-blue-600 underline"
  >
    Start Learning
  </a>
</section>
```

You've now combined:

```text
Font family
Font size
Font weight
Line height
Letter spacing
Text alignment
Text decoration
Text transformation
Text truncation
Line clamp
Gradient text
Responsive typography
Google Fonts
Heading hierarchy
```

### 🧠 The typography formula

When styling text, think in this order:

```text
Font
 ↓
Size
 ↓
Weight
 ↓
Line Height
 ↓
Letter Spacing
 ↓
Color
 ↓
Alignment
 ↓
Responsive Changes
```

For example:

```jsx
className="
  text-4xl
  font-bold
  leading-tight
  tracking-tight
  text-gray-900
  md:text-6xl
"
```

That's the core **Tailwind typography workflow** you'll use throughout your React/Next.js projects.
