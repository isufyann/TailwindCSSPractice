# code reference for dark mode.

## use of toggle button and change color to light/dark.

```
import { useState } from "react";

export default function Home() {
  
  const [dark, setDark] = useState(false);

  function toggleTheme() {
    const newTheme = !dark;
    setDark(newTheme);
    document.documentElement.classList.toggle(
      "dark",
      newTheme
    );
  }
```

## Now use in Navbar to set light/dark.

```
<nav className="flex fixed w-full top-0 z-10 items-center justify-between p-4 text-white bg-black shadow-2xl shadow-black
                      dark:bg-blue-50 dark:text-black">
        <div className="text-2xl font-bold">
          Logo Here
        </div>

        <div className="hidden md:flex gap-6 text-xl mx-7">
          <a href="#" className="active:scale-90 font-bold hover:scale-120 duration-300 hover:bg-white hover:text-black rounded-2xl px-3 py-1 shadow-lg shadow-cyan-500 hover:shadow-sm">Home</a>
          <a href="#" className="active:scale-90 font-bold hover:scale-120 duration-300 hover:bg-white hover:text-black rounded-2xl px-3 py-1 shadow-lg shadow-cyan-500 hover:shadow-sm">About</a>
          <a href="#" className="active:scale-90 font-bold hover:scale-120 duration-300 hover:bg-white hover:text-black rounded-2xl px-3 py-1 shadow-lg shadow-cyan-500 hover:shadow-sm">Services</a>
          <a href="#" className="active:scale-90 font-bold hover:scale-120 duration-300 hover:bg-white hover:text-black rounded-2xl px-3 py-1 shadow-lg shadow-cyan-500 hover:shadow-sm">Contact</a>
          <button className="bg-cyan-100 font-bold text-black px-4 rounded-lg hover:bg-blue-300">
            Login
          </button>
          {/* Dark mode */}
          <button onClick={toggleTheme}>
            <p className="bg-slate-100 text-gray-900 rounded-2xl px-3 dark:bg-gray-900 dark:text-slate-100">
              {dark ? "☀️ Light" : "🌙 Dark"}
            </p>
          </button>
```
