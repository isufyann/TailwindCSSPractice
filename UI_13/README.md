# Tailwind CSS — Advanced Features

You've already covered the core Tailwind topics: colors, typography, spacing, Flexbox, Grid, responsive design, states, forms, transitions, animations, and dark mode.
Now you're moving into the advanced Tailwind level.
The most important idea is:

**Tailwind normally gives you predefined utilities, but advanced Tailwind lets you customize CSS almost exactly when you need it.**

--- 

## 1. Arbitrary Values

An arbitrary value lets you use a value that Tailwind doesn't provide as a standard utility.
Syntax:

```[property]-[value]```
with square brackets.

**Width**
```
<div className="w-[420px]">
  Content
</div>
```

Instead of only:

```
w-96
w-[420px]
```

You can specify exactly 420px.
Background

```
<div className="bg-[#123456]">
  Custom color
</div>
```
Font size

```
<h1 className="text-[42px]">
  Custom Heading
</h1>
```
Margin

```
<div className="mt-[37px]">
  Content
</div>
```
Grid columns
```
<div className="grid-cols-[200px_1fr_300px]">
```

This is extremely useful for custom layouts.

---

## 2. Arbitrary Properties

Arbitrary properties allow you to write a CSS property directly inside a Tailwind class.
Syntax:
```[property:value]```

Example:

```
<div className="[scrollbar-width:none]">
  Content
</div>
```

This generates essentially:
scrollbar-width: none;
Another:

```<div className="[text-wrap:balance]">
  Long heading
</div>
```

Equivalent CSS:
text-wrap: balance;
You can also use CSS variables:

```<div className="[--card-width:420px]">
  Card
</div>
```
Difference
This:

```<div className="w-[420px]">
```

is an arbitrary value.
This:

```
<div className="[width:420px]">
```

is an arbitrary property.
Think:

```
w-[420px]
   ↑
Existing Tailwind utility
with custom value


[width:420px]
 ↑
Custom CSS property
```

---

3. Arbitrary Variants
Arbitrary variants allow you to create a custom selector directly.
For example:
<div className="[&>p]:text-gray-600">
  <p>Paragraph 1</p>
  <p>Paragraph 2</p>
</div>
& represents the current element.
This means approximately:
.parent > p {
  color: ...
}
Another example
<div className="[&_a]:text-blue-600">
  <a href="#">Link 1</a>
  <a href="#">Link 2</a>
</div>
All links inside become blue.
Hover child
<div className="[&_button:hover]:bg-blue-700">
  <button>
    Save
  </button>
</div>
This becomes useful when styling HTML structures where adding classes to every child would be repetitive.
________________________________________
4. Custom Utilities
Sometimes your application repeatedly needs a particular utility.
For example, suppose you frequently create:
rounded-xl
border
shadow-sm
bg-white
dark:bg-slate-900
You could create a reusable custom utility.
In Tailwind v4, you can define custom utilities in CSS using @utility.
@import "tailwindcss";

@utility card-surface {
  border: 1px solid var(--color-gray-200);
  border-radius: 0.75rem;
  background: white;
  box-shadow: 0 1px 3px rgb(0 0 0 / 0.1);
}
Then:
<div className="card-surface">
  Card content
</div>
You can also add dark-mode styling through your design tokens or additional CSS rules depending on your component architecture.
Why use custom utilities?
Instead of repeating:
className="
  rounded-xl
  border
  border-gray-200
  bg-white
  shadow-sm
"
you can have:
className="card-surface"
This becomes especially useful in a component library.
________________________________________
5. Custom Theme Values
Tailwind v4 uses CSS-first configuration.
You can define your own design tokens using @theme.
For example:
@import "tailwindcss";

@theme {
  --color-brand-500: #6366f1;
  --color-brand-600: #4f46e5;

  --font-display: "Inter", sans-serif;

  --radius-card: 1rem;
}
Now you can use:
<div className="bg-brand-500">
  Brand
</div>
And:
<h1 className="font-display">
  Dashboard
</h1>
You can create a consistent design system:
Brand
 ├── brand-400
 ├── brand-500
 ├── brand-600

