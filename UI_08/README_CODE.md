
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
