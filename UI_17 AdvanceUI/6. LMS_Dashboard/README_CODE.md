# LMS dashboard

## Folder Structure

```
my-app/
├── app/
│   ├── layout.tsx
│   ├── page.tsx
│   └── globals.css
├── components/
│   ├── Sidebar.tsx
│   ├── Topbar.tsx
│   ├── StatCard.tsx
│   ├── CourseCard.tsx
│   ├── DeadlinePanel.tsx
│   └── Dashboard.tsx
└── data/
    └── courses.ts
```

## Course data (Dummy data)

```my-app/data/courses.ts```

```code
export type Course = {
  id: number;
  title: string;
  instructor: string;
  category: string;
  progress: number;
  lessons: string;
  hours: string;
  gradient: string;
  icon: string;
};

export const courses: Course[] = [
  {
    id: 1,
    title: "React Fundamentals",
    instructor: "John Doe",
    category: "React",
    progress: 60,
    lessons: "8/12 lessons",
    hours: "4.5 hrs",
    gradient: "from-cyan-500 to-blue-800",
    icon: "⚛",
  },
  {
    id: 2,
    title: "Next.js App Router",
    instructor: "Sarah Khan",
    category: "Next.js",
    progress: 40,
    lessons: "6/15 lessons",
    hours: "5.2 hrs",
    gradient: "from-slate-700 to-black",
    icon: "N.",
  },
  {
    id: 3,
    title: "Tailwind CSS Mastery",
    instructor: "Alex Carter",
    category: "Tailwind",
    progress: 0,
    lessons: "0/18 lessons",
    hours: "6.0 hrs",
    gradient: "from-cyan-500 to-indigo-900",
    icon: "≈",
  },
];

export const recentCourses = [
  {
    id: 1,
    title: "JavaScript ES6+",
    instructor: "Maria Garcia",
    status: "Completed",
    hours: "8.5 hrs",
    lessons: "12 lessons",
    icon: "JS",
  },
  {
    id: 2,
    title: "Node.js & Express",
    instructor: "David Wilson",
    status: "In Progress",
    hours: "4.2 hrs",
    lessons: "10 lessons",
    icon: "⬡",
  },
  {
    id: 3,
    title: "MongoDB Basics",
    instructor: "Lisa Ray",
    status: "Not Started",
    hours: "5.0 hrs",
    lessons: "12 lessons",
    icon: "◈",
  },
];
```

---

```my-app/data/CourseCard.ts```

```code
import type { Course } from "@/app/data/courses";

type CourseCardProps = {
    course: Course;
};

export default function CourseCard({ course }: CourseCardProps) {
    return (
        <article className="overflow-hidden rounded-xl border border-slate-100 bg-white shadow-sm transition hover:-translate-y-1 hover:shadow-lg">
            <div
                className={`relative flex h-28 items-center justify-center bg-linear-to-br ${course.gradient}`}
            >
                <span className="text-6xl font-bold text-white/90">
                    {course.icon}
                </span>

                <span className="absolute right-3 top-3 rounded-full bg-white/95 px-3 py-1 text-[10px] font-semibold text-slate-700">
                    {course.progress === 0
                        ? "Not Started"
                        : "In Progress"}
                </span>
            </div>

            <div className="p-4">
                <h3 className="font-bold text-slate-900">{course.title}</h3>

                <p className="mt-1 text-xs text-slate-500">
                    By {course.instructor}
                </p>

                <div className="mt-4 h-1.5 overflow-hidden rounded-full bg-slate-100">
                    <div
                        className="h-full rounded-full bg-blue-600 transition-all"
                        style={{ width: `${course.progress}%` }}
                    />
                </div>

                <div className="mt-2 flex justify-between text-xs text-slate-500">
                    <span>{course.lessons}</span>
                    <span>{course.progress}%</span>
                </div>

                <div className="mt-4 flex items-center justify-between border-t border-slate-100 pt-3 text-xs text-slate-500">
                    <span>◷ {course.hours}</span>
                    <button
                        className="font-semibold text-blue-600 hover:text-blue-800"
                        onClick={() => alert(`Selected: ${course.title}`)}
                    >
                        {course.progress === 0 ? "Start Course →" : "Continue →"}
                    </button>
                </div>
            </div>
        </article>
    );
}
```

