# Tailwind CSS — Borders, Radius, Shadows & Rings

These utilities are important for creating professional cards, buttons, forms, and interactive UI components.

## 1. Border Width
```code 
<div className="border">1px border</div>

<div className="border-2">2px border</div>

<div className="border-4">4px border</div>

<div className="border-8">8px border</div>
```
You can combine width with color:
```code
<div className="border-2 border-blue-500">
  Blue border
</div>
```

---

## 2. Individual Borders

You don't have to apply a border to every side.

```
<div className="border-t border-gray-300">
  Top border
</div>

<div className="border-b border-gray-300">
  Bottom border
</div>

<div className="border-l border-blue-500">
  Left border
</div>

<div className="border-r border-blue-500">
  Right border
</div>
```
You can also combine sides:

```
<div className="border-x border-gray-300">
  Left + right
</div>

<div className="border-y border-gray-300">
  Top + bottom
</div>
```

--- 

## 3. Border Styles

Tailwind supports different border styles:

```
<div className="border-2 border-solid border-gray-400">
  Solid
</div>

<div className="border-2 border-dashed border-gray-400">
  Dashed
</div>

<div className="border-2 border-dotted border-gray-400">
  Dotted
</div>

<div className="border-2 border-double border-gray-400">
  Double
</div>
```

--- 

## 4. Border Radius

Rounded corners are controlled with rounded-*.

```
<div className="rounded">
  Small radius
</div>

<div className="rounded-lg">
  Large radius
</div>

<div className="rounded-xl">
  Extra large radius
</div>

<div className="rounded-2xl">
  Very rounded
</div>

<div className="rounded-full">
  Fully rounded
</div>
```

--- 

## 5. Rounded Cards

A common card design:

```
<div className="
  rounded-2xl
  border
  border-gray-200
  bg-white
  p-6
">
  <h2 className="text-xl font-bold">
    Pro Plan
  </h2>

  <p className="mt-2 text-gray-600">
    Perfect for growing businesses.
  </p>
</div>
```

--- 

## 6. Rounded Buttons

```
<button className="
  rounded-lg
  bg-blue-600
  px-5
  py-3
  font-semibold
  text-white
">
  Get Started
</button>
For pill-shaped buttons:
<button className="
  rounded-full
  bg-blue-600
  px-6
  py-3
  text-white
">
  Subscribe
</button>
```

--- 

## 7. Circular Elements

Use rounded-full with equal width and height.

```
<div className="
  flex
  h-12
  w-12
  items-center
  justify-center
  rounded-full
  bg-blue-600
  text-white
">
  A
</div>
```

--- 

This is useful for:

* Profile images 
* Avatars 
* Icons 
* Notification badges 
* Status indicators 

--- 

## 8. Shadows

Shadows create depth.

```
<div className="shadow-sm">
  Small shadow
</div>

<div className="shadow">
  Normal shadow
</div>

<div className="shadow-md">
  Medium shadow
</div>

<div className="shadow-lg">
  Large shadow
</div>

<div className="shadow-xl">
  Extra large shadow
</div>

<div className="shadow-2xl">
  Very large shadow
</div>
A card might use:
<div className="
  rounded-2xl
  bg-white
  p-6
  shadow-lg
">
  Pricing Card
</div>
```

--- 


## 9. Custom Shadows

Tailwind also supports arbitrary values.

```
<div className="
  shadow-[0_10px_40px_rgba(0,0,0,0.12)]
">
  Custom shadow
</div>
```

You can control:


```
X offset
Y offset
Blur
Spread
Color
```

For example:

``` shadow-[0_10px_30px_rgba(0,0,0,0.15)] ```
________________________________________
## 10. Rings

A ring is an outline around an element.

```
<div className="
  rounded-xl
  bg-white
  p-6
  ring-2
  ring-blue-500
">
  Highlighted Card
</div>
You can change its color:
<div className="ring-2 ring-purple-500">
  Content
</div>
```

Ring width:

```
ring-1
ring-2
ring-4
ring-8
```

--- 

## 11. Focus Rings

Focus rings are especially important for accessibility and forms.

```
<input
  type="text"
  placeholder="Enter your name"
  className="
    w-full
    rounded-lg
    border
    border-gray-300
    px-4
    py-3
    outline-none
    focus:border-blue-500
    focus:ring-4
    focus:ring-blue-100
  "
/>
```

When the user clicks or tabs into the input:

```
Normal
   ↓
focus:border-blue-500
   +
focus:ring-4
   +
focus:ring-blue-100
```

You can also use it on buttons:

```
<button className="
  rounded-lg
  bg-blue-600
  px-5
  py-3
  text-white
  outline-none
  focus:ring-4
  focus:ring-blue-200
">
  Continue
</button>
```

--- 

## 12. Divide Utilities

