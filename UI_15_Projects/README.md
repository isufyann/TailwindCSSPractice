# Create Designs of above learning.

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

            <hr className="my-10 border-gray-700 w-3/4 mx-auto" />

            <div className="flex flex-col items-center gap-5 bg-black p-15">
                <p className="text-blue-700 text-xl">Expertise</p>
                <h1 className="text-cyan-100 text-5xl font-bold tracking-widest">Technical Skills</h1>
                <div className="grid grid-cols-4 gap-5 p-20">
                    <div className="bg-mist-950 border border-cyan-700 gap-2 text-center text-white rounded-2xl p-3 text-xl hover:scale-115 duration-300">HTML</div>
                    <div className="bg-mist-950 border border-cyan-700 gap-2 text-center text-white rounded-2xl p-3 text-xl hover:scale-115 duration-300">CSS</div>
                    <div className="bg-mist-950 border border-cyan-700 gap-2 text-center text-white rounded-2xl p-3 text-xl hover:scale-115 duration-300">JavaScript</div>
                    <div className="bg-mist-950 border border-cyan-700 gap-2 text-center text-white rounded-2xl p-3 text-xl hover:scale-115 duration-300">TypeScript</div>
                    <div className="bg-mist-950 border border-cyan-700 gap-2 text-center text-white rounded-2xl p-3 text-xl hover:scale-115 duration-300">React</div>
                    <div className="bg-mist-950 border border-cyan-700 gap-2 text-center text-white rounded-2xl p-3 text-xl hover:scale-115 duration-300">Next.js</div>
                    <div className="bg-mist-950 border border-cyan-700 gap-2 text-center text-white rounded-2xl p-3 text-xl hover:scale-115 duration-300">Tailwind CSS</div>
                    <div className="bg-mist-950 border border-cyan-700 gap-2 text-center text-white rounded-2xl p-3 text-xl hover:scale-115 duration-300">REST API</div>
                    <div className="bg-mist-950 border border-cyan-700 gap-2 text-center text-white rounded-2xl p-3 text-xl hover:scale-115 duration-300">Git & GitHub</div>
                    <div className="bg-mist-950 border border-cyan-700 gap-2 text-center text-white rounded-2xl p-3 text-xl hover:scale-115 duration-300">Responsive Design</div>
                    <div className="bg-mist-950 border border-cyan-700 gap-2 text-center text-white rounded-2xl p-3 text-xl hover:scale-115 duration-300">State Management</div>
                    <div className="bg-mist-950 border border-cyan-700 gap-2 text-center text-white rounded-2xl p-3 text-xl hover:scale-115 duration-300">Vercel/Netlify</div>
                    <div className="bg-mist-950 border border-cyan-700 gap-2 text-center text-white rounded-2xl p-3 text-xl hover:scale-115 duration-300">Full Stack Dev</div>
                </div>
            </div>


            {/* Work Experience */}
            {/* Card left */}
            <div className="flex flex-col text-center bg-black p-10">
                <p className="text-blue-500 ">Career</p>
                <h1 className="text-white text-4xl font-bold tracking-widest">Work Experience</h1>
                <div className="grid grid-cols-2 gap-6 rounded-2xl p-10">
                    {/* Card 1 */}
                    <div className="bg-black rounded-2xl border-2 border-slate-700 p-5 hover:scale-105 duration-300">
                        {/* Top row */}
                        <div className="mb-6 flex items-center justify-between">
                            <span className="rounded-full px-4 py-1 text-sm font-medium text-sky-400">
                                2025 - Present
                            </span>
                            <span className="rounded-full px-4 py-1 text-sm font-medium text-sky-400">
                                Lahore, Pakistan.
                            </span>
                        </div>
                        <p className="mb-2 text-2xl font-bold text-left text-white">Frontend Developer (Intern → Junior)</p>
                        <div>
                            <ul className="flex flex-col text-left px-3 py-5 text-white list-disc leading-10">
                                <li>Developed and maintained multiple education-based web platforms</li>
                                <li>Converted UI designs into responsive React/Next.js applications</li>
                                <li>Integrated REST APIs and handled dynamic data rendering</li>
                                <li>Worked on production systems actively used by thousands of users</li>
                            </ul>
                        </div>
                    </div>

                    {/* Card Right */}
                    <div className="bg-black rounded-2xl border-2 border-slate-700 p-5 hover:scale-105 duration-300">
                        {/* Top row */}
                        <div className="mb-6 flex items-center justify-between">
                            <span className="rounded-full px-4 py-1 text-sm font-medium text-sky-400">
                                2025 - Present
                            </span>
                            <span className="rounded-full px-4 py-1 text-sm font-medium text-sky-400">
                                Lahore, Pakistan.
                            </span>
                        </div>
                        <p className="mb-2 text-2xl font-bold text-left text-white">Learner → Instructor & Freelancer</p>
                        <div>
                            <ul className="flex flex-col text-left px-3 py-5 text-white list-disc">
                                <li>Completed a 6-month intensive web development programme — HTML, CSS, JavaScript, and React</li>
                                <li>Progressed from student to Instructor, teaching frontend development to new learners</li>
                                <li>Awarded Best Instructor Certificate by Ehsas Lab for outstanding teaching contributions</li>
                                <li>Took on freelance client projects, building real-world web solutions independently</li>
                            </ul>
                        </div>
                    </div>
                </div>
                <hr className="my-1 border-gray-600 w-3/4 mx-auto" />
            </div>

            <div className="flex justify-center bg-black pt-3 pb-10">
                <button className="text-blue-700 rounded-2xl border border-blue-500 w-fit px-5 py-3 hover:scale-115 duration-300 hover:bg-mist-900 hover:text-white">View Full Experience</button>
            </div>


            <div className="grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-3 bg-black text-white">
                <div className="rounded-xl p-6 shadow-lg">
                    <h2 className="text-xl font-bold md:text-2xl">React</h2>
                    <p className="mt-3 text-sm md:text-base">Learn React for modern web applications.</p>
                    <button className="mt-5 rounded-lg bg-blue-500 px-4 py-2 text-white">Learn More</button>
                </div>
            </div>
            <hr className="border-blue-300"></hr>


            <div className="overflow-x-auto bg-black p-5">
                <div className="flex md:grid md:grid-cols-4 px-30 place-items-center">
                    <p className="text-white text-2xl font-bold p-3 border border-gray-400 rounded-2xl m-2">HTML</p>
                    <p className="text-white text-2xl font-bold p-3 border border-gray-400 rounded-2xl m-2">CSS</p>
                    <p className="text-white text-2xl font-bold p-3 border border-gray-400 rounded-2xl m-2">JavaScript</p>
                    <p className="text-white text-2xl font-bold p-3 border border-gray-400 rounded-2xl m-2">React</p>
                    <p className="text-white text-2xl font-bold p-3 border border-gray-400 rounded-2xl m-2">Next.js</p>
                    <p className="text-white text-2xl font-bold p-3 border border-gray-400 rounded-2xl m-2">Tailwind CSS</p>
                    <p className="text-white text-2xl font-bold p-3 border border-gray-400 rounded-2xl m-2">Machine Learning</p>
                    <p className="text-white text-2xl font-bold p-3 border border-gray-400 rounded-2xl m-2">AI</p>
                </div>
            </div>
            <hr className="border-blue-300"></hr>
            
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