---

```my-app/data/Dashboard.ts```

```code
"use client";

import { useMemo, useState } from "react";
import Sidebar from "./Sidebar";
import Topbar from "./Topbar";
import StatCard from "./StatCard";
import CourseCard from "./CourseCard";
import DeadlinePanel from "./DeadlinePanel";
import { courses, recentCourses } from "@/app/data/courses";

export default function Dashboard() {
  const [search, setSearch] = useState("");

  const filteredCourses = useMemo(
    () =>
      courses.filter((course) =>
        `${course.title} ${course.instructor} ${course.category}`
          .toLowerCase()
          .includes(search.toLowerCase())
      ),
    [search]
  );

  return (
    <div className="min-h-screen bg-[#f5f7fc] text-slate-900 md:flex">
      <Sidebar />

      <div className="min-w-0 flex-1">
        <Topbar onSearch={setSearch} />

        <main className="p-4 sm:p-6 lg:p-7">
          <div className="grid gap-6 xl:grid-cols-[minmax(0,1fr)_340px]">
            {/* Main content */}
            <div className="min-w-0 space-y-6">
              {/* Welcome banner */}
              <section className="relative overflow-hidden rounded-2xl bg-linear-to-r from-sky-100 via-blue-100 to-violet-100 p-7 sm:p-9">
                <div className="relative z-10 max-w-lg">
                  <p className="text-sm font-semibold text-blue-700">
                    YOUR LEARNING SPACE
                  </p>

                  <h1 className="mt-3 text-3xl font-bold tracking-tight text-[#101d38] sm:text-4xl">
                    Good morning, Sufyan 👋
                  </h1>

                  <p className="mt-3 max-w-md leading-7 text-slate-600">
                    Keep learning, keep growing. Your next skill can
                    change your future.
                  </p>

                  <button
                    onClick={() =>
                      document
                        .getElementById("courses")
                        ?.scrollIntoView({ behavior: "smooth" })
                    }
                    className="mt-5 rounded-xl bg-linear-to-r from-blue-600 to-indigo-600 px-5 py-3 text-sm font-semibold text-white shadow-lg shadow-blue-600/20 transition hover:-translate-y-0.5"
                  >
                    Continue Learning →
                  </button>
                </div>

                <div className="pointer-events-none absolute -bottom-16 -right-8 text-[170px] opacity-20 sm:right-5 sm:text-[210px]">
                  🎓
                </div>
              </section>

              {/* Stats */}
              <section className="grid grid-cols-2 gap-4 xl:grid-cols-4">
                <StatCard
                  title="Enrolled Courses"
                  value="5"
                  change="+2 this month"
                  icon="▣"
                  color="bg-blue-100 text-blue-600"
                />

                <StatCard
                  title="Completed Courses"
                  value="1"
                  change="+1 this month"
                  icon="☑"
                  color="bg-emerald-100 text-emerald-600"
                />

                <StatCard
                  title="Learning Hours"
                  value="12.5"
                  change="+3.2 this month"
                  icon="◷"
                  color="bg-violet-100 text-violet-600"
                />

                <StatCard
                  title="Certificates"
                  value="1"
                  change="+1 this month"
                  icon="♧"
                  color="bg-orange-100 text-orange-600"
                />
              </section>

              {/* Courses */}
              <section id="courses" className="scroll-mt-6">
                <div className="mb-5 flex items-end justify-between gap-3">
                  <div>
                    <h2 className="text-xl font-bold text-[#101d38]">
                      Continue Learning
                    </h2>

                    <p className="mt-1 text-sm text-slate-500">
                      Pick up where you left off
                    </p>
                  </div>

                  <span className="text-sm text-slate-500">
                    {filteredCourses.length} courses
                  </span>
                </div>

                {filteredCourses.length > 0 ? (
                  <div className="grid gap-5 sm:grid-cols-2 lg:grid-cols-3">
                    {filteredCourses.map((course) => (
                      <CourseCard key={course.id} course={course} />
                    ))}
                  </div>
                ) : (
                  <div className="rounded-2xl border border-dashed border-slate-300 bg-white p-10 text-center">
                    <p className="font-semibold">No courses found</p>
                    <p className="mt-2 text-sm text-slate-500">
                      Try another course title or instructor.
                    </p>
                  </div>
                )}
              </section>

              {/* Recent courses */}
              <section className="overflow-hidden rounded-2xl border border-slate-100 bg-white p-5 shadow-sm">
                <div className="mb-4 flex items-center justify-between">
                  <div>
                    <h2 className="text-lg font-bold">
                      Recent Courses
                    </h2>
                    <p className="mt-1 text-xs text-slate-500">
                      Your latest enrolled courses
                    </p>
                  </div>
                </div>

                <div className="divide-y divide-slate-100">
                  {recentCourses.map((course) => (
                    <div
                      key={course.id}
                      className="flex items-center gap-3 py-4"
                    >
                      <div className="flex h-10 w-10 shrink-0 items-center justify-center rounded-xl bg-slate-100 font-bold text-slate-800">
                        {course.icon}
                      </div>

                      <div className="min-w-0 flex-1">
                        <p className="truncate text-sm font-semibold">
                          {course.title}
                        </p>
                        <p className="mt-1 text-xs text-slate-500">
                          {course.instructor}
                        </p>
                      </div>

                      <span
                        className={`hidden rounded-full px-3 py-1 text-xs font-medium sm:inline-block ${
                          course.status === "Completed"
                            ? "bg-emerald-100 text-emerald-700"
                            : course.status === "In Progress"
                              ? "bg-blue-100 text-blue-700"
                              : "bg-slate-100 text-slate-600"
                        }`}
                      >
                        {course.status}
                      </span>

                      <span className="hidden text-xs text-slate-500 lg:block">
                        {course.hours}
                      </span>
                    </div>
                  ))}
                </div>
              </section>
            </div>

            {/* Right column */}
            <aside className="space-y-6">
              {/* Calendar */}
              <section className="rounded-2xl border border-slate-100 bg-white p-5 shadow-sm">
                <h2 className="text-lg font-bold">Calendar</h2>
                <p className="mt-2 text-sm font-medium text-slate-700">
                  October 2026
                </p>

                <div className="mt-5 grid grid-cols-7 gap-y-3 text-center">
                  {["Su", "Mo", "Tu", "We", "Th", "Fr", "Sa"].map(
                    (day) => (
                      <span
                        key={day}
                        className="text-xs font-medium text-slate-400"
                      >
                        {day}
                      </span>
                    )
                  )}

                  {Array.from({ length: 35 }, (_, i) => {
                    const day = i - 3 + 1;
                    const valid = day >= 1 && day <= 31;

                    return (
                      <span
                        key={i}
                        className={`mx-auto flex h-8 w-8 items-center justify-center rounded-full text-xs ${
                          day === 10
                            ? "bg-blue-600 font-bold text-white shadow-md shadow-blue-600/30"
                            : valid
                              ? "text-slate-700 hover:bg-blue-50"
                              : "text-transparent"
                        }`}
                      >
                        {valid ? day : ""}
                      </span>
                    );
                  })}
                </div>

                <div className="mt-5 border-t border-slate-100 pt-5">
                  <DeadlinePanel />
                </div>
              </section>

              {/* Motivation */}
              <section className="rounded-2xl border border-indigo-100 bg-linear-to-br from-indigo-50 to-blue-50 p-7 text-center">
                <div className="text-5xl">🏆</div>

                <h2 className="mt-4 text-lg font-bold text-[#101d38]">
                  You're Doing Great!
                </h2>

                <p className="mt-2 text-sm leading-6 text-slate-600">
                  Keep up the good work and stay consistent. Your
                  efforts will pay off!
                </p>
              </section>
            </aside>
          </div>
        </main>
      </div>
    </div>
  );
}
```

