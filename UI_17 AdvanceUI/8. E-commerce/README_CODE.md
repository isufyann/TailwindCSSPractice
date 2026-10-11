# E-commerce Interface

### Category Filter

```app/components/CategoryFilter.tsx```

```code
type CategoryFilterProps = {
  categories: string[];
  selected: string;
  onSelect: (category: string) => void;
};

export default function CategoryFilter({
  categories,
  selected,
  onSelect,
}: CategoryFilterProps) {
  return (
    <div className="flex flex-wrap gap-3">
      {categories.map((category) => (
        <button
          key={category}
          type="button"
          onClick={() => onSelect(category)}
          aria-pressed={selected === category}
          className={`rounded-full px-5 py-2.5 text-sm font-semibold transition ${
            selected === category
              ? "bg-violet-600 text-white shadow-lg shadow-violet-200"
              : "border border-slate-200 bg-white text-slate-600 hover:border-violet-300 hover:text-violet-600"
          }`}
        >
          {category}
        </button>
      ))}
    </div>
  );
}
```

---

### Hero Section

```app/components/hero.tsx```

```code
export default function Hero() {
  return (
    <section className="relative overflow-hidden bg-linear-to-br from-violet-950 via-indigo-900 to-slate-900 text-white">
      <div className="absolute -right-24 -top-24 h-80 w-80 rounded-full bg-violet-500/30 blur-3xl" />

      <div className="relative mx-auto grid max-w-7xl items-center gap-10 px-6 py-16 sm:py-20 lg:grid-cols-2 lg:px-8 lg:py-24">
        <div>
          <span className="inline-flex rounded-full border border-white/20 bg-white/10 px-4 py-2 text-xs font-semibold tracking-wide text-violet-200">
            YOUR EVERYDAY STYLE DESTINATION
          </span>

          <h1 className="mt-6 max-w-xl text-4xl font-black leading-tight tracking-tight sm:text-5xl lg:text-6xl">
            Discover products you'll
            <span className="text-violet-300"> love.</span>
          </h1>

          <p className="mt-5 max-w-lg leading-7 text-slate-300">
            Shop the latest essentials, discover your favorites, and
            enjoy a better online shopping experience.
          </p>

          <a
            href="#products"
            className="mt-8 inline-flex items-center gap-3 rounded-full bg-white px-7 py-3.5 text-sm font-bold text-violet-950 transition hover:-translate-y-0.5 hover:bg-violet-100"
          >
            Explore Collection <span aria-hidden="true">→</span>
          </a>

          <div className="mt-10 flex flex-wrap gap-6 text-sm text-slate-300">
            <span>✓ Quality products</span>
            <span>✓ Great prices</span>
            <span>✓ Easy shopping</span>
          </div>
        </div>

        <div className="relative mx-auto w-full max-w-lg">
          <div className="absolute inset-5 rounded-full bg-violet-500/30 blur-3xl" />

          <img
            src="https://images.unsplash.com/photo-1441986300917-64674bd600d8?auto=format&fit=crop&w=1000&q=85"
            alt="Modern fashion and retail store"
            className="relative h-72 w-full rounded-3xl object-cover shadow-2xl sm:h-96 hover:scale-110 transition"
          />

          <div className="absolute -bottom-5 left-4 group hover:scale-90 transition hover:bg-transparent hover:text-white rounded-2xl bg-white p-4 text-slate-900 shadow-xl sm:left-8">
            <p className="text-xs text-slate-500 group-hover:text-white">Discover your next</p>
            <p className="mt-1 font-bold">Everyday favorite ✨</p>
          </div>
        </div>
      </div>
    </section>
  );
}
```

### Navbar Section

```app/components/navbar.tsx```