Design Testimonials.

```code


export default function Testinomials() {
    return (
        <main>
            <div className="bg-blue-700 text-white text-center max-w-7xl mx-auto rounded-2xl px-10 py-5">
                <h1 className="text-6xl font-bold text-center pb-7">Testinomials</h1>
                <div className="grid grid-cols-2">
                    <div className="m-3 hover:-translate-y-3 active:scale-90 transition border-white/20 shadow-lg shadow-black border-2 p-10 rounded-2xl bg-white/20 backdrop-blur-md col-span-1">
                        <h1 className="text-3xl font-bold ">
                            Customer Comments
                        </h1>
                        <p>
                            Customer gives us good comments about our products after using our products.
                            Here are more good products into my profile and we are going to spread it in
                            the whole world.
                        </p>
                    </div>
                    <div className="m-3 hover:-translate-y-3 active:scale-90 transition border-white/20 shadow-lg shadow-black border-2 p-10 rounded-2xl bg-white/20 backdrop-blur-md col-span-1">
                        <h1 className="text-3xl font-bold ">
                            Customer Comments
                        </h1>
                        <p>
                            Customer gives us good comments about our products after using our products.
                            Here are more good products into my profile and we are going to spread it in
                            the whole world.
                        </p>
                    </div>

                    <div className="m-3 hover:-translate-y-3 active:scale-90 transition border-white/20 shadow-lg shadow-black border-2 p-10 rounded-2xl bg-white/20 backdrop-blur-md col-span-2">
                        <h1 className="text-3xl font-bold ">
                            Customer Comments
                        </h1>
                        <p>
                            Customer gives us good comments about our products after using our products.
                            Here are more good products into my profile and we are going to spread it in
                            the whole world.
                        </p>
                    </div>
                </div>

                {/* 2nd */}
                <div className="grid grid-cols-2 ">
                    <div className="m-3 hover:-translate-y-3 active:scale-90 transition border-white/20 shadow-lg shadow-black border-2 p-10 rounded-2xl bg-white/20 backdrop-blur-md col-span-1">
                        <h1 className="text-3xl font-bold ">
                            Customer Comments
                        </h1>
                        <p>
                            Customer gives us good comments about our products after using our products.
                            Here are more good products into my profile and we are going to spread it in
                            the whole world.
                        </p>
                    </div>
                    <div className="m-3 hover:-translate-y-3 active:scale-90 transition border-white/20 shadow-lg shadow-black border-2 p-10 rounded-2xl bg-white/20 backdrop-blur-md col-span-1">
                        <h1 className="text-3xl font-bold ">
                            Customer Comments
                        </h1>
                        <p>
                            Customer gives us good comments about our products after using our products.
                            Here are more good products into my profile and we are going to spread it in
                            the whole world.
                        </p>
                    </div>

                    <div className="m-3 hover:-translate-y-3 active:scale-90 transition border-white/20 shadow-lg shadow-black border-2 p-10 rounded-2xl bg-white/20 backdrop-blur-md col-span-2">
                        <h1 className="text-3xl font-bold ">
                            Customer Comments
                        </h1>
                        <p>
                            Customer gives us good comments about our products after using our products.
                            Here are more good products into my profile and we are going to spread it in
                            the whole world.
                        </p>
                    </div>
                </div>



            </div>
        </main>
    );
}
```