---

```my-app/data/DeadlinePanel.ts```

```code
const deadlines = [
  {
    title: "React Project Submission",
    due: "Due in 2 days",
    icon: "▣",
    color: "bg-emerald-100 text-emerald-600",
  },
  {
    title: "JavaScript Quiz",
    due: "Due in 4 days",
    icon: "▤",
    color: "bg-violet-100 text-violet-600",
  },
  {
    title: "Next.js Assignment",
    due: "Due in 6 days",
    icon: "▣",
    color: "bg-orange-100 text-orange-600",
  },
  {
    title: "Tailwind CSS Project",
    due: "Due in 10 days",
    icon: "▤",
    color: "bg-blue-100 text-blue-600",
  },
];

export default function DeadlinePanel() {
  return (
    <section className="rounded-2xl border border-slate-100 bg-white p-5 shadow-sm">
      <div className="mb-4 flex items-center justify-between">
        <h2 className="text-lg font-bold text-slate-900">
          Upcoming Deadlines
        </h2>

        <button className="text-xs font-semibold text-blue-600">
          View all →
        </button>
      </div>

      <div className="divide-y divide-slate-100">
        {deadlines.map((deadline) => (
          <div
            key={deadline.title}
            className="flex items-center gap-3 py-4"
          >
            <div
              className={`flex h-11 w-11 shrink-0 items-center justify-center rounded-xl text-xl ${deadline.color}`}
            >
              {deadline.icon}
            </div>

            <div className="min-w-0 flex-1">
              <h3 className="truncate text-sm font-semibold text-slate-800">
                {deadline.title}
              </h3>

              <p className="mt-1 text-xs text-slate-500">
                {deadline.due}
              </p>
            </div>

            <span className="text-slate-400">›</span>
          </div>
        ))}
      </div>
    </section>
  );
}
```

