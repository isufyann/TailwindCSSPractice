
# UI_08 Tailwind Background


```
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
