# Code practice for reference.

## 1.	Arbitrary Values

An arbitrary value lets you use a value that Tailwind doesn't provide as a standard utility.

```<div className="w-[420px]"> Content </div>```

## 2.	Arbitrary Properties

Arbitrary properties allow you to write a CSS property directly inside a Tailwind class.

```<div className="[scrollbar-width:none]">
  Content
</div>
```

## 3. Arbitrary Variants

Arbitrary variants allow you to create a custom selector directly.

```
<div className="[&>p]:text-gray-600">
  <p>Paragraph 1</p>
  <p>Paragraph 2</p>
</div>
```

```&``` represents the current element.

This means approximately:

```
<div className="[&_a]:text-blue-600">
  <a href="#">Link 1</a>
  <a href="#">Link 2</a>
</div>
```

**Hover child**

```
<div className="[&_button:hover]:bg-blue-700">
  <button>
    Save
  </button>
</div>
```