---

```my-app/data/Sidebar.ts```

```code
"use client";

import { useState } from "react";

const navItems = [
    { name: "Dashboard", icon: "⌂" },
    { name: "My Courses", icon: "▤" },
    { name: "Browse Courses", icon: "⌕" },
    { name: "Assignments", icon: "▧", badge: "3" },
    { name: "Quizzes", icon: "☑" },
    { name: "Certificates", icon: "♧" },
    { name: "Messages", icon: "✉", badge: "2" },
    { name: "Settings", icon: "⚙" },
];

export default function Sidebar() {
    const [active, setActive] = useState("Dashboard");

    return (
        <aside className="flex w-full flex-col bg-[#101d38] p-4 text-white md:sticky md:top-0 md:h-screen md:w-64 md:shrink-0 md:p-5">
            <a href="/" className="mb-8 flex items-center gap-3 px-2 py-2">
                <span className="text-3xl text-blue-400">◆</span>
                <span className="text-2xl font-bold">
                    Learn<span className="text-blue-400">Hub</span>
                </span>
            </a>

            <nav className="flex gap-2 overflow-x-auto md:flex-col md:overflow-visible">
                {navItems.map((item) => (
                    <button
                        key={item.name}
                        onClick={() => setActive(item.name)}
                        className={`flex shrink-0 items-center gap-3 rounded-xl px-3 py-3 text-left transition ${active === item.name
                                ? "bg-blue-600 text-white shadow-lg shadow-blue-950/30"
                                : "text-slate-300 hover:bg-white/10 hover:text-white"
                            }`}
                    >
                        <span className="w-6 text-center text-xl">{item.icon}</span>
                        <span className="text-sm font-medium">{item.name}</span>

                        {item.badge && (
                            <span className="ml-auto rounded-full bg-rose-500 px-2 py-0.5 text-xs">
                                {item.badge}
                            </span>
                        )}
                    </button>
                ))}
            </nav>

            <div className="mt-8 hidden rounded-2xl border border-slate-700 bg-slate-800/60 p-4 md:mt-auto md:block">
                <div className="text-center text-5xl">🎓</div>

                <h3 className="mt-4 font-bold">Upgrade to Pro</h3>

                <p className="mt-2 text-sm leading-6 text-slate-300">
                    Get access to premium courses, certificates and more.
                </p>

                <button className="mt-4 w-full rounded-lg bg-linear-to-r from-indigo-500 to-blue-500 py-2.5 text-sm font-semibold hover:opacity-90">
                    Go Pro.
                </button>
            </div>
        </aside>
    );
}
```