Neutral
 ├── neutral-100
 ├── neutral-500
 └── neutral-900
________________________________________
6. CSS Variables
CSS variables are custom values that can be reused throughout your application.
Example:
:root {
  --brand-color: #4f46e5;
  --page-background: #f8fafc;
}
Then:
.button {
  background: var(--brand-color);
}
With Tailwind, arbitrary properties can also use variables:
<div className="bg-[var(--page-background)]">
  Content
</div>
You can also define variables inline:
<div
  style={{
    "--card-width": "420px",
  }}
  className="w-[var(--card-width)]"
>
  Card
</div>
This is particularly useful for reusable components.
________________________________________
7. CSS Variables + Theme
A more realistic design system:
@import "tailwindcss";

:root {
  --app-background: #f8fafc;
  --app-foreground: #0f172a;
  --card-background: #ffffff;
}

.dark {
  --app-background: #020617;
  --app-foreground: #f8fafc;
  --card-background: #0f172a;
}
Then:
<div className="
  min-h-screen
  bg-[var(--app-background)]
  text-[var(--app-foreground)]
">
And:
<div className="
  rounded-xl
  bg-[var(--card-background)]
">
Now your entire theme can be controlled by variables.
This becomes powerful for large applications.
________________________________________
8. Container Queries
This is an important advanced responsive feature.
Normal responsive design usually asks:
"How wide is the screen?"
Container queries ask:
"How wide is this component's container?"
This matters for reusable components.
Suppose you have a card:
<div className="@container">
  <div className="flex flex-col @md:flex-row">
    ...
  </div>
</div>
The outer element:
@container
becomes the query container.
Then:
@md:
means the container, rather than the browser viewport, has reached that breakpoint.
________________________________________
9. Viewport Responsive vs Container Responsive
Normal responsive
<div className="
  flex
  flex-col
  md:flex-row
">
This depends on:
Browser width
Container query
<div className="@container">

  <div className="
    flex
    flex-col
    @md:flex-row
  ">

  </div>

</div>
This depends on:
Component container width
This is excellent for component libraries.
Imagine the same Card component being used in:
Sidebar        → narrow
Main content   → wide
Modal          → medium
Dashboard      → wide
The component can adapt to its own available space.
________________________________________
10. Advanced Responsive Layouts
You can combine Grid, Flexbox, arbitrary values, and responsive variants.
Example:
<div className="
  grid
  grid-cols-1
  gap-6

  sm:grid-cols-2

  lg:grid-cols-[240px_1fr]

  xl:grid-cols-[280px_1fr_320px]
">
Layout changes:
Mobile
┌─────────────┐
│ Content     │
└─────────────┘

Tablet
┌──────┬──────┐
│      │      │
└──────┴──────┘

Desktop
┌──────┬────────────┬──────┐
│ Side │ Main       │ Side │
└──────┴────────────┴──────┘
You can also combine:
<div className="
  flex
  flex-col

  lg:flex-row
  lg:items-start
  lg:gap-8
">
________________________________________
11. Complex Selectors
Tailwind can target relationships between elements.
For example:
<div className="[&_h2]:text-2xl [&_p]:text-gray-600">
  <h2>Title</h2>
  <p>Description</p>
</div>
You can style:
all h2 elements
all p elements
inside that component.
Another example:
<div className="[&>div]:p-4">
  <div>One</div>
  <div>Two</div>
  <div>Three</div>
</div>
Every direct child <div> receives padding.
________________________________________
12. Data Attributes
Modern components often use data attributes to represent state.
Example:
<button data-state="open">
  Menu
</button>
Tailwind can respond to data attributes.
Example:
<button
  data-state="open"
  className="
    data-[state=open]:bg-blue-600
    data-[state=open]:text-white
  "
>
  Menu
</button>
You can also use:
data-[state=closed]:
data-[active=true]:
data-[status=error]:
This is especially useful with:
•	dropdowns 
•	tabs 
•	modals 
•	accordions 
•	menus 
•	component libraries 
________________________________________
13. Accessibility Variants
Tailwind has accessibility-focused variants.
One of the most important is:
sr-only
It visually hides content while keeping it available to screen readers.
Example:
<button>
  <span className="sr-only">
    Close menu
  </span>

  ✕
