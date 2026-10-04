
# UI_08 Tailwind Background

```code

export default function UI08() {
    return (
        <div className="relative min-h-screen">
            <div className="relative bg-[url('/img/img_profile2.png')] bg-cover h-300">
                <div className="absolute bg-black/70 inset-10 rounded-2xl p-20 space-y-5">
                    <p className="uppercase text-blue-700 text-xl">Next Mind Creation</p>
                    <h1 className="font-bold text-5xl text-white">Build the Future with AI</h1>
                    <p className="text-lg text-white max-w-1/2">Create intelligent applications using modern artificial intelligence and advanced technology.
                    </p>
                    <button className="bg-blue-700 px-5 py-3 rounded-2xl text-white font-bold">Get Started</button>
                </div>
            </div>
        </div>
    );
}
```



**GPT**
```code
export default function UI() {
  return (
    <div className="min-h-screen bg-slate-100">
      <section className="relative h-screen bg-[url('/img/img_profile2.png')] bg-cover bg-center">

        {/* Gradient Overlay */}
        <div className="absolute inset-0 bg-linear-to-r from-black/80 via-black/50 to-transparent"></div>

        {/* Content */}
        <div className="relative z-10 flex h-full items-center">

          <div className="max-w-2xl px-8 text-white">

            <p className="mb-4 text-blue-400 font-semibold">
              NEXT GENERATION TECHNOLOGY
            </p>

            <h1 className="text-5xl font-bold leading-tight">
              Build the Future with AI
            </h1>

            <p className="mt-5 text-lg text-gray-200">
              Create intelligent applications using modern
              artificial intelligence and advanced technology.
            </p>

            <button className="mt-8 rounded-lg bg-blue-600 px-6 py-3 font-semibold hover:bg-blue-700">
              Get Started
            </button>

          </div>

        </div>

      </section>

    </div>
  );
}
```

# state and interaction variants Like Focus, Hover, Active.

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