---

## UI_16_07 Design FAQs

### app/components/faqs/page.tsx

```code


export default function FAQs() {
    return (
        <main>
            <section className="bg-gray-200 py-20 mb-50">
                <div className="max-w-4xl px-6 mx-auto  text-center">
                    <div className="space-y-5">
                        <p className="text-blue-700 tet-sm">
                            FAQs
                        </p>
                        <h1 className="text-4xl font-black text-black">Frequently Asked Questions.
                        </h1>
                        <p className="text-gray-700 text-xl max-2xl">Find answers to some of the most common questions about our product and services.
                        </p>
                    </div>

                    {/* FAQs */}
                    <div className="max-w-xl mx-auto space-y-4 py-7">
                        <details className="text-left text-xl bg-white rounded-2xl px-7 py-2 group border-2 border-gray-300 hover:shadow-lg shadow-gray-700 shadow-lg hover:shadow-black">
                            <summary className="group">
                                How do I reset my Password?
                            </summary>
                            <p className="text-gray-500 text-lg px-7 py-3">
                                Here is trick to reset your password.
                            </p>
                        </details>
                        <details className="text-left text-xl bg-white rounded-2xl px-7 py-2 group border-2 border-gray-300 hover:shadow-lg shadow-gray-700 shadow-lg hover:shadow-black">
                            <summary className="group">
                                How do I reset my Password?
                            </summary>
                            <p className="text-gray-500 text-lg px-7 py-3">
                                Here is trick to reset your password.
                            </p>
                        </details>
                        <details className="text-left text-xl bg-white rounded-2xl px-7 py-2 group border-2 border-gray-300 hover:shadow-lg shadow-gray-700 shadow-lg hover:shadow-black">
                            <summary className="group">
                                How do I reset my Password?
                            </summary>
                            <p className="text-gray-500 text-lg px-7 py-3">
                                Here is trick to reset your password.
                            </p>
                        </details>


                    </div>
                </div>

            </section>

        </main>
    );
}
```

### Design FAQs using Map function.

### Below is GPT code