</button>
A sighted user sees:
✕
A screen reader can understand:
Close menu
________________________________________
14. focus-visible
You have already seen this earlier, but it becomes especially important for accessible components.
<button className="
  rounded-lg
  px-4
  py-2

  focus-visible:outline-none
  focus-visible:ring-2
  focus-visible:ring-blue-500
">
  Save
</button>
The focus indicator is primarily shown when keyboard navigation requires it.
This is better than completely removing focus indicators:
❌ outline-none only

✅ outline-none + focus-visible:ring
________________________________________
15. Reduced-Motion Variants
Some users configure their operating system to reduce animations.
Your application should respect that preference.
Tailwind provides:
motion-safe:
motion-reduce:
Normal animation
<div className="
  motion-safe:animate-bounce
">
  ↓
</div>
Animation happens when motion is allowed.
Disable animation for reduced motion
<div className="
  animate-bounce
  motion-reduce:animate-none
">
  ↓
</div>
This means:
Normal user
    ↓
animate-bounce

Reduced motion preference
    ↓
animate-none
This is an important accessibility practice.
________________________________________
16. Reduced Motion + Transitions
You can also control transitions:
<div className="
  transition-transform
  duration-300
  hover:scale-105
  motion-reduce:transition-none
  motion-reduce:hover:scale-100
">
  Card
</div>
For users who prefer reduced motion:
No transition
No scaling animation
________________________________________
17. Print Styles
Web pages aren't only viewed on screens.
Sometimes users print:
•	invoices 
•	reports 
•	documentation 
•	resumes 
•	receipts 
•	dashboards 
Tailwind provides the:
print:
variant.
Example:
<div className="
  bg-white
  print:bg-white
">
  Invoice
</div>
Hide something when printing:
<nav className="
  print:hidden
">
  Navigation
</nav>
Show something only when printing:
<p className="
  hidden
  print:block
">
  Printed document
</p>
You can create a print-friendly invoice:
<div className="mx-auto max-w-3xl p-8">

  <header className="print:hidden">
    <button>Download</button>
  </header>

  <main>
    <h1 className="text-3xl font-bold">
      Invoice #1001
    </h1>

    <p className="text-gray-600">
      Customer: John Doe
    </p>
  </main>

</div>
When printing:
Download button
      ↓
hidden
________________________________________
18. Combining Advanced Features
This is where Tailwind becomes very powerful.
For example:
<div className="
  @container
  rounded-xl
  bg-white
  p-6

  dark:bg-slate-900

  [--card-gap:1rem]

  @md:flex
  @md:gap-[var(--card-gap)]

  motion-safe:transition-transform
  motion-safe:duration-300

  motion-reduce:transition-none
">
You have combined:
@container
dark:
CSS variable
arbitrary value
container responsive
motion-safe
motion-reduce
transition
________________________________________
Build: Responsive Component Library
Now let's build a small reusable component library using the advanced features you've learned.
We'll create:
components/
│
├── Button.jsx
├── Card.jsx
├── Badge.jsx
├── StatsCard.jsx
└── Dashboard.jsx
________________________________________
19. Button Component
export default function Button({
  children,
  variant = "primary",
  disabled = false,
}) {
  const variants = {
    primary: `
      bg-blue-600
      text-white
      hover:bg-blue-700
      dark:bg-blue-500
      dark:hover:bg-blue-600
    `,

    secondary: `
      bg-gray-100
      text-gray-900
      hover:bg-gray-200
      dark:bg-slate-800
      dark:text-white
      dark:hover:bg-slate-700
    `,

    danger: `
      bg-red-600
      text-white
      hover:bg-red-700
    `,
  };

  return (
    <button
      disabled={disabled}
      className={`
        rounded-lg
        px-4
        py-2
        font-medium

        transition-colors
        duration-200

        focus-visible:outline-none
        focus-visible:ring-2
        focus-visible:ring-blue-500
        focus-visible:ring-offset-2

        disabled:cursor-not-allowed
        disabled:opacity-50

        motion-reduce:transition-none

        ${variants[variant]}
      `}
    >
      {children}
    </button>
  );
}
Usage:
<Button>
  Save