```code
"use client";

type NavbarProps = {
    cartCount: number;
    search: string;
    onSearchChange: (value: string) => void;
};

export default function Navbar({
    cartCount,
    search,
    onSearchChange,
}: NavbarProps) {
    
    return (
        <header className="sticky top-0 z-50 border-b border-slate-100 bg-white/95 backdrop-blur">
            <div className="mx-auto flex max-w-7xl flex-wrap items-center justify-between gap-4 px-5 py-4 lg:px-8">
                <a href="/" className="text-2xl font-black tracking-tight">
                    Shop<span className="text-violet-600">Ease.</span>
                </a>

                <div className="order-3 w-full sm:w-auto sm:flex-1 sm:max-w-md sm:px-6">
                    <label htmlFor="product-search" className="sr-only">
                        Search products
                    </label>
                    <input
                        id="product-search"
                        type="search"
                        value={search}
                        onChange={(event) => onSearchChange(event.target.value)}
                        placeholder="Search products..."
                        className="w-full rounded-full border border-slate-200 bg-slate-50 px-5 py-2.5 text-sm outline-none transition focus:border-violet-500 focus:ring-4 focus:ring-violet-100"
                    />
                </div>

                <div className="flex items-center gap-4">
                    <a
                        href="#products"
                        className="hidden text-sm font-medium text-slate-600 hover:text-violet-600 sm:block"
                    >
                        Shop
                    </a>

                    <button
                        type="button"
                        onClick={() =>
                            document
                                .getElementById("cart-summary")
                                ?.scrollIntoView({ behavior: "smooth" })
                        }
                        className="relative rounded-full bg-slate-100 p-3 transition hover:bg-violet-100"
                        aria-label={`Shopping cart, ${cartCount} items`}
                    >
                        <svg
                            viewBox="0 0 24 24"
                            fill="none"
                            stroke="currentColor"
                            strokeWidth="1.8"
                            className="h-5 w-5"
                            aria-hidden="true"
                        >
                            <path
                                d="M3 3h2l2.4 11.4a2 2 0 0 0 2 1.6h7.8a2 2 0 0 0 2-1.6L21 8H6"
                                strokeLinecap="round"
                                strokeLinejoin="round"
                            />
                            <circle cx="10" cy="20" r="1" />
                            <circle cx="18" cy="20" r="1" />
                        </svg>

                        {cartCount > 0 && (
                            <span className="absolute -right-1 -top-1 flex h-5 min-w-5 items-center justify-center rounded-full bg-violet-600 px-1 text-xs font-bold text-white">
                                {cartCount}
                            </span>
                        )}
                    </button>
                </div>
            </div>
        </header>
    );
}
```

---

### Product Card

```app/components/ProductCard.tsx```

```code
import type { Product } from "@/app/data/products";

type ProductCardProps = {
  product: Product;
  onAddToCart: (product: Product) => void;
};

export default function ProductCard({
  product,
  onAddToCart,
}: ProductCardProps) {
  const discount = Math.round(
    ((product.oldPrice - product.price) / product.oldPrice) * 100
  );

  return (
    <article className="group overflow-hidden rounded-2xl border border-slate-100 bg-white transition duration-300 hover:-translate-y-1 hover:shadow-xl hover:shadow-slate-200/70">
      <div className="relative overflow-hidden bg-slate-50">
        <img
          src={product.image}
          alt={product.name}
          loading="lazy"
          className="h-56 w-full object-cover transition duration-500 group-hover:scale-105"
        />

        {product.badge && (
          <span className="absolute left-3 top-3 rounded-full bg-violet-600 px-3 py-1.5 text-xs font-bold text-white">
            {product.badge}
          </span>
        )}

        <span className="absolute right-3 top-3 rounded-full bg-white px-2.5 py-1.5 text-xs font-bold text-emerald-600 shadow-sm">
          -{discount}%
        </span>
      </div>

      <div className="p-4">
        <p className="text-xs font-semibold uppercase tracking-wider text-violet-600">
          {product.category}
        </p>

        <h3 className="mt-2 min-h-12 font-bold leading-6 text-slate-900">
          {product.name}
        </h3>

        <div className="mt-2 flex items-center gap-1.5 text-sm">
          <span className="text-amber-400">★</span>
          <span className="font-semibold text-slate-700">
            {product.rating}
          </span>
          <span className="text-slate-400">/ 5</span>
        </div>

        <div className="mt-4 flex items-center gap-2">
          <span className="text-xl font-extrabold text-slate-900">
            Rs. {product.price.toLocaleString("en-PK")}
          </span>

          <span className="text-sm text-slate-400 line-through">
            Rs. {product.oldPrice.toLocaleString("en-PK")}
          </span>
        </div>

        <button
          type="button"
          onClick={() => onAddToCart(product)}
          className="mt-5 w-full rounded-xl bg-slate-900 px-4 py-3 text-sm font-semibold text-white transition hover:bg-violet-600 focus:outline-none focus:ring-4 focus:ring-violet-200"
        >
          + Add to Cart
        </button>
      </div>
    </article>
  );
}
```

---

### Product Section

```app/components/ProductSection.tsx```

