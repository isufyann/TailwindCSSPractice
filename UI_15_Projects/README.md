# Create designs of above learning.

## UI_16_01 Design a navbar

### app/components/navbar/page.tsx

```
'use client'
import { useState } from "react";

export default function Navbar() {
    const [dark, setDark] = useState(false);

    function toggleTheme() {
        const newTheme = !dark;
        setDark(newTheme);
        document.documentElement.classList.toggle(
            "dark",
            newTheme
        );
    }

    return (
        <main>
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


                    <div className="relative hover:scale-120 duration-300">
                        <button className="text-2xl bg-gray-800 rounded-xl">🔔</button>
                        <span className="absolute h-3 w-3 text-xs text-white -top-1 -right-1 flex items-center justify-center rounded-2xl">7</span>
                    </div>
                </div>
                <button className="text-2xl text-white block md:hidden">
                    ☰
                </button>

            </nav>

        </main>
    );
}
```

---

## UI_16_02 Design a megamenu

### app/components/navbar/page.tsx

```
import Image from "next/image";
import img_profile from "@/public/img/img_profile.png"

export default function Megamenu() {
    return (
        <main>
            <div className="grid grid-cols-1 md:grid-cols-2 p-5">
                {/* Leftside */}
                <div className="bg-linear-to-r from-blue-300 via-orange-400 to-red-300 rounded-2xl m-3 p-15">
                    <h1 className="text-5xl font-bold p-5">
                        Build for next generation of debt-free vehicle
                    </h1>
                    <p className="text-xl p-5">
                        There is nothing perfect than our services.
                        English has international language and the language of science and technology.
                    </p>
                    <div className="flex flex-row  gap-5">
                        <button className="bg-blue-700 text-white rounded px-5 py-3">
                            Click for More
                        </button>
                        <button className="bg-gray-700 text-white rounded px-5 py-3">
                            Join our Team
                        </button>
                    </div>
                </div>

                {/* Rightside */}
                <div className="grid grid-cols-1 md:grid-cols-2">
                    {/* sideLeftside` */}
                    <div className="">
                        <div className="w-1/2 h-1/2 items-center flex justify-center">
                            <Image src={img_profile} alt="Profile image"></Image>
                        </div>
                        <div>
                            <h2 className="text-2xl font-bold ">Overview</h2>
                            <p className="text-xl">Eastern side</p>

                            <div className="flex flex-row gap-3 m-5">
                                <div className="text-center bg-gray-200 p-1 rounded-2xl ">
                                    97 <br />
                                    <span className="text-lg font-bold text-black">Public Score</span>
                                </div>
                                <div className="text-center bg-gray-200 p-1 rounded-2xl ">
                                    97 <br />
                                    <span className="text-lg font-bold text-black">Public Score</span>
                                </div>
                                <div className="text-center bg-gray-200 p-1 rounded-2xl ">
                                    97 <br />
                                    <span className="text-lg font-bold text-black">Public Score</span>
                                </div>
                            </div>
                        </div>

                    </div>
                    {/* sideRigthside */}
                    <div className="bg-gray-100">
                        <div>
                            <Image src={img_profile} alt="Profile image" className="w-50 h-50"></Image>
                        </div>

                        <div className="bg-orange-100 grid grid-cols-1 md:grid-cols-2 rounded-4xl">
                            <div className="p-5 bg-white rounded-2xl m-3">
                                Savings
                            </div>
                            <div className="p-5 bg-white font-bold rounded-2xl">
                                Subscriptions
                            </div>
                        </div>
                        <div className="">
                            <Image src={img_profile} alt="Profile image"></Image>
                        </div>

                        <div className="bg-orange-100 grid grid-cols-1 md:grid-cols-2 rounded-4xl">
                            <div className="p-5 bg-white rounded-2xl m-3">
                                Savings
                            </div>
                            <div className="p-5 bg-white font-bold rounded-2xl">
                                Subscriptions
                            </div>
                        </div>

                    </div>

                </div>
            </div>


        </main>
    );
}
```

---

## UI_16_03 Design a Hero Section

### app/components/hero/page.tsx

```

import Image from "next/image"
import img_profile from "@/public/img/img_profile.png"

