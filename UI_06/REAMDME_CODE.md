## Page.tsx file

```
import Image from "next/image";
import img_franchise_7205 from "@/public/img/img_franchise_7205.png"
import img_profile from "@/public/img/img_profile.png"
import DocumentationPage from "./components/DocumentationPage";
import Pricing from "./components/Pricing";

export default function Home() {
  return (
    <main className="bg-linear-to-b from-gray-700 to-black h-screen">

      <nav className="flex items-center justify-between p-4 text-white bg-black">
        <div className="text-2xl font-bold">
          Logo Here
        </div>
          <div className="hidden md:flex gap-6 text-xl mx-7">
            <a href="#" className="font-bold hover:scale-110 duration-300 hover:bg-white hover:text-black rounded-2xl px-3 py-1 shadow-lg shadow-cyan-500 hover:shadow-sm">Home</a>
            <a href="#" className="font-bold hover:scale-110 duration-300 hover:bg-white hover:text-black rounded-2xl px-3 py-1 shadow-lg shadow-cyan-500 hover:shadow-sm">About</a>
            <a href="#" className="font-bold hover:scale-110 duration-300 hover:bg-white hover:text-black rounded-2xl px-3 py-1 shadow-lg shadow-cyan-500 hover:shadow-sm">Services</a>
            <a href="#" className="font-bold hover:scale-110 duration-300 hover:bg-white hover:text-black rounded-2xl px-3 py-1 shadow-lg shadow-cyan-500 hover:shadow-sm">Contact</a>
            <button  className="bg-cyan-100 font-bold text-black px-4 rounded-lg hover:bg-blue-300">
              Login
            </button>
        </div>
        <button className="text-2xl text-white block md:hidden">
          ☰
        </button>

      </nav>

      <div>
        <h1 className="text-5xl text-blue-200 text-center p-3 font-bold ">My Profile</h1>
        <div className="flex justify-center items-center p-3">
          <Image className="rounded-4xl hover:scale-110 duration-300 shadow-2xl shadow-gray-400" src={img_profile} alt="Franchise Pic" width={200} height={100}></Image>
        </div>
        <h2 className=" font-bold text-5xl uppercase tracking-widest text-center p-3 font-sans bg-linear-to-r from-blue-900 via-cyan-100 to-red-900 bg-clip-text text-transparent">Muhammad Sufyan </h2>
        <p className="text-white font-bold text-xl text-center">Software Engineers</p>
        <p className="text-white font-semibold text-xl text-center pb-3">Learning AI Agents from MCASCE</p>
      </div>

      <div className="flex flex-wrap justify-center space-x-15 bg-linear-to-b from-gray-800 to-black py-5">
        <div className="bg-black text-white p-4 text-center rounded-2xl hover:scale-115 duration-300 border-b-2 border-white">13+ Projects<br /><span className="text-gray-400 text-sm">Projects</span></div>
        <div className="bg-black text-white p-4 text-center rounded-2xl scale-120 hover:scale-135 duration-300 border-b-2 border-white">10+ Technologies<br /><span className="text-gray-400 text-sm">Technologies</span></div>
        <div className="bg-black text-white p-4 text-center rounded-2xl hover:scale-115 duration-300 border-b-2 border-white">2+ Years <br /><span className="text-gray-400 text-sm">Experience</span>
        </div>
      </div>

      {/* <div className="flex items-center justify-center h-48 bg-gray-100">
        <div className="p-4 bg-blue-500 text-white rounded">Centered Box</div>
        </div> */}
      {/* <hr/> */}

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
      <hr />

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
      </div>
      <hr />

      <div className="flex justify-center bg-black pt-3 pb-10">
        <button className="text-blue-700 rounded-2xl border border-blue-500 w-fit px-5 py-3 hover:scale-115 duration-300 hover:bg-mist-900 hover:text-white">View Full Experience</button>
      </div>
      <hr className="border-blue-300"></hr>


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

      <section className="px-4 py-12 md:px-8 md:py-20 lg:px-16 lg:py-24 bg-black text-white">
        <div className="mx-auto flex max-w-7xl flex-col items-center gap-10 lg:flex lg:flex-row">
          <div className="text-center lg:w-1/2 lg:text-left">
            <h1 className="text-4xl font-bold md:text-5xl lg:text-6xl">Build Modern Websites</h1>
            <p className="mt-5 text-base leading-7 md:text-lg">Create beautiful and responsive websites with modern technologies.</p>
            <button className="mt-6 rounded-lg bg-blue-600 px-6 py-3 text-white hover:bg-white hover:text-black hover:scale-115 duration-300">
              Get Started
            </button>
            <button className="mt-6 rounded-lg bg-blue-900 px-6 py-3 mx-5 hover:bg-white hover:text-black hover:scale-115 duration-300">
              Learn More
            </button>
          </div>
          <div className="w-full lg:w-1/2 lg:items-center justify-center flex lg:max-w-sm">
            <Image src={img_profile} alt="Profile Image" className="bg-blue-700/30 rounded-2xl hover:scale-115 duration-300"></Image>
          </div>
        </div>
      </section>

      <DocumentationPage/>

        <Pricing/>

    </main>
  );
}
```