```code
"use client";

import { useMemo, useState } from "react";
import { categories, products, type Product } from "@/app/data/products";
import CategoryFilter from "./CategoryFilter";
import ProductCard from "./ProductCard";

export default function ProductSection() {
  const [selectedCategory, setSelectedCategory] = useState("All");
  const [cart, setCart] = useState<Product[]>([]);
  const [search, setSearch] = useState("");

  const filteredProducts = useMemo(() => {
    return products.filter((product) => {
      const matchesCategory =
        selectedCategory === "All" ||
        product.category === selectedCategory;

      const matchesSearch = product.name
        .toLowerCase()
        .includes(search.toLowerCase());

      return matchesCategory && matchesSearch;
    });
  }, [selectedCategory, search]);

  function addToCart(product: Product) {
    setCart((currentCart) => [...currentCart, product]);
  }

  const cartTotal = cart.reduce((total, product) => total + product.price, 0);

  return (
    <>
      <section
        id="products"
        className="mx-auto max-w-7xl scroll-mt-24 px-5 py-16 lg:px-8"
      >
        <div className="flex flex-col justify-between gap-6 md:flex-row md:items-end">
          <div>
            <p className="text-sm font-bold uppercase tracking-widest text-violet-600">
              Our collection
            </p>

            <h2 className="mt-2 text-3xl font-black tracking-tight text-slate-900 sm:text-4xl">
              Featured Products
            </h2>

            <p className="mt-3 text-slate-500">
              Find something special for yourself.
            </p>
          </div>

          <div className="w-full md:max-w-xs">
            <input
              type="search"
              value={search}
              onChange={(event) => setSearch(event.target.value)}
              placeholder="Filter products by name..."
              aria-label="Filter products by name"
              className="w-full rounded-xl border border-slate-200 bg-white px-4 py-3 text-sm outline-none focus:border-violet-500 focus:ring-4 focus:ring-violet-100"
            />
          </div>
        </div>

        <div className="mt-8">
          <CategoryFilter
            categories={categories}
            selected={selectedCategory}
            onSelect={setSelectedCategory}
          />
        </div>

        <div className="mt-8 grid grid-cols-1 gap-6 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4">
          {filteredProducts.map((product) => (
            <ProductCard
              key={product.id}
              product={product}
              onAddToCart={addToCart}
            />
          ))}
        </div>

        {filteredProducts.length === 0 && (
          <div className="mt-8 rounded-2xl border border-dashed border-slate-300 p-12 text-center">
            <p className="text-lg font-bold text-slate-800">
              No products found
            </p>
            <p className="mt-2 text-sm text-slate-500">
              Try another search term or category.
            </p>
            <button
              type="button"
              onClick={() => {
                setSearch("");
                setSelectedCategory("All");
              }}
              className="mt-4 font-semibold text-violet-600 hover:text-violet-800"
            >
              Clear filters
            </button>
          </div>
        )}
      </section>

      <section
        id="cart-summary"
        className="mx-auto max-w-7xl scroll-mt-24 px-5 pb-12 lg:px-8"
      >
        <div className="flex flex-col justify-between gap-4 rounded-2xl border border-violet-100 bg-violet-50 p-6 sm:flex-row sm:items-center">
          <div>
            <h2 className="text-xl font-bold text-slate-900">
              Your Shopping Cart
            </h2>
            <p className="mt-1 text-sm text-slate-600">
              {cart.length} {cart.length === 1 ? "item" : "items"} added
            </p>
          </div>

          <div className="sm:text-right">
            <p className="text-sm text-slate-500">Cart total</p>
            <p className="mt-1 text-2xl font-black text-violet-700">
              Rs. {cartTotal.toLocaleString("en-PK")}
            </p>
          </div>
        </div>

        {cart.length > 0 && (
          <div className="mt-4 divide-y divide-slate-100 rounded-2xl border border-slate-200 bg-white px-5">
            {cart.map((product, index) => (
              <div
                key={`${product.id}-${index}`}
                className="flex items-center justify-between gap-4 py-4"
              >
                <div className="min-w-0">
                  <p className="truncate text-sm font-semibold text-slate-800">
                    {product.name}
                  </p>
                  <p className="mt-1 text-xs text-slate-500">
                    Rs. {product.price.toLocaleString("en-PK")}
                  </p>
                </div>

                <button
                  type="button"
                  onClick={() =>
                    setCart((currentCart) =>
                      currentCart.filter((_, i) => i !== index)
                    )
                  }
                  className="shrink-0 text-sm font-semibold text-rose-600 hover:text-rose-800"
                  aria-label={`Remove ${product.name} from cart`}
                >
                  Remove
                </button>
              </div>
            ))}
          </div>
        )}
      </section>
    </>
  );
}
```