```code
GPT
export default function UI() {
  const faqs = [
    {
      question: "What is Tailwind CSS?",
      answer:
        "Tailwind CSS is a utility-first CSS framework that helps you build modern and responsive user interfaces quickly.",
    },
    {
      question: "Is Tailwind CSS free?",
      answer:
        "Yes. Tailwind CSS is an open-source framework that you can use in your projects.",
    },
    {
      question: "Can I use Tailwind CSS with React?",
      answer:
        "Yes. Tailwind CSS works very well with React, Next.js, Vue, and other modern frontend frameworks.",
    },
    {
      question: "Is Tailwind CSS responsive?",
      answer:
        "Yes. Tailwind provides responsive utilities such as sm, md, lg, xl, and 2xl.",
    },
  ];

  return (
    <section className="bg-gray-50 py-20">
      <div className="mx-auto max-w-4xl px-6">
        {/* Heading */}
        <div className="mb-12 text-center">
          <p className="mb-2 text-sm font-semibold uppercase tracking-wider text-blue-600">
            FAQ
          </p>

          <h2 className="text-3xl font-bold text-gray-900 sm:text-4xl">
            Frequently Asked Questions
          </h2>

          <p className="mx-auto mt-4 max-w-2xl text-gray-600">
            Find answers to some of the most common questions about our
            product and services.
          </p>
        </div>

        {/* FAQ List */}
        <div className="space-y-4">
          {faqs.map((faq, index) => (
            <details
              key={index}
              className="group rounded-xl border border-gray-200 bg-white p-6 shadow-sm"
            >
              <summary className="flex cursor-pointer list-none items-center justify-between font-semibold text-gray-900">
                {faq.question}

                <span className="ml-4 text-2xl text-gray-500 transition-transform duration-200 group-open:rotate-45">
                  +
                </span>
              </summary>

              <p className="mt-4 leading-7 text-gray-600">
                {faq.answer}
              </p>
            </details>
          ))}
        </div>
      </div>
    </section>
  );
}
```

---

## UI_16_08 Design CTA Section

### app/components/CTA/page.tsx

Design CTA.

```code
import Image from "next/image";
import img_profile from "@/public/img/img_profile.png"


export default function Positioning() {
    return (
        <main>


            <div className="relative h-screen w-full mt-20">
                <Image
                    src={img_profile}
                    alt="Image Profile"
                    className="h-fit w-full object-cover bg-black/30 inset-0"
                ></Image>
                <div className=" absolute hover:backdrop-blur-none hover:text-black backdrop-blur-md bg-black/10 hover:scale-80 transition duration-300 inset-50 text-white text-6xl font-bold text-center content-center rounded-3xl border border-white/50">
                    Professional Software Engineer
                </div>
            </div>
            


        </main>
    );
}
```

---

## UI_16_09 Design Footer

### app/components/Footer/page.tsx