## Components/DocumentationPage.tsx

```



export default function DocumentationPage() {
    return (
        <div className="min-h-screen bg-gray-50 text-gray-800">
            <main className="mx-auto max-w-4xl px-6 py-12">
                {/* Header */}
                <header className="mb-12 border-b border-gray-200 pb-8">
                    <p className="text-blue-700 p-5 ">
                        Documentation
                    </p>
                    <h1 className="text-5xl font-bold bg-linear-to-r from-blue-600 via-rose-700 to-orange-700 bg-clip-text text-transparent">
                        Get Started with GitHub
                    </h1>
                    <p className="mt-4 text-lg leading-8 text-gray-600">
                        Learn the fundamentals of Tailwind CSS and build modern, interactive
                        user interfaces using reusable Website.
                    </p>
                </header>

                <section className="">
                    <h2 className="text-2xl font-bold py-5">
                        Introduction
                    </h2>
                    <div className=" tracking-widest leading-7">
                        <p className="my-3">React is a JavaScript library for building user interfaces. It allows developers to create reusable components and manage application state efficiently.
                        </p>
                        <p className="my-3">React is commonly used with modern frameworks such as Next.js to build complete web applications.
                        </p>
                    </div>
                </section>
                <section className="">
                    <h2 className="text-2xl font-bold mt-15 mb-5 text-gray-900">
                        Prerequisites
                    </h2>
                    <p className="mb-4 leading-7 text-gray-600">
                        Before learning React, you should have a basic understanding of:
                    </p>
                    <ul className="list-disc space-y-2 text-gray-600">
                        <li>HTML and CSS</li>
                        <li>JavaScript fundamentals</li>
                        <li>Functions and objects</li>
                        <li>Arrays and array methods</li>
                        <li>ES6 features</li>
                    </ul>
                </section>
                <section>
                    <h2 className="text-3xl font-bold mt-15">
                        Create a React Project
                    </h2>
                    <p className="py-5">You can create a React project using a modern development tool such as Vite.</p>
                    <div className="bg-gray-900 rounded-lg ">
                        <div className="border-b border-gray-700 px-4 py-2 text-sm text-gray-400">
                            Terminal
                        </div>
                        <pre className="text-white text-sm p-3 overflow-x-auto leading-6">
                            <code>
                                {`    npm create next@latest my-app
    cd my-app
    npm install
    npn run dev`}
                            </code>
                        </pre>
                    </div>
                </section>

                <section>
                    <h2 className="text-3xl font-bold mt-15">
                        Creating a Component
                    </h2>
                    <p className="py-5">
                        A React component is a reusable piece of UI. Components can contain HTML-like JSX, JavaScript logic, and styling.
                    </p>
                    <div className="bg-gray-900 rounded-lg ">
                        <div className="border-b border-gray-700 px-4 py-2 text-sm text-gray-400">
                            App.tsx
                        </div>
                        <pre className="text-white text-sm p-3 overflow-x-auto leading-6">
                            <code>
                                {`function Welcome() {
  return (
    <div>
      <h1>Hello React</h1>
      <p>Welcome to my application.</p>
    </div>
  );
}

export default Welcome;
    npm install
    npn run dev`}
                            </code>
                        </pre>
                    </div>
                </section>

                <section>
                    <h2 className="text-3xl font-bold mt-15">Best Practice</h2>
                    <ol className="list-decimal space-y-2 m-3">
                        <li>Keep components small and reusable.</li>
                        <li>Use meaningful names for variables and components.</li>
                        <li>Avoid unnecessary duplication of code.</li>
                        <li>Keep your project structure organized.</li>
                        <li>Write clean and readable code.</li>
                    </ol>

                    <h2 className="text-3xl font-bold mt-15">Conclusion</h2>
                    <p className="p-3 text-gray-600 leading-7">React provides a powerful component-based approach for building modern web interfaces. Once you understand components, props, state, and events, you can start building more complex applications.
                    </p>
                </section>


            </main>
        </div>
    );
}

```
## components/Pricing.tsx

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

[Image for reference]()
