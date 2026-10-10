# Pricing Page
## components/pricing.tsx

  ```code


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