```code
import { FaFacebook } from "react-icons/fa6";
import { FaInstagram } from "react-icons/fa";
import { BsTwitterX } from "react-icons/bs";



export default function Footer() {
    return (
        <main>
            <footer className="bg-gray-900 dark:bg-white dark:text-black text-gray-300 font-sans">

                <div className="max-w-7xl mx-auto px-4 pt-16 pb-5 sm:px-6 lg:px-8">
                    <div className="grid grid-cols-1 md:grid-cols-3 gap-8 pb-12 border-b border-gray-800">

                        <div className="md:col-span-1">
                            <span className="text-2xl font-bold text-white tracking-wide">Logo Here</span>
                            <p className="mt-4 text-sm text-gray-400 max-w-sm leading-relaxed">
                                Building the future of modern web development with scalable, sleek, and component-driven designs.
                            </p>
                        </div>

                        <div className="md:col-span-2 md:flex md:justify-end md:items-start">
                            <div className="w-full max-w-md">
                                <h3 className="text-sm font-semibold text-white uppercase tracking-wider">Subscribe to our newsletter</h3>
                                <p className="mt-2 text-sm text-gray-400">The latest news, articles, and resources, sent to your inbox weekly.</p>
                                <form className="mt-4 sm:flex gap-3">
                                    <input type="email" required placeholder="Enter your email" className="w-full px-4 py-2.5 text-base text-gray-900 placeholder-gray-500 bg-white border border-transparent rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500" />
                                    <button type="submit" className="mt-3 sm:mt-0 w-full sm:w-auto flex items-center justify-center px-5 py-2.5 border border-transparent text-base font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 transition-colors">
                                        Subscribe
                                    </button>
                                </form>
                            </div>
                        </div>
                    </div>


                    <div className="grid grid-cols-2 sm:grid-cols-2 md:grid-cols-4 gap-8 py-5">
                        <div>
                            <h4 className="text-sm font-semibold text-white uppercase tracking-wider">Solutions</h4>
                            <ul className="mt-4 space-y-2">
                                <li><a href="#" className="text-sm hover:text-white transition-colors">Marketing</a></li>
                                <li><a href="#" className="text-sm hover:text-white transition-colors">Analytics</a></li>
                                <li><a href="#" className="text-sm hover:text-white transition-colors">Commerce</a></li>
                                <li><a href="#" className="text-sm hover:text-white transition-colors">Insights</a></li>
                            </ul>
                        </div>
                        <div>
                            <h4 className="text-sm font-semibold text-white uppercase tracking-wider">Support</h4>
                            <ul className="mt-4 space-y-2">
                                <li><a href="#" className="text-sm hover:text-white transition-colors">Pricing</a></li>
                                <li><a href="#" className="text-sm hover:text-white transition-colors">Documentation</a></li>
                                <li><a href="#" className="text-sm hover:text-white transition-colors">Guides</a></li>
                                <li><a href="#" className="text-sm hover:text-white transition-colors">API Status</a></li>
                            </ul>
                        </div>
                        <div>
                            <h4 className="text-sm font-semibold text-white uppercase tracking-wider">Company</h4>
                            <ul className="mt-4 space-y-2">
                                <li><a href="#" className="text-sm hover:text-white transition-colors">About Us</a></li>
                                <li><a href="#" className="text-sm hover:text-white transition-colors">Blog</a></li>
                                <li><a href="#" className="text-sm hover:text-white transition-colors">Jobs</a></li>
                                <li><a href="#" className="text-sm hover:text-white transition-colors">Press</a></li>
                            </ul>
                        </div>
                        <div>
                            <h4 className="text-sm font-semibold text-white uppercase tracking-wider">Legal</h4>
                            <ul className="mt-4 space-y-2">
                                <li><a href="#" className="text-sm hover:text-white transition-colors">Claim</a></li>
                                <li><a href="#" className="text-sm hover:text-white transition-colors">Privacy Policy</a></li>
                                <li><a href="#" className="text-sm hover:text-white transition-colors">Terms of Service</a></li>
                            </ul>
                        </div>
                    </div>


                    <div className="pt-2 border-t border-gray-800 flex flex-col-reverse sm:flex-row sm:items-center sm:justify-between gap-4">
                        <p className="text-sm text-gray-400">&copy; 2026 @isufyann Inc. All rights reserved.</p>

                        <div className="flex space-x-6 text-2xl">
                            <a href="#" className="text-gray-400 hover:text-white transition-colors">
                                <FaFacebook /></a>
                            <a href="#" className="text-gray-400 hover:text-white transition-colors">
                                <FaInstagram /></a>
                            <a href="#" className="text-gray-400 hover:text-white transition-colors">
                                <BsTwitterX /></a>
                        </div>
                    </div>
                </div>
            </footer>

        </main>
    );
}
```

---

## UI_16_09 Design dashboard

### app/components/?/page.tsx

```
Working on it.
```

---

## UI_16_11 Design Sidebar

### app/components/Sidebar/page.tsx

