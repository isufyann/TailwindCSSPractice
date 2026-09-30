
# 5. Tailwind CSS — UI-5 Colors & Visual design

Tailwind provides color utilities that you can use for backgrounds, text, borders, rings, and more.

### Background colors

```
```

```
<div className="bg-blue-500">
  Blue background
</div>

<div className="bg-gray-100">
  Light gray background
</div>

<div className="bg-slate-900">
  Dark background
</div>
```

Common colors:

```
```

```
slate
gray
zinc
neutral
stone
red
orange
amber
yellow
green
emerald
teal
cyan
sky
blue
indigo
violet
purple
fuchsia
pink
rose
```

---

## 2. Text Colors

Use `text-*` utilities.

```
```

```
<h1 className="text-gray-900">
  Main Heading
</h1>

<p className="text-gray-600">
  Description text
</p>

<p className="text-blue-600">
  Primary text
</p>

<p className="text-red-500">
  Error message
</p>
```

The number represents the shade:

```
```

```
text-blue-100
text-blue-200
text-blue-300
text-blue-400
text-blue-500
text-blue-600
text-blue-700
text-blue-800
text-blue-900
text-blue-950
```

Generally:

- `100` → very light 
- `500` → medium 
- `600–700` → stronger 
- `900–950` → very dark 

---

## 3. Border Colors

```
```

```
<div className="border border-gray-200">
  Card
</div>

<div className="border-2 border-blue-500">
  Blue Border
</div>
```

You can combine border width and color:

```
```

```
<div className="border-2 border-purple-500">
  Content
</div>
```

---

## 4. Ring Colors

Rings are commonly used for focus states.

```
```

```
<input
  className="rounded-lg border border-gray-300
             focus:ring-2 focus:ring-blue-500
             focus:outline-none"
/>
```

Another example:

```
```

```
<button className="rounded-lg bg-blue-600 px-5 py-2
                   text-white
                   focus:ring-4 focus:ring-blue-200">
  Subscribe
</button>
```

---

## 5. Opacity

Tailwind supports opacity modifiers.

```
```

```
<div className="bg-black/50">
  50% transparent black
</div>
```

Examples:

```
```

```
bg-black/10
bg-black/25
bg-black/50
bg-black/75
bg-black/90
```

You can also use opacity with text:

```
```

```
<p className="text-white/70">
  Secondary text
</p>
```

---

# 6. Color Combinations

A professional UI usually uses a **consistent color system** instead of randomly choosing colors.

For example:

```
```

```
Primary:     Blue
Background:  White
Text:        Slate
Border:      Gray
Success:     Green
Error:       Red
```

Example:

```
```

```
<div className="bg-white text-slate-900">
  <h2 className="text-blue-600">
    Pro Plan
  </h2>

  <p className="text-slate-600">
    Perfect for growing teams.
  </p>

  <div className="border border-slate-200">
    Plan details
  </div>
</div>
```

---

# 7. Neutral Color Palettes

Neutral colors are useful for backgrounds and normal text.

```
```

```
<div className="bg-slate-50">
  Light background
</div>

<div className="bg-slate-900 text-white">
  Dark section
</div>
```

A common professional combination:

```
```

```
Background → slate-50
Cards      → white
Heading    → slate-900
Paragraph  → slate-600
Border     → slate-200
```

---

# 8. Brand Color Palettes

Choose one main brand color.

For example, blue:

```
```

```
<button className="bg-blue-600 text-white hover:bg-blue-700">
  Get Started
</button>
```

Or purple:

```
```

```
<button className="bg-purple-600 text-white hover:bg-purple-700">
  Get Started
</button>
```

The important thing is **consistency**.

---

# 9. Dark Color Palettes

For dark UI:

```
```

```
<div className="bg-slate-950 text-white">
  <h2 className="text-white">
    Dark Dashboard
  </h2>

  <p className="text-slate-400">
    Manage your account and settings.
  </p>
</div>
```

A useful dark palette:

```
```

```
Background → slate-950
Card       → slate-900
Border     → slate-800
Heading    → white
Text       → slate-400
Primary    → blue-500
```

---

# 10. Gradient Backgrounds

Tailwind provides:

```
```

```
bg-linear-to-r
bg-linear-to-l
bg-linear-to-b
bg-linear-to-t
```

Example:

```
```

```
<div className="bg-linear-to-r from-blue-600 to-purple-600 p-10">
  <h1 className="text-white text-4xl font-bold">
    Build Faster
  </h1>
</div>
```

---

# 11. Gradient Text

For gradient text, combine a gradient background with text clipping:

```
```

```
<h1 className="bg-linear-to-r from-blue-600 to-purple-600
               bg-clip-text text-5xl font-bold text-transparent">
  Build Amazing Products
</h1>
```

The important classes are:

```
```

```
bg-linear-to-r
from-blue-600
to-purple-600
bg-clip-text
text-transparent
```

---

# 12. Multi-Color Gradients

You can use multiple colors:

```
```

```
<div className="bg-linear-to-r
                from-blue-600
                via-purple-600
                to-pink-600
                p-10">
  Multi-color gradient
</div>
```

The gradient flows:

```
```

```
Blue → Purple → Pink
```

---

# 13. Hover Color Changes

Tailwind makes interactive colors easy.

```
```

```
<button className="
  bg-blue-600
  text-white
  hover:bg-blue-700
">
  Get Started
</button>
```

You can also change text:

```
```

```
<a className="text-gray-600 hover:text-blue-600">
  Learn More
</a>
```

And borders:

```
```

```
<div className="border border-gray-200 hover:border-blue-500">
  Hover me
</div>
```