divide-* adds borders between child elements.
```
<div className="divide-y divide-gray-200">

  <div className="p-4">
    Basic
  </div>

  <div className="p-4">
    Pro
  </div>

  <div className="p-4">
    Enterprise
  </div>

</div>
```

This produces:

```
Basic
──────────────
Pro
──────────────
```

Enterprise

For horizontal layouts:

```
<div className="flex divide-x divide-gray-200">
  <div className="px-4">One</div>
  <div className="px-4">Two</div>
  <div className="px-4">Three</div>
</div>
```

## 13. Border Opacity

You can control border opacity using /.

```
<div className="border border-black/10">
  Very light border
</div>
```

Other examples:
```
border-black/10
border-black/20
border-black/30
border-blue-500/50
```
This is useful when you want subtle borders

--- 

### Build: Modern Pricing Card

Now let's combine **border + radius + shadow + hover + ring + focus states** into one realistic component.

```code
export default function PricingCard() {
  return (
    <section className="flex min-h-screen items-center justify-center bg-slate-50 px-6 py-12">

      <div
        className="
          w-full
          max-w-sm
          rounded-2xl
          border
          border-slate-200
          bg-white
          p-8
          shadow-md

          transition
          duration-300

          hover:-translate-y-2
          hover:border-blue-300
          hover:shadow-2xl
        "
      >

        {/* Header */}
        <div className="mb-6">

          <div className="mb-4 flex items-center justify-between">

            <h2 className="text-2xl font-bold text-slate-900">
              Pro Plan
            </h2>

            <span
              className="
                rounded-full
                bg-blue-100
                px-3
                py-1
                text-xs
                font-semibold
                text-blue-700
              "
            >
              Popular
            </span>

          </div>

          <p className="text-sm leading-6 text-slate-500">
            Everything you need to build and grow your
            application.
          </p>

        </div>


        {/* Price */}
        <div className="mb-8">

          <span className="text-5xl font-bold text-slate-900">
            $29
          </span>

          <span className="ml-2 text-slate-500">
            / month
          </span>

        </div>


        {/* Button */}
        <button
          className="
            w-full
            rounded-xl
            bg-blue-600
            px-5
            py-3
            font-semibold
            text-white

            transition
            duration-200

            hover:bg-blue-700

            focus:outline-none
            focus:ring-4
            focus:ring-blue-200
          "
        >
          Start Free Trial
        </button>


        {/* Features */}
        <div className="mt-8 divide-y divide-slate-100">

          <div className="flex items-center gap-3 py-3">
            <span
              className="
                flex
                h-6
                w-6
                items-center
                justify-center
                rounded-full
                bg-green-100
                text-sm
                text-green-600
              "
            >
              ✓
            </span>

            <span className="text-sm text-slate-600">
              Unlimited projects
            </span>
          </div>


          <div className="flex items-center gap-3 py-3">
            <span
              className="
                flex
                h-6
                w-6
                items-center
                justify-center
                rounded-full
                bg-green-100
                text-sm
                text-green-600
              "
            >
              ✓
            </span>

            <span className="text-sm text-slate-600">
              100 GB storage
            </span>
          </div>


          <div className="flex items-center gap-3 py-3">
            <span
              className="
                flex
                h-6
                w-6
                items-center
                justify-center
                rounded-full
                bg-green-100
                text-sm
                text-green-600
              "
            >
              ✓
            </span>

            <span className="text-sm text-slate-600">
              Priority support
            </span>
          </div>


          <div className="flex items-center gap-3 py-3">
            <span
              className="
                flex
                h-6
                w-6
                items-center
                justify-center
                rounded-full
                bg-green-100
                text-sm
                text-green-600
              "
            >
              ✓
            </span>

            <span className="text-sm text-slate-600">
              Advanced analytics
            </span>
          </div>

        </div>

      </div>

    </section>
  );
}
```

### Important part: Hover elevation

This section creates the card's hover effect:

```
transition
duration-300
hover:-translate-y-2
hover:border-blue-300
hover:shadow-2xl
```

So the card:

**Normal → slightly moves upward → border changes → shadow becomes stronger
Important part: Focus state**

The button uses:

```
focus:outline-none
focus:ring-4
focus:ring-blue-200
```

This gives the user a visible focus indicator when the button receives keyboard/mouse focus.

**Concepts you've now practiced**
```
Border
 ├── width
 ├── individual sides
 ├── style
 └── opacity

Radius
 ├── cards
 ├── buttons
 └── circles

Shadow
 ├── normal
 ├── large
 ├── hover elevation
 └── custom shadows

Ring
 ├── ring width
 ├── ring color
 └── focus ring

Divide
 ├── divide-y
 └── divide-x

States
 ├── hover:
 └── focus:
```

This pricing card is a strong practice project because it combines the **Tailwind border, radius, shadow, ring, state, and spacing utilities** into one realistic component.

