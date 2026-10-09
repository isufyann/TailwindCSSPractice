# 2. Blog website

## Navbar.tsx

```app/components/Navbar.tsx```

```code
"use client";

import { useState } from "react";

export default function Navbar() {
    const [open, setOpen] = useState(false);

    return (
        <nav className="border-b border-gray-200 bg-white">
            <div className="mx-auto flex max-w-7xl items-center justify-between px-6 py-4">

                {/* Logo */}
                <a href="/" className="text-2xl font-bold text-blue-600">
                    DevBlog
                </a>

                {/* Desktop Menu */}
                <div className="hidden items-center gap-8 md:flex">
                    <a href="/" className="text-gray-700 hover:text-blue-600">
                        Home
                    </a>

                    <a href="/blog" className="text-gray-700 hover:text-blue-600">
                        Blog
                    </a>

                    <a href="#" className="text-gray-700 hover:text-blue-600">
                        About
                    </a>

                    <a href="#" className="text-gray-700 hover:text-blue-600">
                        Contact
                    </a>

                    <button className="rounded-lg bg-blue-600 px-5 py-2 text-white hover:bg-blue-700">
                        Subscribe
                    </button>
                </div>

                {/* Mobile Button */}
                <button
                    onClick={() => setOpen(!open)}
                    className="text-2xl md:hidden"
                >
                    ☰
                </button>
            </div>

            {/* Mobile Menu */}
            {open && (
                <div className="border-t border-gray-200 px-6 py-4 md:hidden">
                    <div className="flex flex-col gap-4">
                        <a href="/" className="text-gray-700">
                            Home
                        </a>

                        <a href="/blog" className="text-gray-700">
                            Blog
                        </a>

                        <a href="#" className="text-gray-700">
                            About
                        </a>

                        <a href="#" className="text-gray-700">
                            Contact
                        </a>

                        <button className="rounded-lg bg-blue-600 px-5 py-2 text-white">
                            Subscribe
                        </button>
                    </div>
                </div>
            )}
        </nav>
    );
}
```

---

## BlogCard Component

```components/BlogCard.tsx```

```code
import type { Blog } from "@/app/data/blog";

type BlogCardProps = {
  blog: Blog;
};

export default function BlogCard({ blog }: BlogCardProps) {
  return (
    <article className="rounded-xl border border-gray-200 bg-white p-6 shadow-sm transition hover:-translate-y-1 hover:shadow-lg">
      <span className="text-sm font-semibold text-blue-600">
        {blog.category}
      </span>

      <h2 className="mt-3 text-xl font-bold text-gray-900">
        {blog.title}
      </h2>

      <p className="mt-3 leading-7 text-gray-600">
        {blog.description}
      </p>

      <div className="mt-6 flex items-center justify-between border-t pt-4">
        <span className="text-sm text-gray-500">
          By {blog.author}
        </span>

        <button
          type="button"
          className="font-semibold text-blue-600 hover:text-blue-800"
        >
          Read More →
        </button>
      </div>
    </article>
  );
}
```

---

## BlogCard Component

```components/Footer.tsx```

```code
export default function Footer() {
  return (
    <footer
      id="about"
      className="mt-16 bg-gray-900 px-6 py-8 text-center text-white"
    >
      <h2 className="text-xl font-bold">DevBlog</h2>

      <p className="mt-2 text-sm text-gray-400">
        Learn React, Next.js, and modern web development.
      </p>

      <p className="mt-5 text-sm text-gray-500">
        © 2026 DevBlog. All rights reserved.
      </p>
    </footer>
  );
}
```

---

## Main Page

```code
import Navbar from "./components/Navbar";
import BlogCard from "./components/BlogCard";
import { blogs } from "@/app/data/blog";
import Footer from "./components/Footer";

export default function HomePage() {
  return (
    <>
      <Navbar />

      <main>
        {/* Hero Section */}
        <section className="bg-blue-50 px-6 py-20 text-center">
          <h1 className="text-4xl font-bold text-gray-900 sm:text-5xl">
            Welcome to DevBlog
          </h1>

          <p className="mx-auto mt-5 max-w-2xl text-lg leading-8 text-gray-600">
            Explore tutorials, learn new technologies, and improve
            your web development skills.
          </p>

          <a
            href="#blogs"
            className="mt-8 inline-block rounded-lg bg-blue-600 px-6 py-3 font-semibold text-white transition hover:bg-blue-700"
          >
            Explore Blogs
          </a>
        </section>

        {/* Blog Section */}
        <section id="blogs" className="mx-auto max-w-6xl px-6 py-16">
          <div className="mb-10">
            <h2 className="text-3xl font-bold text-gray-900">
              Latest Blogs
            </h2>

            <p className="mt-2 text-gray-600">
              Learn something new today.
            </p>
          </div>

          <div className="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
            {blogs.map((blog) => (
              <BlogCard key={blog.id} blog={blog} />
            ))}
          </div>
        </section>
      </main>

      <Footer />
    </>
  );
}
```

---

## Blog Data

```app/data/blog.tsx```

```code
export type Blog = {
  id: number;
  title: string;
  description: string;
  category: string;
  author: string;
};

export const blogs: Blog[] = [
  {
    id: 1,
    title: "Getting Started with React",
    description:
      "Learn React components, props, state, and how to build interactive websites.",
    category: "React",
    author: "Ali",
  },
  {
    id: 2,
    title: "Introduction to Next.js",
    description:
      "Discover the Next.js App Router, layouts, pages, and routing.",
    category: "Next.js",
    author: "Ahmed",
  },
  {
    id: 3,
    title: "Learn Tailwind CSS",
    description:
      "Build beautiful and responsive user interfaces using utility classes.",
    category: "Tailwind CSS",
    author: "Usman",
  },
  {
    id: 4,
    title: "Learn Tailwind CSS",
    description:
      "Build beautiful and responsive user interfaces using utility classes.",
    category: "Tailwind CSS",
    author: "Usman",
  },
  {
    id: 5,
    title: "Learn Tailwind CSS",
    description:
      "Build beautiful and responsive user interfaces using utility classes.",
    category: "Tailwind CSS",
    author: "Usman",
  },
  {
    id: 6,
    title: "Learn Tailwind CSS",
    description:
      "Build beautiful and responsive user interfaces using utility classes.",
    category: "Tailwind CSS",
    author: "Usman",
  },
];
```

---