export default function Hero() {
    return (
        <main>
            <div>
                <h1 className="text-5xl text-blue-200 text-center p-3 font-bold ">My Profile</h1>
                <div className="flex justify-center items-center p-3">
                    <Image className="rounded-4xl hover:scale-110 duration-300 shadow-2xl shadow-gray-400" src={img_profile} alt="Franchise Pic" width={200} height={100}></Image>
                </div>
                <h2 className="dark:text-black animate-slide-up font-bold text-5xl uppercase tracking-widest text-center p-3 font-sans bg-linear-to-r from-blue-900 via-cyan-100 to-red-900 bg-clip-text text-transparent">Muhammad Sufyan </h2>
                <p className="text-white font-bold text-xl text-center animate-slide-up">Software Engineers</p>
                <p className="text-white font-semibold text-xl text-center pb-3 animate-slide-up">Learning AI Agents from MCASCE</p>
            </div>

            <div className="flex flex-wrap justify-center space-x-15 bg-linear-to-b from-gray-800 to-black py-5">
                <div className="bg-black text-white p-4 text-center rounded-2xl hover:scale-115 duration-300 border-b-2 border-white">13+ Projects<br /><span className="text-gray-400 text-sm">Projects</span></div>
                <div className="bg-black text-white p-4 text-center rounded-2xl scale-120 hover:scale-135 duration-300 border-b-2 border-white">10+ Technologies<br /><span className="text-gray-400 text-sm">Technologies</span></div>
                <div className="bg-black text-white p-4 text-center rounded-2xl hover:scale-115 duration-300 border-b-2 border-white">2+ Years <br /><span className="text-gray-400 text-sm">Experience</span>
                </div>
            </div>
        </main>
    );
}
```

---

## UI_16_04 Design feature cards & Pricing cards

### app/components/pricing/page.tsx

```