</Button>

<Button variant="secondary">
  Cancel
</Button>

<Button variant="danger">
  Delete
</Button>
________________________________________
20. Card Component
export default function Card({
  children,
  className = "",
}) {
  return (
    <div
      className={`
        rounded-xl
        border
        border-gray-200
        bg-white
        p-6
        shadow-sm

        dark:border-slate-800
        dark:bg-slate-900

        transition-all
        duration-300

        hover:shadow-lg

        motion-reduce:transition-none

        ${className}
      `}
    >
      {children}
    </div>
  );
}
Usage:
<Card>
  <h2 className="text-xl font-bold">
    Revenue
  </h2>

  <p className="mt-2 text-gray-600 dark:text-gray-400">
    $24,500
  </p>
</Card>
________________________________________
21. Badge Component
Here we can use data attributes.
export default function Badge({
  status = "success",
  children,
}) {
  return (
    <span
      data-status={status}
      className="
        inline-flex
        rounded-full
        px-3
        py-1
        text-xs
        font-medium

        data-[status=success]:bg-green-100
        data-[status=success]:text-green-700

        data-[status=warning]:bg-yellow-100
        data-[status=warning]:text-yellow-700

        data-[status=error]:bg-red-100
        data-[status=error]:text-red-700

        dark:data-[status=success]:bg-green-950
        dark:data-[status=success]:text-green-400

        dark:data-[status=warning]:bg-yellow-950
        dark:data-[status=warning]:text-yellow-400

        dark:data-[status=error]:bg-red-950
        dark:data-[status=error]:text-red-400
      "
    >
      {children}
    </span>
  );
}
Usage:
<Badge status="success">
  Active
</Badge>

<Badge status="warning">
  Pending
</Badge>

<Badge status="error">
  Failed
</Badge>
The component itself determines its visual state.
________________________________________
22. Container Query Stats Card
This is where container queries become useful.
export default function StatsCard({
  title,
  value,
  change,
}) {
  return (
    <div className="@container">

      <div className="
        rounded-xl
        border
        border-gray-200
        bg-white
        p-5

        dark:border-slate-800
        dark:bg-slate-900

        @md:flex
        @md:items-center
        @md:justify-between
      ">

        <div>
          <p className="
            text-sm
            text-gray-500
            dark:text-gray-400
          ">
            {title}
          </p>

          <p className="
            mt-2
            text-2xl
            font-bold
            text-gray-900
            dark:text-white

            @md:text-3xl
          ">
            {value}
          </p>
        </div>

        <span className="
          mt-3
          inline-block
          rounded-full
          bg-green-100
          px-3
          py-1
          text-sm
          text-green-700

          dark:bg-green-950
          dark:text-green-400

          @md:mt-0
        ">
          {change}
        </span>

      </div>

    </div>
  );
}
Notice:
@md:flex
@md:text-3xl
@md:mt-0
These respond to the component container, not necessarily the browser.
That's exactly why container queries are valuable in reusable components.
________________________________________
23. Dashboard Using the Components
import Button from "./components/Button";
import Card from "./components/Card";
import Badge from "./components/Badge";
import StatsCard from "./components/StatsCard";

