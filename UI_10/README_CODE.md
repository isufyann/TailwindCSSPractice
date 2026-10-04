# UI_10 just  for try
## Important was skew, delay, custom animation below.

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
  return (
    <div className="min-h-screen bg-slate-100">
      <div className="h-8 w-8 border-4 border-gray-300 border-t-blue-600 rounded-full animate-spin">Hi</div>
      <div className="animate-ping bg-gray-300 h-6 w-32 rounded">
        Hi</div>
      <div className="bg-gray-300 h-6 w-32 rounded animate-slide-up">
        Hi slide up</div>

      <div className="groupbg-white rounded-2xl p-6 shadow-md transition-all duration-300 ease-in-out
        hover:-translate-y-2 hover:shadow-xl animate-slide-up">
        <div className="h-14 w-14 rounded-xl bg-blue-100 flex items-center justify-center 
        transition-transform duration-300 group-hover:scale-110">
          🚀
        </div>

        <h2 className="mt-4 text-xl font-bold">
          Full Stack Development
        </h2>

        <p className="mt-2 text-gray-600">
          Learn React, Next.js, Node.js and databases.
        </p>
      </div>
      <button
        className="bg-blue-600 hover:bg-blue-700 active:bg-blue-800 hover:scale-105 active:scale-95
        text-white px-6 py-3 rounded-lg transition-all duration-200 ease-in-out">
        Get Started
      </button>
      <button className="bg-blue-500 text-white hover:bg-green-500 duration-500">
        Hover Me
      </button>


      <div className="transition-transform skew-x-6">
        Box is here for the process
      </div>
      <div className="skew-6 transition-transform">
        Box
      </div>
    </div>
  );
}

```
