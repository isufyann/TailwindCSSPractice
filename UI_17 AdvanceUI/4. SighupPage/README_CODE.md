# 4. Signup Page

```
Signup/SignupForm.tsx
Signup/SignupPage.tsx
Signup/WelcomePage.tsx
app/page.tsx
```

# SignupForm

```code
"use client";

import { useState, type FormEvent } from "react";
import Link from "next/link";

export default function SignupForm() {
  const [showPassword, setShowPassword] = useState(false);
  const [showConfirmPassword, setShowConfirmPassword] = useState(false);

  const [name, setName] = useState("");
  const [email, setEmail] = useState("");
  const [password, setPassword] = useState("");
  const [confirmPassword, setConfirmPassword] = useState("");
  const [acceptedTerms, setAcceptedTerms] = useState(false);
  const [error, setError] = useState("");

  function handleSubmit(event: FormEvent<HTMLFormElement>) {
    event.preventDefault();
    setError("");

    if (password.length < 8) {
      setError("Password must contain at least 8 characters.");
      return;
    }

    if (password !== confirmPassword) {
      setError("Passwords do not match.");
      return;
    }

    if (!acceptedTerms) {
      setError("Please accept the terms and conditions.");
      return;
    }

    // Connect your registration API here.
    console.log({ name, email, password });

    alert("Form validated! Connect your signup API next.");
  }

  const inputClass =
    "w-full rounded-xl border border-slate-200 bg-white px-4 py-3.5 text-sm text-slate-900 outline-none transition placeholder:text-slate-400 focus:border-blue-500 focus:ring-4 focus:ring-blue-500/10";

  return (
    <div className="w-full max-w-md">
      <div className="mb-7 flex items-center justify-between gap-3">
        <h2 className="text-3xl font-bold tracking-tight text-slate-900">
          Sign Up
        </h2>

        <p className="text-sm text-slate-500">
          Have an account?{" "}
          <Link
            href="/login"
            className="font-semibold text-blue-600 hover:text-blue-800"
          >
            Sign in
          </Link>
        </p>
      </div>

      <p className="mb-7 text-sm text-slate-500">
        Enter your details below to create your account.
      </p>

      <form onSubmit={handleSubmit} className="space-y-5">
        {/* Full name */}
        <div>
          <label
            htmlFor="name"
            className="mb-2 block text-sm font-semibold text-slate-700"
          >
            Full Name
          </label>

          <input
            id="name"
            type="text"
            autoComplete="name"
            placeholder="John Doe"
            value={name}
            onChange={(e) => setName(e.target.value)}
            required
            className={inputClass}
          />
        </div>

        {/* Email */}
        <div>
          <label
            htmlFor="email"
            className="mb-2 block text-sm font-semibold text-slate-700"
          >
            Email Address
          </label>

          <input
            id="email"
            type="email"
            autoComplete="email"
            placeholder="you@example.com"
            value={email}
            onChange={(e) => setEmail(e.target.value)}
            required
            className={inputClass}
          />
        </div>

        {/* Password */}
        <div>
          <label
            htmlFor="password"
            className="mb-2 block text-sm font-semibold text-slate-700"
          >
            Password
          </label>

          <div className="relative">
            <input
              id="password"
              type={showPassword ? "text" : "password"}
              autoComplete="new-password"
              placeholder="Create a strong password"
              value={password}
              onChange={(e) => setPassword(e.target.value)}
              required
              minLength={8}
              className={`${inputClass} pr-20`}
            />

            <button
              type="button"
              onClick={() => setShowPassword(!showPassword)}
              className="absolute right-4 top-1/2 -translate-y-1/2 text-sm font-semibold text-blue-600"
            >
              {showPassword ? "Hide" : "Show"}
            </button>
          </div>
        </div>

        {/* Confirm password */}
        <div>
          <label
            htmlFor="confirmPassword"
            className="mb-2 block text-sm font-semibold text-slate-700"
          >
            Confirm Password
          </label>

          <div className="relative">
            <input
              id="confirmPassword"
              type={showConfirmPassword ? "text" : "password"}
              autoComplete="new-password"
              placeholder="Confirm your password"
              value={confirmPassword}
              onChange={(e) => setConfirmPassword(e.target.value)}
              required
              className={`${inputClass} pr-20`}
            />

            <button
              type="button"
              onClick={() =>
                setShowConfirmPassword(!showConfirmPassword)
              }
              className="absolute right-4 top-1/2 -translate-y-1/2 text-sm font-semibold text-blue-600"
            >
              {showConfirmPassword ? "Hide" : "Show"}
            </button>
          </div>
        </div>

        {/* Terms */}
        <label className="flex items-start gap-3 text-sm leading-6 text-slate-600">
          <input
            type="checkbox"
            checked={acceptedTerms}
            onChange={(e) => setAcceptedTerms(e.target.checked)}
            className="mt-1 h-4 w-4 shrink-0 accent-blue-600"
          />

          <span>
            I agree to the{" "}
            <Link href="/terms" className="font-medium text-blue-600">
              Terms of Service
            </Link>{" "}
            and{" "}
            <Link href="/privacy" className="font-medium text-blue-600">
              Privacy Policy
            </Link>
            .
          </span>
        </label>

        {/* Validation message */}
        {error && (
          <p
            role="alert"
            className="rounded-lg bg-red-50 p-3 text-sm text-red-600"
          >
            {error}
          </p>
        )}

        {/* Submit */}
        <button
          type="submit"
          className="flex w-full items-center justify-center gap-2 rounded-xl bg-linear-to-r from-blue-600 to-indigo-600 px-5 py-3.5 font-semibold text-white shadow-lg shadow-blue-600/20 transition hover:-translate-y-0.5 hover:shadow-xl focus:outline-none focus:ring-4 focus:ring-blue-500/30"
        >
          Create Account
          <span aria-hidden="true">→</span>
        </button>
      </form>

      {/* Divider */}
      <div className="my-7 flex items-center gap-4">
        <div className="h-px flex-1 bg-slate-200" />
        <span className="text-sm text-slate-400">Or sign up with</span>
        <div className="h-px flex-1 bg-slate-200" />
      </div>

      {/* Social signup */}
      <div className="grid grid-cols-2 gap-3">
        <button
          type="button"
          className="rounded-xl border border-slate-200 px-3 py-3 text-sm font-semibold text-slate-700 transition hover:bg-slate-50"
        >
          Google
        </button>

        <button
          type="button"
          className="rounded-xl border border-slate-200 px-3 py-3 text-sm font-semibold text-slate-700 transition hover:bg-slate-50"
        >
          GitHub
        </button>
      </div>
    </div>
  );
}
```