---

### Shop Section

```app/components/Shop.tsx```

```code
"use client";

import { useState } from "react";
import type { Product } from "@/app/data/products";
import Navbar from "./Navbar";
import Hero from "./Hero";
import ProductSection from "./ProductSection";

export default function Shop() {
  const [search, setSearch] = useState("");
  const [cart, setCart] = useState<Product[]>([]);

  return (
    <main className="min-h-screen bg-white">
      <Navbar
        cartCount={cart.length}
        search={search}
        onSearchChange={setSearch}
      />

      <Hero />

      {/* <ProductSection
        search={search}
        cart={cart}
        setCart={setCart}
      /> */}

      <footer className="border-t border-slate-100 bg-slate-950 px-5 py-10 text-center text-sm text-slate-400">
        <p className="text-xl font-bold text-white">
          Shop<span className="text-violet-400">Ease.</span>
        </p>
        <p className="mt-3">Shopping made simple.</p>
        <p className="mt-5">© 2026 ShopEase. All rights reserved.</p>
      </footer>
    </main>
  );
}
```

---

### Data Folder

```app/data/products.tsx```

```code
export type Product = {
  id: number;
  name: string;
  category: string;
  price: number;
  oldPrice: number;
  rating: number;
  image: string;
  badge?: string;
};

export const products: Product[] = [
  {
    id: 1,
    name: "Premium Wireless Headphones",
    category: "Electronics",
    price: 7999,
    oldPrice: 9999,
    rating: 4.8,
    image:
      "https://images.unsplash.com/photo-1505740420928-5e560c06d30e?auto=format&fit=crop&w=700&q=80",
    badge: "Best Seller",
  },
  {
    id: 2,
    name: "Classic Everyday Sneakers",
    category: "Fashion",
    price: 5499,
    oldPrice: 6999,
    rating: 4.6,
    image:
      "https://images.unsplash.com/photo-1542291026-7eec264c27ff?auto=format&fit=crop&w=700&q=80",
    badge: "Sale",
  },
  {
    id: 3,
    name: "Minimalist Wrist Watch",
    category: "Accessories",
    price: 8999,
    oldPrice: 10999,
    rating: 4.9,
    image:
      "https://images.unsplash.com/photo-1523275335684-37898b6baf30?auto=format&fit=crop&w=700&q=80",
  },
  {
    id: 4,
    name: "Modern Travel Backpack",
    category: "Accessories",
    price: 3999,
    oldPrice: 4999,
    rating: 4.5,
    image:
      "https://images.unsplash.com/photo-1553062407-98eeb64c6a62?auto=format&fit=crop&w=700&q=80",
    badge: "Popular",
  },
  {
    id: 5,
    name: "Premium Running Shoes",
    category: "Fashion",
    price: 6499,
    oldPrice: 7999,
    rating: 4.7,
    image:
      "https://images.unsplash.com/photo-1542291026-7eec264c27ff?auto=format&fit=crop&w=700&q=80",
  },
  {
    id: 6,
    name: "Wireless Audio Headphones",
    category: "Electronics",
    price: 6999,
    oldPrice: 8999,
    rating: 4.6,
    image:
      "https://images.unsplash.com/photo-1484704849700-f032a568e944?auto=format&fit=crop&w=700&q=80",
  },
];

export const categories = [
  "All",
  "Electronics",
  "Fashion",
  "Accessories",
];
```

---

### Main page

```code
import Navbar from "@/app/components/Navbar";
import Hero from "./components/Hero";
import ProductSection from "./components/ProductSection";

export default function HomePage() {
  return (
    <main className="min-h-screen bg-white">
      {/* <Navbar cartCount={0} search="" onSearchChange={() => { }} /> */}
      <Hero />
      <ProductSection />

      <section className="bg-slate-950 px-5 py-12 text-center text-white">
        <h2 className="text-2xl font-bold">
          Shopping made simple.
        </h2>
        <p className="mt-3 text-sm text-slate-400">
          Discover your favorites with ShopEase.
        </p>
      </section>

      <footer className="border-t border-slate-100 px-5 py-6 text-center text-sm text-slate-500">
        © 2026 ShopEase. All rights reserved.
      </footer>
    </main>
  );
}
```















<br/>