export default function Pricing() {
    return (
        <main className="min-h-screen bg-slate-100 text-center">
            <div className="p-10">
                <p className="text-center font-bold text-xl uppercase bg-linear-to-r from-blue-700 via-zinc-450 tracking-widest to-red-700 bg-clip-text text-transparent">Pricing</p>
                <h1 className="text-5xl font-bold text-center bg-linear-to-r from-blue-600 via-orange-500 to-red-900 bg-clip-text text-transparent">Simple Pricing for Everyone Here...</h1>
                <p className="text-lg p-5 text-gray-700">Choose the plan that works best for your business. Upgrade whenever you need more features.</p>
            </div>

            <div className="p-5 grid grid-cols-1 md:grid-cols-3 mx-20 rounded-2xl gap-7">
                <div className="bg-white rounded-2xl p-7 hover:-translate-y-3 hover:shadow-black hover:shadow-xl duration-300">
                    <h2 className="text-3xl font-bold p-3 text-left">Basic</h2>
                    <p className="text-md text-gray-700 text-left">For individuals getting started</p>
                    <div className="py-5 text-left">
                        <span className="font-bold text-2xl line-through">$11</span> <br />
                        <span className="font-bold text-4xl">$9</span>
                        <span className="text-xl text-gray-700">/Month</span>
                    </div>
                    <button className="text-blue-700 hover:text-white hover:bg-blue-700 duration-300 text-xl font-bold px-20 py-3 rounded-2xl border-2 border-black">Get Started</button>
                    <div className="leading-10 mt-5 text-left">
                        <ul>
                            <li>✓ 5 Projects</li>
                            <li>✓ 10 GB Storage</li>
                            <li>✓ Email Support</li>
                            <li>✓ Basic Analytics</li>
                        </ul>
                    </div>
                </div>
                {/* /// */}
                <div className="bg-white rounded-2xl p-7 hover:-translate-y-3 hover:shadow-black hover:shadow-xl duration-300">
                    <div className="top-4 -translate-y-12 rounded-full hover:bg-blue-900 duration-500 bg-blue-600 px-3 py-2 text-sm font-semibold text-white ">
                        Most Popular
                    </div>
                    <h2 className="text-3xl font-bold p-3 text-left">Pro</h2>
                    <p className="text-md text-gray-700 text-left">For growing businesses.</p>
                    <div className="py-5 text-left">
                        <span className="font-bold text-2xl line-through">$11</span> <br />
                        <span className="font-bold text-4xl">$9</span>
                        <span className="text-xl text-gray-700">/Month</span>
                    </div>
                    <button className="text-white hover:text-white duration-300 bg-blue-700 hover:bg-blue-800 text-xl font-bold px-20 py-3 rounded-2xl border-2 border-black">Get Started</button>
                    <div className="leading-10 mt-5 text-left">
                        <ul>
                            <li>✓ 5 Projects</li>
                            <li>✓ 10 GB Storage</li>
                            <li>✓ Email Support</li>
                            <li>✓ Basic Analytics</li>
                        </ul>
                    </div>
                </div>
                {/* /// */}
                <div className="bg-gray-900 text-white rounded-2xl border-2 border-black p-7 hover:-translate-y-3 hover:shadow-black hover:shadow-xl duration-300">
                    <h2 className="text-3xl font-bold p-3 text-left">Enterpirse</h2>
                    <p className="text-md text-cyan-200 text-left">For large teams and organizations.</p>
                    <div className="py-5 text-left">
                        <span className="font-bold text-2xl line-through">$11</span> <br />
                        <span className="font-bold text-4xl">$9</span>
                        <span className="text-xl text-gray-200">/Month</span>
                    </div>
                    <button className="text-black bg-white hover:text-black duration-300 hover:bg-blue-100 text-xl font-bold px-20 py-3 rounded-2xl border-2 border-black">Get Started</button>
                    <div className="leading-10 mt-5 text-left">
                        <ul>
                            <li>✓ 5 Projects</li>
                            <li>✓ 10 GB Storage</li>
                            <li>✓ Email Support</li>
                            <li>✓ Basic Analytics</li>
                        </ul>
                    </div>
                </div>



            </div>

        </main>
    );
}
```

---

## UI_16_05 Design pricing cards & Feature cards

### app/components/pricing/page.tsx

```
export default function Pricing() {
    return (
        <main className="min-h-screen bg-slate-100 text-center">
            <div className="p-10">
                <p className="text-center font-bold text-xl uppercase bg-linear-to-r from-blue-700 via-zinc-450 tracking-widest to-red-700 bg-clip-text text-transparent">Pricing</p>
                <h1 className="text-5xl font-bold text-center bg-linear-to-r from-blue-600 via-orange-500 to-red-900 bg-clip-text text-transparent">Simple Pricing for Everyone Here...</h1>
                <p className="text-lg p-5 text-gray-700">Choose the plan that works best for your business. Upgrade whenever you need more features.</p>
            </div>

            <div className="p-5 grid grid-cols-1 md:grid-cols-3 mx-20 rounded-2xl gap-7">
                <div className="bg-white rounded-2xl p-7 hover:-translate-y-3 hover:shadow-black hover:shadow-xl duration-300">
                    <h2 className="text-3xl font-bold p-3 text-left">Basic</h2>
                    <p className="text-md text-gray-700 text-left">For individuals getting started</p>
                    <div className="py-5 text-left">
                        <span className="font-bold text-2xl line-through">$11</span> <br />
                        <span className="font-bold text-4xl">$9</span>
                        <span className="text-xl text-gray-700">/Month</span>
                    </div>
                    <button className="text-blue-700 hover:text-white hover:bg-blue-700 duration-300 text-xl font-bold px-20 py-3 rounded-2xl border-2 border-black">Get Started</button>
                    <div className="leading-10 mt-5 text-left">
                        <ul>
                            <li>✓ 5 Projects</li>
                            <li>✓ 10 GB Storage</li>
                            <li>✓ Email Support</li>
                            <li>✓ Basic Analytics</li>
                        </ul>
                    </div>
                </div>
                {/* /// */}
                <div className="bg-white rounded-2xl p-7 hover:-translate-y-3 hover:shadow-black hover:shadow-xl duration-300">
                    <div className="top-4 -translate-y-12 rounded-full hover:bg-blue-900 duration-500 bg-blue-600 px-3 py-2 text-sm font-semibold text-white ">
                        Most Popular
                    </div>
                    <h2 className="text-3xl font-bold p-3 text-left">Pro</h2>
                    <p className="text-md text-gray-700 text-left">For growing businesses.</p>
                    <div className="py-5 text-left">
                        <span className="font-bold text-2xl line-through">$11</span> <br />
                        <span className="font-bold text-4xl">$9</span>
                        <span className="text-xl text-gray-700">/Month</span>
                    </div>
                    <button className="text-white hover:text-white duration-300 bg-blue-700 hover:bg-blue-800 text-xl font-bold px-20 py-3 rounded-2xl border-2 border-black">Get Started</button>
                    <div className="leading-10 mt-5 text-left">
                        <ul>
                            <li>✓ 5 Projects</li>
                            <li>✓ 10 GB Storage</li>
                            <li>✓ Email Support</li>
                            <li>✓ Basic Analytics</li>
                        </ul>
                    </div>
                </div>
                {/* /// */}
                <div className="bg-gray-900 text-white rounded-2xl border-2 border-black p-7 hover:-translate-y-3 hover:shadow-black hover:shadow-xl duration-300">
                    <h2 className="text-3xl font-bold p-3 text-left">Enterpirse</h2>
                    <p className="text-md text-cyan-200 text-left">For large teams and organizations.</p>
                    <div className="py-5 text-left">
                        <span className="font-bold text-2xl line-through">$11</span> <br />
                        <span className="font-bold text-4xl">$9</span>
                        <span className="text-xl text-gray-200">/Month</span>
                    </div>
                    <button className="text-black bg-white hover:text-black duration-300 hover:bg-blue-100 text-xl font-bold px-20 py-3 rounded-2xl border-2 border-black">Get Started</button>
                    <div className="leading-10 mt-5 text-left">
                        <ul>
                            <li>✓ 5 Projects</li>
                            <li>✓ 10 GB Storage</li>
                            <li>✓ Email Support</li>
                            <li>✓ Basic Analytics</li>
                        </ul>
                    </div>
                </div>



            </div>

        </main>
    );
}
```

---

## UI_16_06 Design testimonials

### app/components/navbar/page.tsx











<br/>
<br/>
<br/>
<br/>
<br/>