---

```code
type StatCardProps = {
  title: string;
  value: string;
  change: string;
  icon: string;
  color: string;
};

export default function StatCard({
  title,
  value,
  change,
  icon,
  color,
}: StatCardProps) {
  return (
    <article className="rounded-2xl border border-slate-100 bg-white p-5 shadow-sm transition hover:-translate-y-1 hover:shadow-md">
      <div
        className={`flex h-11 w-11 items-center justify-center rounded-xl text-xl ${color}`}
      >
        {icon}
      </div>

      <p className="mt-4 text-sm text-slate-500">{title}</p>

      <h3 className="mt-1 text-3xl font-bold text-[#101d38]">
        {value}
      </h3>

      <p className="mt-2 text-xs font-medium text-emerald-600">
        ↗ {change}
      </p>
    </article>
  );
}
```

```my-app/data/StatCard.ts```

```code
type StatCardProps = {
  title: string;
  value: string;
  change: string;
  icon: string;
  color: string;
};

export default function StatCard({
  title,
  value,
  change,
  icon,
  color,
}: StatCardProps) {
  return (
    <article className="rounded-2xl border border-slate-100 bg-white p-5 shadow-sm transition hover:-translate-y-1 hover:shadow-md">
      <div
        className={`flex h-11 w-11 items-center justify-center rounded-xl text-xl ${color}`}
      >
        {icon}
      </div>

      <p className="mt-4 text-sm text-slate-500">{title}</p>

      <h3 className="mt-1 text-3xl font-bold text-[#101d38]">
        {value}
      </h3>

      <p className="mt-2 text-xs font-medium text-emerald-600">
        ↗ {change}
      </p>
    </article>
  );
}
```

---

```my-app/data/Topbar.ts```

```code
"use client";

import { useState } from "react";

type TopbarProps = {
    onSearch: (value: string) => void;
};

export default function Topbar({ onSearch }: TopbarProps) {
    const [search, setSearch] = useState("");

    return (
        <header className="flex flex-col gap-4 border-b border-slate-200 bg-white px-5 py-4 sm:flex-row sm:items-center sm:justify-between sm:px-8">
            <div className="relative w-full sm:max-w-md">
                <span className="absolute left-4 top-3 text-xl text-slate-400">
                    ⌕
                </span>

                <input
                    value={search}
                    onChange={(event) => {
                        setSearch(event.target.value);
                        onSearch(event.target.value);
                    }}
                    placeholder="Search courses or topics..."
                    className="w-full rounded-xl border border-slate-200 bg-slate-50 py-3 pl-11 pr-4 text-sm outline-none focus:border-blue-500 focus:ring-4 focus:ring-blue-500/10"
                />
            </div>

            <div className="flex items-center justify-between gap-5">
                <button
                    aria-label="Notifications"
                    className="relative text-2xl text-slate-600"
                >
                    ♧
                    <span className="absolute -right-1 -top-1 h-3 w-3 rounded-full border-2 border-white bg-rose-500" />
                </button>

                <div className="flex items-center gap-3">
                    <div className="flex h-11 w-11 items-center justify-center rounded-full bg-blue-100 text-xl">
                        👨🏻‍💻
                    </div>

                    <div>
                        <p className="text-sm font-bold text-slate-900">
                            Sufyan Ahmed
                        </p>
                        <p className="text-xs text-slate-500">Student</p>
                    </div>

                    <span className="text-slate-400">⌄</span>
                </div>
            </div>
        </header>
    );
}
```


![Image View](img_Modern_LearnHub_LMS_Dashboard.png)

## End of point.



<br/>
