# Code reference for Dark Mode.

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

---


# ChatGPT Code for dashboard

```
"use client";

import { useState } from "react";

export default function Dashboard() {
  const [dark, setDark] = useState(false);

  function toggleTheme() {
    const newTheme = !dark;

    setDark(newTheme);

    document.documentElement.classList.toggle(
      "dark",
      newTheme
    );
  }

  const stats = [
    {
      title: "Total Sales",
      value: "$24,560",
      change: "+12.5%",
    },
    {
      title: "Customers",
      value: "1,248",
      change: "+8.2%",
    },
    {
      title: "Orders",
      value: "856",
      change: "+5.4%",
    },
  ];

  return (
    <div className="
      min-h-screen
      bg-gray-100
      text-gray-900
      transition-colors
      duration-300

      dark:bg-slate-950
      dark:text-white
    ">

      {/* Navbar */}

      <header className="
        sticky
        top-0
        z-50
        border-b
        border-gray-200
        bg-white/90
        backdrop-blur

        dark:border-slate-800
        dark:bg-slate-900/90
      ">

        <div className="
          flex
          h-16
          items-center
          justify-between
          px-6
        ">

          <h1 className="
            text-xl
            font-bold
            text-gray-900
            dark:text-white
          ">
            MyDashboard
          </h1>


          <div className="flex items-center gap-4">

            <button
              onClick={toggleTheme}
              className="
                rounded-lg
                border
                border-gray-300
                bg-white
                px-4
                py-2
                text-sm
                font-medium
                text-gray-700
                transition

                hover:bg-gray-100

                dark:border-slate-700
                dark:bg-slate-800
                dark:text-gray-200
                dark:hover:bg-slate-700
              "
            >
              {dark ? "☀️ Light" : "🌙 Dark"}
            </button>

            <div className="
              flex
              h-9
              w-9
              items-center
              justify-center
              rounded-full
              bg-blue-600
              font-semibold
              text-white
            ">
              JD
            </div>

          </div>

        </div>

      </header>


      <div className="flex">

        {/* Sidebar */}

        <aside className="
          hidden
          min-h-[calc(100vh-4rem)]
          w-64
          border-r
          border-gray-200
          bg-white
          p-4

          dark:border-slate-800
          dark:bg-slate-900

          md:block
        ">

          <nav className="space-y-2">

            <a
              href="#"
              className="
                block
                rounded-lg
                bg-blue-50
                px-4
                py-3
                font-medium
                text-blue-600

                dark:bg-blue-950
                dark:text-blue-400
              "
            >
              Dashboard
            </a>

            <a
              href="#"
              className="
                block
                rounded-lg
                px-4
                py-3
                text-gray-600
                transition

                hover:bg-gray-100

                dark:text-gray-300
                dark:hover:bg-slate-800
              "
            >
              Analytics
            </a>

            <a
              href="#"
              className="
                block
                rounded-lg
                px-4
                py-3
                text-gray-600
                transition

                hover:bg-gray-100

                dark:text-gray-300
                dark:hover:bg-slate-800
              "
            >
              Customers
            </a>

            <a
              href="#"
              className="
                block
                rounded-lg
                px-4
                py-3
                text-gray-600
                transition

                hover:bg-gray-100

                dark:text-gray-300
                dark:hover:bg-slate-800
              "
            >
              Settings
            </a>

          </nav>

        </aside>


        {/* Main Content */}

        <main className="
          flex-1
          p-6
          md:p-8
        ">

          {/* Heading */}

          <div className="mb-8">

            <h2 className="
              text-3xl
              font-bold
              text-gray-900
              dark:text-white
            ">
              Welcome back, John
            </h2>

            <p className="
              mt-2
              text-gray-600
              dark:text-gray-400
            ">
              Here's what's happening with your business.
            </p>

          </div>


          {/* Stats */}

          <div className="
            grid
            gap-5
            sm:grid-cols-2
            lg:grid-cols-3
          ">

            {stats.map((stat) => (
              <div
                key={stat.title}
                className="
                  rounded-xl
                  border
                  border-gray-200
                  bg-white
                  p-6
                  shadow-sm
                  transition-all
                  duration-300

                  hover:-translate-y-1
                  hover:shadow-lg

                  dark:border-slate-800
                  dark:bg-slate-900
                  dark:hover:border-slate-700
                "
              >

                <p className="
                  text-sm
                  font-medium
                  text-gray-500
                  dark:text-gray-400
                ">
                  {stat.title}
                </p>

                <div className="
                  mt-3
                  flex
                  items-end
                  justify-between
                ">

                  <p className="
                    text-3xl
                    font-bold
                    text-gray-900
                    dark:text-white
                  ">
                    {stat.value}
                  </p>

                  <span className="
                    rounded-full
                    bg-green-100
                    px-2
                    py-1
                    text-xs
                    font-medium
                    text-green-700

                    dark:bg-green-950
                    dark:text-green-400
                  ">
                    {stat.change}
                  </span>

                </div>

              </div>
            ))}

          </div>


          {/* Recent Activity */}

          <div className="
            mt-8
            overflow-hidden
            rounded-xl
            border
            border-gray-200
            bg-white
            shadow-sm

            dark:border-slate-800
            dark:bg-slate-900
          ">

            <div className="
              border-b
              border-gray-200
              px-6
              py-5

              dark:border-slate-800
            ">

              <h3 className="
                font-semibold
                text-gray-900
                dark:text-white
              ">
                Recent Activity
              </h3>

            </div>


            <div className="overflow-x-auto">

              <table className="w-full text-left">

                <thead className="
                  bg-gray-50
                  dark:bg-slate-800
                ">

                  <tr>

                    <th className="
                      px-6
                      py-4
                      text-sm
                      font-semibold
                      text-gray-700

                      dark:text-gray-300
                    ">
                      User
                    </th>

                    <th className="
                      px-6
                      py-4
                      text-sm
                      font-semibold
                      text-gray-700

                      dark:text-gray-300
                    ">
                      Action
                    </th>

                    <th className="
                      px-6
                      py-4
                      text-sm
                      font-semibold
                      text-gray-700

                      dark:text-gray-300
                    ">
                      Date
                    </th>

                  </tr>

                </thead>


                <tbody className="
                  divide-y
                  divide-gray-200

                  dark:divide-slate-800
                ">

                  <tr className="
                    transition
                    hover:bg-gray-50
                    dark:hover:bg-slate-800/50
                  ">

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-900
                      dark:text-gray-200
                    ">
                      Sarah
                    </td>

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-600
                      dark:text-gray-400
                    ">
                      Created a new order
                    </td>

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-500
                      dark:text-gray-500
                    ">
                      Today
                    </td>

                  </tr>


                  <tr className="
                    transition
                    hover:bg-gray-50
                    dark:hover:bg-slate-800/50
                  ">

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-900
                      dark:text-gray-200
                    ">
                      Michael
                    </td>

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-600
                      dark:text-gray-400
                    ">
                      Updated profile
                    </td>

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-500
                      dark:text-gray-500
                    ">
                      Yesterday
                    </td>

                  </tr>


                  <tr className="
                    transition
                    hover:bg-gray-50
                    dark:hover:bg-slate-800/50
                  ">

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-900
                      dark:text-gray-200
                    ">
                      David
                    </td>

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-600
                      dark:text-gray-400
                    ">
                      Completed payment
                    </td>

                    <td className="
                      px-6
                      py-4
                      text-sm
                      text-gray-500
                      dark:text-gray-500
                    ">
                      2 days ago
                    </td>

                  </tr>

                </tbody>

              </table>

            </div>

          </div>

        </main>

      </div>

    </div>
  );
}
```
