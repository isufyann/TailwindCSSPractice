# UI_09
## state and interaction variants Like Focus, Hover, Active.


```code
export default function UI08() {
    return (
        <div className="relative min-h-screen">
            <div className="relative bg-[url('/img/img_profile2.png')] bg-cover h-300">
                <div className="absolute bg-black/70 inset-10 rounded-2xl p-20 space-y-5">
                    <p className="uppercase text-blue-700 text-xl">Next Mind Creation</p>
                    <p className="text-white text-xs">1914 translation by H. Rackham</p>
                    <h1 className="font-bold text-5xl text-white">Build the Future with AI</h1>
                    <p className="text-lg text-white max-w-1/2">Create intelligent applications using modern artificial intelligence and advanced technology.
                    </p>
                    <button className="bg-blue-700 px-5 py-3 rounded-2xl text-white font-bold">Get Started</button>
                    <p className="text-xl text-white max-w-1/2 mt-10">Still using old method to learn programming.</p>
                    <p className="text-white text-lg w-3/4 leading-loose">"But I must explain to you how all this mistaken idea of denouncing pleasure and praising pain was born and I will give you a complete account of the system, and expound the actual teachings of the great explorer of the truth, the master-builder of human happiness. No one rejects, dislikes, or avoids pleasure itself, because it is pleasure, but because those who do not know how to pursue pleasure rationally encounter consequences that are extremely painful. Nor again is there anyone who loves or pursues or desires to obtain pain of itself, because it is pain, but because occasionally circumstances occur in which toil and pain can procure him some great pleasure. To take a trivial example, which of us ever undertakes laborious physical exercise, except to obtain some advantage from it? But who has any right to find fault with a man who chooses to enjoy a pleasure that has no annoying consequences, or one who avoids a pain that produces no resultant pleasure?"
                    </p>

                    <div>
                        <input
                        type="name"
                        className="text-white border hover:bg-red-500/30 focus:outline-none rounded-lg hover:shadow-lg transition hover:shadow-amber-300"/>
                    <button className="bg-blue-700 text-white rounded-2xl px-3 py-2 mx-3">
                        Click Here
                    </button>
                    </div>

                    <div className="group rounded-2xl border-2 p-6 hover:shadow-2xl transition shadow-amber-300">
                        <h2 className="text-xl font-bold group-hover:text-blue-600">Login Card</h2>
                        <p className="text-gray-700">Hover over the card</p>
                    </div>

                </div>
            </div>
        </div>
    );
}
```


# UI_09
## Beautiful login page.

```
export default function UI09() {
    return (

        <main className="bg-gray-100 min-h-screen justify-center items-center flex">
            <div className="w-full max-w-md bg-white px-3 py-5 rounded-2xl">
                <div className="text-center">
                    <h1 className="text-4xl font-bold p-3">Welcome Back</h1>
                    <p className="text-gray-500">Login to your Account</p>
                </div>
                <form className="">
                    <div className="flex flex-col px-5 py-5">
                        <label className="text-gray-700 py-1 text-sm">
                            Email
                        </label>
                        <input
                            type="email"
                            placeholder="isufyann@gmail.com"
                            className="px-3 py-3 border border-gray-700 rounded-xl" />
                        <label className="text-gray-700 py-1 pt-7 text-sm">
                            Email
                        </label>
                        <input
                            type="password"
                            placeholder="••••••••"
                            className="px-3 py-3 border border-gray-700 rounded-xl" />
                    </div>

                    <div className="flex text-center justify-between px-5">
                        <label>
                            <input type="checkbox"
                                className="text-xl h-4 w-5" >
                            </input>
                            <span className="px-3 items-center">Remember Me</span>
                        </label>
                        <a href="#" className="text-blue-700 text-sm">Forgot Password</a>
                    </div>
                </form>
                <button className="bg-blue-600 w-full px-3 py-3 my-5 rounded-2xl text-white font-bold text-lg hover:bg-blue-700">Login</button>
                <div className="flex justify-center text-sm">
                    <p className="text-gray-600">Don't have an account? <a href="#" className="text-blue-700">Create Account</a></p>
                </div>
            </div>

        </main>
    );
}
```