export default function Dashboard() {
  return (
    <main className="
      min-h-screen
      bg-gray-100
      p-6
      text-gray-900

      dark:bg-slate-950
      dark:text-white

      md:p-10
    ">

      <div className="
        mx-auto
        max-w-7xl
      ">

        <header className="
          flex
          flex-col
          gap-4

          sm:flex-row
          sm:items-center
          sm:justify-between
        ">

          <div>
            <h1 className="text-3xl font-bold">
              Dashboard
            </h1>

            <p className="
              mt-2
              text-gray-600
              dark:text-gray-400
            ">
              Welcome back.
            </p>
          </div>

          <Button>
            Add Project
          </Button>

        </header>


        <section className="
          mt-8
          grid
          gap-5

          sm:grid-cols-2
          lg:grid-cols-3
        ">

          <StatsCard
            title="Revenue"
            value="$24,500"
            change="+12%"
          />

          <StatsCard
            title="Customers"
            value="1,240"
            change="+8%"
          />

          <StatsCard
            title="Orders"
            value="856"
            change="+15%"
          />

        </section>


        <section className="
          mt-8
          grid
          gap-6

          lg:grid-cols-2
        ">

          <Card>

            <div className="
              flex
              items-center
              justify-between
            ">

              <h2 className="text-xl font-bold">
                Recent Project
              </h2>

              <Badge status="success">
                Active
              </Badge>

            </div>

            <p className="
              mt-4
              text-gray-600
              dark:text-gray-400
            ">
              Building a modern SaaS dashboard.
            </p>

          </Card>


          <Card>

            <h2 className="text-xl font-bold">
              Actions
            </h2>

            <div className="
              mt-5
              flex
              flex-wrap
              gap-3
            ">

              <Button>
                Save
              </Button>

              <Button variant="secondary">
                Cancel
              </Button>

              <Button variant="danger">
                Delete
              </Button>

            </div>

          </Card>

        </section>

      </div>

    </main>
  );
}
________________________________________
24. Advanced Features You've Now Used
Our component library demonstrates:
Feature	Example
Arbitrary values	w-[420px]
Arbitrary properties	[scrollbar-width:none]
Arbitrary variants	[&_p]:text-gray-600
Custom utilities	@utility card-surface
Custom theme	@theme
CSS variables	var(--card-width)
Container queries	@container, @md:
Responsive layouts	sm:, md:, lg:
Complex selectors	[&_h2]:...
Data attributes	data-[status=success]:...
Accessibility	sr-only, focus-visible:
Reduced motion	motion-reduce:
Print	print:hidden
Dark mode	dark:
________________________________________
25. What to Use in Real Projects
Don't use advanced Tailwind features just because they're available.
Use them when they solve a real problem.
Use arbitrary values when:
Tailwind's standard scale doesn't have what you need.
Example:
w-[420px]
Use arbitrary properties when:
You need a CSS property that doesn't have a Tailwind utility.
Example:
[text-wrap:balance]
Use arbitrary variants when:
You need to target a specific HTML relationship.
Example:
[&_p]:text-gray-600
Use custom utilities when:
The same styling pattern appears repeatedly.
Use CSS variables when:
You need dynamic/reusable design values.
Use container queries when:
A reusable component should respond to its own available width.
Use data attributes when:
A component has states such as:
open
closed
active
error
success
Use motion-reduce when:
Your UI has animations.
Use print: when:
Your page needs a useful printed version.
________________________________________
26. The Advanced Tailwind Mental Model
You've now progressed from:
TAILWIND BASICS
       ↓
Utilities
       ↓
Responsive
       ↓
States
       ↓
Forms
       ↓
Transitions
       ↓
Dark Mode
       ↓
ADVANCED TAILWIND
And the advanced layer looks like:
                    ADVANCED TAILWIND
                           │
       ┌───────────────────┼───────────────────┐
       ↓                   ↓                   ↓
   Custom CSS          Responsive           Component
       │                   │                   │
 arbitrary values     container queries    data states
 arbitrary props      complex layouts      custom utilities
 CSS variables         print styles         theme tokens
       │                   │                   │
       └───────────────────┼───────────────────┘
                           ↓
                 REUSABLE COMPONENT
                      LIBRARY
One important rule
Don't try to memorize every advanced utility.
Instead, remember what problem each feature solves:
Need exact value?          → Arbitrary value

Need CSS property?         → Arbitrary property

Need custom selector?      → Arbitrary variant

Repeated utility pattern?  → Custom utility

Need design tokens?        → @theme

Need dynamic values?        → CSS variables

Component-based responsive?
                            → Container queries

Component state?           → Data attributes

Keyboard accessibility?    → focus-visible

Screen-reader content?     → sr-only

Animations + accessibility?
                            → motion-reduce

Printable page?            → print:
That is the point where Tailwind stops being just a collection of utility classes and starts becoming a complete design-system tool for building reusable React/Next.js components.