### SignupPage.tsx

```code
import SignupForm from "./SignupForm";
import WelcomePanel from "./WelcomePanel";

export default function SignupPage() {
  return (
    <main className="flex min-h-screen items-center hover:scale-90 transition justify-center bg-slate-100 p-4 sm:p-8">
      <div className="grid w-full max-w-6xl overflow-hidden rounded-3xl bg-white shadow-2xl shadow-slate-300/40 md:grid-cols-2">
        <WelcomePanel />

        <section className="flex items-center justify-center px-6 py-10 sm:px-10 lg:px-14 lg:py-12">
          <SignupForm />
        </section>
      </div>
    </main>
  );
}
```

### WelcomePanel.tsx

```code
export default function WelcomePanel() {
    const features = [
        {
            icon: "⚡",
            title: "Build faster",
            description: "Get started with powerful tools.",
        },
        {
            icon: "👥",
            title: "Work together",
            description: "Collaborate with your team.",
        },
        {
            icon: "🛡️",
            title: "Stay secure",
            description: "Your data is always protected.",
        },
        {
            icon: "😀",
            title: "Happy Clients",
            description: "Reviews about our product",
        },
    ];

    return (
        <section className="relative hidden overflow-hidden bg-linear-to-br from-blue-950 via-blue-800 to-indigo-600 p-10 text-white md:flex md:flex-col md:justify-between lg:p-12">
            <div className="absolute -bottom-20 -right-20 h-80 w-80 rounded-full bg-blue-400/20 blur-3xl" />

            <div className="relative">
                <div className="flex items-center gap-3">
                    <div className="flex h-11 w-11 items-center justify-center rounded-xl bg-white text-2xl font-bold text-blue-700">
                        D
                    </div>

                    <span className="text-2xl font-bold">iSufyann Dev</span>
                </div>

                <h1 className="mt-20 text-4xl font-bold leading-tight lg:text-5xl">
                    Create Your
                    <br />
                    <span className="text-blue-300">Free Account.</span>
                </h1>

                <p className="mt-5 max-w-sm leading-7 text-blue-100">
                    Join DevFlow and start building your ideas today.
                </p>

                <div className="mt-10 space-y-7">
                    {features.map((feature) => (
                        <div key={feature.title} className="flex items-center gap-4">
                            <div className="flex h-12 w-12 shrink-0 items-center justify-center rounded-2xl bg-white/15 text-xl">
                                {feature.icon}
                            </div>

                            <div>
                                <h3 className="font-semibold">{feature.title}</h3>
                                <p className="mt-1 text-sm text-blue-100">
                                    {feature.description}
                                </p>
                            </div>
                        </div>
                    ))}
                </div>
            </div>

            <p className="relative mt-12 text-sm text-blue-200">
                Better tools. Better developers.
            </p>
        </section>
    );
}
```

### page.tsx

```code
import SignupPage from "./Signup/SignupPage";

export default function Home() {
  return (
    <div className="flex flex-col flex-1 items-center justify-center bg-zinc-50 font-sans dark:bg-black">
      <SignupPage/>
    </div>
  );
}
```

**End**