---

# Build: Modern SaaS Pricing Section

Now let's combine everything you've learned.

```
```

```
export default function PricingSection() {
  return (
    <section className="min-h-screen bg-slate-50 px-6 py-20">

      {/* Header */}
      <div className="mx-auto max-w-3xl text-center">

        <p className="mb-3 text-sm font-semibold uppercase
                      tracking-wider text-blue-600">
          Pricing
        </p>

        <h1 className="
          bg-linear-to-r
          from-blue-600
          via-purple-600
          to-pink-600
          bg-clip-text
          text-4xl
          font-bold
          text-transparent
          md:text-5xl
        ">
          Simple pricing for everyone
        </h1>

        <p className="mt-4 text-lg leading-8 text-slate-600">
          Choose the plan that works best for your business.
          Upgrade whenever you need more features.
        </p>

      </div>


      {/* Pricing Cards */}
      <div className="
        mx-auto
        mt-12
        grid
        max-w-6xl
        gap-8
        md:grid-cols-3
      ">

        {/* Basic */}
        <div className="
          rounded-2xl
          border
          border-slate-200
          bg-white
          p-8
          shadow-sm
          transition
          hover:-translate-y-1
          hover:shadow-lg
        ">

          <h2 className="text-xl font-bold text-slate-900">
            Basic
          </h2>

          <p className="mt-2 text-slate-500">
            For individuals getting started.
          </p>

          <div className="mt-6">
            <span className="text-4xl font-bold text-slate-900">
              $9
            </span>

            <span className="text-slate-500">
              /month
            </span>
          </div>

          <button className="
            mt-8
            w-full
            rounded-lg
            border
            border-blue-600
            px-5
            py-3
            font-semibold
            text-blue-600
            transition
            hover:bg-blue-600
            hover:text-white
          ">
            Get Started
          </button>

          <ul className="mt-8 space-y-4 text-sm text-slate-600">
            <li>✓ 5 Projects</li>
            <li>✓ 10 GB Storage</li>
            <li>✓ Email Support</li>
            <li>✓ Basic Analytics</li>
          </ul>

        </div>


        {/* Pro */}
        <div className="
          relative
          rounded-2xl
          border-2
          border-blue-600
          bg-white
          p-8
          shadow-xl
          transition
          hover:-translate-y-1
        ">

          {/* Badge */}
          <div className="
            absolute
            -top-4
            left-1/2
            -translate-x-1/2
            rounded-full
            bg-blue-600
            px-4
            py-1
            text-sm
            font-semibold
            text-white
          ">
            Most Popular
          </div>

          <h2 className="text-xl font-bold text-slate-900">
            Pro
          </h2>

          <p className="mt-2 text-slate-500">
            For growing businesses.
          </p>

          <div className="mt-6">
            <span className="text-4xl font-bold text-slate-900">
              $29
            </span>

            <span className="text-slate-500">
              /month
            </span>
          </div>

          <button className="
            mt-8
            w-full
            rounded-lg
            bg-linear-to-r
            from-blue-600
            to-purple-600
            px-5
            py-3
            font-semibold
            text-white
            transition
            hover:from-blue-700
            hover:to-purple-700
            focus:ring-4
            focus:ring-blue-200
          ">
            Start Free Trial
          </button>

          <ul className="mt-8 space-y-4 text-sm text-slate-600">
            <li>✓ Unlimited Projects</li>
            <li>✓ 100 GB Storage</li>
            <li>✓ Priority Support</li>
            <li>✓ Advanced Analytics</li>
          </ul>

        </div>


        {/* Enterprise */}
        <div className="
          rounded-2xl
          border
          border-slate-800
          bg-slate-900
          p-8
          shadow-lg
          transition
          hover:-translate-y-1
          hover:shadow-xl
        ">

          <h2 className="text-xl font-bold text-white">
            Enterprise
          </h2>

          <p className="mt-2 text-slate-400">
            For large teams and organizations.
          </p>

          <div className="mt-6">
            <span className="text-4xl font-bold text-white">
              $99
            </span>

            <span className="text-slate-400">
              /month
            </span>
          </div>

          <button className="
            mt-8
            w-full
            rounded-lg
            bg-white
            px-5
            py-3
            font-semibold
            text-slate-900
            transition
            hover:bg-slate-200
          ">
            Contact Sales
          </button>

          <ul className="mt-8 space-y-4 text-sm text-slate-300">
            <li>✓ Unlimited Projects</li>
            <li>✓ 1 TB Storage</li>
            <li>✓ 24/7 Premium Support</li>
            <li>✓ Advanced Security</li>
          </ul>

        </div>

      </div>

    </section>
  );
}
```

### What this project practices

| Concept                  | Where used                                |
| ------------------------ | ----------------------------------------- |
| Background colors        | `bg-slate-50`, `bg-white`, `bg-slate-900` |
| Text colors              | `text-slate-900`, `text-slate-600`        |
| Border colors            | `border-slate-200`, `border-blue-600`     |
| Ring colors              | `focus:ring-blue-200`                     |
| Opacity                  | Can be added with `/50`, `/70`, etc.      |
| Neutral palette          | Slate colors                              |
| Brand palette            | Blue + purple                             |
| Dark palette             | Enterprise card                           |
| Gradient background      | Pro button                                |
| Gradient text            | Main heading                              |
| Multi-color gradient     | Blue → Purple → Pink heading              |
| Hover colors             | Buttons and cards                         |
| Responsive colors/layout | Combined with responsive utilities        |

This is a very good project for your current Tailwind stage because you're no longer just practicing individual utilities—you are learning how to build a **consistent design system inside a real UI**.