```code


export default function Sidebar() {
    return (
        <div className="min-h-screen mt-5">
            <div className="grid grid-cols-4">
                <aside className="col-span-1 bg-slate-100 mx-3 rounded-2xl p-3 text-center">

                    <div className="sticky top-40">
                        <h2 className="m-2 border font-bold bg-blue-700 p-3 text-white rounded-2xl">One</h2>
                        <h2 className="m-2 border font-bold bg-white p-3 text-black rounded-2xl">One</h2>
                        <ul className="mt-4 space-y-2 text-sm bg-amber-100 rounded-2xl px-8 py-3 mx-10 font-bold text-left list-disc">
                            <li>Introduction</li>
                            <li>Installation</li>
                            <li>Components</li>
                            <li>Examples</li>
                        </ul>
                    </div>
                </aside>

                <article className="p-3 space-y-2 col-span-3 bg-blue-100 rounded-2xl">
                    <h1 className="text-5xl font-bold text-center pt-5 uppercase bg-linear-to-r from-blue-900 via-yellow-400 to-red-900 bg-clip-text text-transparent">Article publish here</h1>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                </article>
            </div>

            {/* 2nd article will be here */}


            <div className="grid grid-cols-4">
                <aside className="col-span-1 bg-slate-100 mx-3 rounded-2xl p-3 text-center">

                    <div className="sticky top-40">
                        <h2 className="m-2 border font-bold bg-blue-700 p-3 text-white rounded-2xl">Two</h2>
                        <h2 className="m-2 border font-bold bg-white p-3 text-black rounded-2xl">Two</h2>
                        <ul className="mt-4 space-y-2 text-sm bg-amber-100 rounded-2xl px-8 py-3 mx-10 font-bold text-left list-disc">
                            <li>Introduction</li>
                            <li>Installation</li>
                            <li>Components</li>
                            <li>Examples</li>
                        </ul>
                    </div>
                </aside>

                <article className="p-3 space-y-2 col-span-3 bg-blue-100 rounded-2xl">
                    <h1 className="text-5xl font-bold text-center pt-5 uppercase bg-linear-to-r from-blue-900 via-yellow-400 to-red-900 bg-clip-text text-transparent">Article publish here again</h1>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                </article>
            </div>


            <div className="grid grid-cols-4">
                <aside className="col-span-1 bg-slate-100 mx-3 rounded-2xl p-3 text-center">

                    <div className="sticky top-40">
                        <h2 className="m-2 border font-bold bg-blue-700 p-3 text-white rounded-2xl">Three</h2>
                        <h2 className="m-2 border font-bold bg-white p-3 text-black rounded-2xl">Three</h2>
                        <ul className="mt-4 space-y-2 text-sm bg-amber-100 rounded-2xl px-8 py-3 mx-10 font-bold text-left list-disc">
                            <li>Introduction</li>
                            <li>Installation</li>
                            <li>Components</li>
                            <li>Examples</li>
                        </ul>
                    </div>
                </aside>

                <article className="p-3 space-y-2 col-span-3 bg-blue-100 rounded-2xl">
                    <h1 className="text-5xl font-bold text-center pt-5 uppercase bg-linear-to-r from-blue-900 via-yellow-400 to-red-900 bg-clip-text text-transparent">Article publish here</h1>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                </article>
            </div>


            <div className="grid grid-cols-4">
                <aside className="col-span-1 bg-slate-100 mx-3 rounded-2xl p-3 text-center">

                    <div className="sticky top-40">
                        <h2 className="m-2 border font-bold bg-blue-700 p-3 text-white rounded-2xl">Four</h2>
                        <h2 className="m-2 border font-bold bg-white p-3 text-black rounded-2xl">Four</h2>
                        <ul className="mt-4 space-y-2 text-sm bg-amber-100 rounded-2xl px-8 py-3 mx-10 font-bold text-left list-disc">
                            <li>Introduction</li>
                            <li>Installation</li>
                            <li>Components</li>
                            <li>Examples</li>
                        </ul>
                    </div>
                </aside>

                <article className="p-3 space-y-2 col-span-3 bg-blue-100 rounded-2xl">
                    <h1 className="text-5xl font-bold text-center pt-5 uppercase bg-linear-to-r from-blue-900 via-yellow-400 to-red-900 bg-clip-text text-transparent">Article publish here again</h1>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                    <div className="mx-5 my-10 space-y-5">
                        <h1 className="font-bold text-xl">Artile will be below</h1>
                        <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets. It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised thanks to these sheets and more recently with desktop publishing software like Aldus PageMaker and Microsoft Word including versions of Lorem Ipsum</p>
                        <p>Long article will be here. Once upan a time there was crow.</p>
                        <p>Long article will be here</p>
                        <p>Long article will be here</p>
                    </div>
                </article>
            </div>
            {/* End here */}




        </div>
    );

}
```

---

## UI_16_12 Design Data Table

### app/components/?/page.tsx

```
Working on it
```

---

## UI_16_13 Design Notification Panel

### app/Navbar (in main) /page.tsx

```
                    <div className="relative hover:scale-120 duration-300">
                        <button className="text-2xl bg-gray-800 rounded-xl">🔔</button>
                        <span className="absolute h-3 w-3 text-xs text-white -top-1 -right-1 flex items-center justify-center rounded-2xl">7</span>
                    </div>
```

---


## UI_16_14 Design Profile Page

### I designed whole profile page.

```
All the code is uploaded on GitHub step by step.
```

---

## UI_16_15 Design Setting Page

### Still learning.

```
Setting page still learning.
```

---

## UI_16_16 Design Authentication Page

### Still learning.

```
Setting page still learning.
```

---



<br/>
<br/>
<br/>
<br/>
<br/>

