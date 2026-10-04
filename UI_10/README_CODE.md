# UI_10 Animated SaaS Product Cards

## Important was skew, delay, custom animation below.
## Professional Button

### Custom CSS in globals.css

```
@import "tailwindcss";

:root {
  --background: #ffffff;
  --foreground: #171717;
}

@theme inline {
  --color-background: var(--background);
  --color-foreground: var(--foreground);
  --font-sans: var(--font-geist-sans);
  --font-mono: var(--font-geist-mono);

  /* Custom animation */  
  --animate-slide-up: slide-up 0.5s ease-out;
   @keyframes slide-up {
    from {
      opacity: 0;
      transform: translateY(70px);
    }

    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
}


@media (prefers-color-scheme: dark) {
  :root {
    --background: #0a0a0a;
    --foreground: #ededed;
  }
}

body {
  background: var(--background);
  color: var(--foreground);
  font-family: Arial, Helvetica, sans-serif;
}

```


```
  export default function UI() {
    const plans = [
      {
        name: "Starter",
        price: "$9",
        description: "For individuals getting started.",
      },
      {
        name: "Professional",
        price: "$29",
        description: "For growing businesses.",
      },
      {
        name: "Enterprise",
        price: "$99",
        description: "For large organizations.",
      },
    ];

    return (
      <section className="bg-slate-100 px-6 py-20">
        <div className="mx-auto max-w-6xl">

          <div className="mb-12 text-center">
            <h1 className="text-4xl font-bold text-slate-900">
              Choose Your Plan
            </h1>

            <p className="mt-4 text-slate-600">
              Simple pricing for every stage of your business.
            </p>
          </div>

          <div className="grid gap-8 md:grid-cols-3">

            {plans.map((plan, index) => (
              <div
                key={plan.name}
                className={`
                  group
                  rounded-2xl
                  bg-white
                  p-8
                  shadow-md

                  transition-all
                  duration-300
                  ease-out

                  hover:-translate-y-2
                  hover:shadow-2xl
                `}
              >

                <div className="
                  flex
                  h-14
                  w-14
                  items-center
                  justify-center
                  rounded-xl
                  bg-blue-100
                  text-2xl

                  transition-transform
                  duration-300

                  group-hover:scale-110
                  group-hover:rotate-6
                ">
                  🚀
                </div>

                <h2 className="mt-6 text-2xl font-bold text-slate-900">
                  {plan.name}
                </h2>

                <p className="mt-2 text-slate-600">
                  {plan.description}
                </p>

                <div className="mt-6">
                  <span className="text-4xl font-bold text-slate-900">
                    {plan.price}
                  </span>

                  <span className="text-slate-500">
                    /month
                  </span>
                </div>

                <button className="
                  mt-8
                  w-full
                  rounded-lg
                  bg-blue-600
                  px-5
                  py-3
                  font-semibold
                  text-white

                  transition-all
                  duration-200
                  ease-out

                  hover:bg-blue-700
                  hover:-translate-y-0.5
                  hover:shadow-lg

                  active:scale-95

                  focus-visible:outline-none
                  focus-visible:ring-2
                  focus-visible:ring-blue-500
                  focus-visible:ring-offset-2
                ">
                  Get Started
                </button>

              </div>
            ))}

          </div>
        </div>
      </section>
    );
  }
```

```
<button className="
  rounded-lg
  bg-blue-600
  px-6
  py-3
  font-semibold
  text-white

  transition-all
  duration-200
  ease-out

  hover:bg-blue-700
  hover:-translate-y-0.5
  hover:shadow-lg

  active:translate-y-0
  active:scale-95

  focus-visible:outline-none
  focus-visible:ring-2
  focus-visible:ring-blue-500
  focus-visible:ring-offset-2
">
  Get Started
</button>
```
