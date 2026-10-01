# page.tsx

```
import Image from "next/image";
import img_franchise_7205 from "@/public/img/img_franchise_7205.png"
import img_profile from "@/public/img/img_profile.png"
import DocumentationPage from "./components/DocumentationPage";
import Pricing from "./components/Pricing";
import Positioning from "./components/Positioning";
import Sidebar from "./components/SideBar";

export default function Home() {
  return (
    <main className="bg-linear-to-b from-gray-700 to-black h-screen">

      <nav className="flex fixed w-full top-0 z-10 items-center justify-between p-4 text-white bg-black shadow-2xl shadow-black">
        <div className="text-2xl font-bold">
          Logo Here
        </div>
        
        <div className="hidden md:flex gap-6 text-xl mx-7">
          <a href="#" className="font-bold hover:scale-90 duration-300 hover:bg-white hover:text-black rounded-2xl px-3 py-1 shadow-lg shadow-cyan-500 hover:shadow-sm">Home</a>
          <a href="#" className="font-bold hover:scale-90 duration-300 hover:bg-white hover:text-black rounded-2xl px-3 py-1 shadow-lg shadow-cyan-500 hover:shadow-sm">About</a>
          <a href="#" className="font-bold hover:scale-90 duration-300 hover:bg-white hover:text-black rounded-2xl px-3 py-1 shadow-lg shadow-cyan-500 hover:shadow-sm">Services</a>
          <a href="#" className="font-bold hover:scale-90 duration-300 hover:bg-white hover:text-black rounded-2xl px-3 py-1 shadow-lg shadow-cyan-500 hover:shadow-sm">Contact</a>
          <button className="bg-cyan-100 font-bold text-black px-4 rounded-lg hover:bg-blue-300">
            Login
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

      <DocumentationPage />
      <Pricing />
      <Positioning/>
      <Sidebar/>


      <br />
      <br />
      <br />
      <br />

    </main>
  );
}
```
