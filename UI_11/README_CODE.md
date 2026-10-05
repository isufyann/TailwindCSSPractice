# GPT generated code for complete Registration Form

```code
"use client";

import { useState } from "react";

export default function UI() {
  const [form, setForm] = useState({
    name: "",
    email: "",
    password: "",
    country: "",
    gender: "",
    message: "",
    terms: false,
  });

  const [errors, setErrors] = useState({});
  const [success, setSuccess] = useState(false);
  const [loading, setLoading] = useState(false);

  function handleChange(e:any) {
    const { name, value, type, checked } = e.target;

    setForm({
      ...form,
      [name]: type === "checkbox" ? checked : value,
    });

    // Remove error when user starts correcting the field
    setErrors({
      ...errors,
      [name]: "",
    });

    setSuccess(false);
  }

  function validate() {
    const newErrors = {};

    if (!form.name.trim()) {
      newErrors.name = "Name is required.";
    }

    if (!form.email.trim()) {
      newErrors.email = "Email is required.";
    } else if (!form.email.includes("@")) {
      newErrors.email = "Please enter a valid email.";
    }

    if (!form.password) {
      newErrors.password = "Password is required.";
    } else if (form.password.length < 8) {
      newErrors.password =
        "Password must be at least 8 characters.";
    }

    if (!form.country) {
      newErrors.country = "Please select your country.";
    }

    if (!form.gender) {
      newErrors.gender = "Please select your gender.";
    }

    if (!form.terms) {
      newErrors.terms =
        "You must accept the terms and conditions.";
    }

    return newErrors;
  }

  async function handleSubmit(e) {
    e.preventDefault();

    const validationErrors = validate();

    if (Object.keys(validationErrors).length > 0) {
      setErrors(validationErrors);
      setSuccess(false);
      return;
    }

    setLoading(true);
    setSuccess(false);

    // Simulate API request
    await new Promise((resolve) =>
      setTimeout(resolve, 1500)
    );

    setLoading(false);
    setSuccess(true);
  }

  const inputClass = (field) => `
    w-full
    px-4
    py-3
    border
    rounded-lg
    outline-none
    transition-colors
    duration-200

    ${
      errors[field]
        ? "border-red-500 focus:border-red-500 focus:ring-2 focus:ring-red-200"
        : "border-gray-300 focus:border-blue-500 focus:ring-2 focus:ring-blue-200"
    }
  `;

  return (
    <div className="min-h-screen bg-gray-100 py-10 px-4">

      <div className="max-w-3xl mx-auto bg-white rounded-2xl shadow-lg p-6 md:p-8">

        <div className="mb-8">
          <h1 className="text-3xl font-bold text-gray-900">
            Create Account
          </h1>

          <p className="mt-2 text-gray-600">
            Register your account by filling out the form below.
          </p>
        </div>

        <form
          onSubmit={handleSubmit}
          className="space-y-6"
        >

          {/* Name + Email */}

          <div className="grid grid-cols-1 md:grid-cols-2 gap-5">

            <div>
              <label className="block mb-2 font-medium text-gray-700">
                Full Name
              </label>

              <input
                type="text"
                name="name"
                value={form.name}
                onChange={handleChange}
                placeholder="Muhammad Sufyan"
                className={inputClass("name")}
              />

              {errors.name && (
                <p className="mt-1 text-sm text-red-600">
                  {errors.name}
                </p>
              )}
            </div>


            <div>
              <label className="block mb-2 font-medium text-gray-700">
                Email
              </label>

              <input
                type="email"
                name="email"
                value={form.email}
                onChange={handleChange}
                placeholder="you@example.com"
                className={inputClass("email")}
              />

              {errors.email && (
                <p className="mt-1 text-sm text-red-600">
                  {errors.email}
                </p>
              )}
            </div>

          </div>


          {/* Password */}

          <div>

            <label className="block mb-2 font-medium text-gray-700">
              Password
            </label>

            <input
              type="password"
              name="password"
              value={form.password}
              onChange={handleChange}
              placeholder="Minimum 8 characters"
              className={inputClass("password")}
            />

            {errors.password && (
              <p className="mt-1 text-sm text-red-600">
                {errors.password}
              </p>
            )}

          </div>


          {/* Country */}

          <div>

            <label className="block mb-2 font-medium text-gray-700">
              Country
            </label>

            <select
              name="country"
              value={form.country}
              onChange={handleChange}
              className={inputClass("country")}
            >
              <option value="">
                Select your country
              </option>

              <option value="pakistan">
                Pakistan
              </option>

              <option value="india">
                India
              </option>

              <option value="usa">
                United States
              </option>

              <option value="uk">
                United Kingdom
              </option>
            </select>

            {errors.country && (
              <p className="mt-1 text-sm text-red-600">
                {errors.country}
              </p>
            )}

          </div>


          {/* Gender */}

          <div>

            <label className="block mb-3 font-medium text-gray-700">
              Gender
            </label>

            <div className="flex flex-wrap gap-6">

              <label className="flex items-center gap-2">
                <input
                  type="radio"
                  name="gender"
                  value="male"
                  checked={form.gender === "male"}
                  onChange={handleChange}
                  className="h-4 w-4 accent-blue-600"
                />

                <span>Male</span>
              </label>


              <label className="flex items-center gap-2">
                <input
                  type="radio"
                  name="gender"
                  value="female"
                  checked={form.gender === "female"}
                  onChange={handleChange}
                  className="h-4 w-4 accent-blue-600"
                />

                <span>Female</span>
              </label>

            </div>

            {errors.gender && (
              <p className="mt-1 text-sm text-red-600">
                {errors.gender}
              </p>
            )}

          </div>


          {/* Message */}

          <div>

            <label className="block mb-2 font-medium text-gray-700">
              About You
            </label>

            <textarea
              name="message"
              value={form.message}
              onChange={handleChange}
              placeholder="Tell us something about yourself..."
              className="
                w-full
                min-h-32
                px-4
                py-3
                border
                border-gray-300
                rounded-lg
                outline-none
                resize-y
                placeholder:text-gray-400
                focus:border-blue-500
                focus:ring-2
                focus:ring-blue-200
              "
            />

          </div>


          {/* Terms */}

          <div>

            <label className="flex items-start gap-3">

              <input
                type="checkbox"
                name="terms"
                checked={form.terms}
                onChange={handleChange}
                className="mt-1 h-5 w-5 accent-blue-600"
              />

              <span className="text-sm text-gray-600">
                I agree to the terms and conditions.
              </span>

            </label>

            {errors.terms && (
              <p className="mt-1 text-sm text-red-600">
                {errors.terms}
              </p>
            )}

          </div>


          {/* Success Message */}

          {success && (
            <div className="
              rounded-lg
              border
              border-green-200
              bg-green-50
              px-4
              py-3
              text-green-700
            ">
              Registration successful!
            </div>
          )}


          {/* Submit */}

          <button
            type="submit"
            disabled={loading}
            className="
              w-full
              bg-blue-600
              hover:bg-blue-700
              active:scale-[0.99]
              text-white
              font-semibold
              py-3
              rounded-lg
              transition
              duration-200
              disabled:bg-gray-400
              disabled:cursor-not-allowed
              disabled:opacity-70
            "
          >
            {loading ? "Creating Account..." : "Create Account"}
          </button>

        </form>

      </div>

    </div>
  );
}
```
