# 1. Fonts

Text is ubiquitous on the web. Websites must have a legible and appropriate font that suits their target audience. Styling the text to indicate the importance or to provide an emphasis helps in the readability of the website.

# Font Family

The CSS property `font-family` takes a list of font family names that the browser will use to render the text based on font availability.

In general, font families can be broadly categorized into:

* Serif fonts - Fonts that help improve readability in non-screen texts like in newspapers.
    
* Sans serif fonts - Fonts that help improve readability in screen texts like on a PC or a Macbook or even Androids and iPhones.
    
* Monospace fonts - Fonts that help improve readability in code.
    

TailwindCSS offers classes for all these font types - `font-serif`, `font-sans`, `font-mono` respectively.

If you want a one-off font family for a particular text, we can do so by specifying an arbitrary font family name within `[]` after `font-`

```css
font-['Impact'] becomes font-family: 'Impact';
/* Spaces to be replaced with _ and use quotes like below */
font-['Times_New_Roman'] becomes font-family: 'Times New Roman';
```

## Theming

TailwindCSS can be themed using `tailwind.config.js` The Font Family can be themed using `theme.extend.fontFamily` object. You can either override `sans`, `serif`, and `mono` if you want to continue using `font-sans`, `font-serif`, `font-mono` or if you want to include your own `font-{suffix}` you can do so too by specifying the `suffix` as key in `theme.extend.fontFamily` and value of type `String | String[]`

```javascript
// Overriding 'font-sans' with String[] format
'sans': ['Helvetica', 'Arial', 'sans-serif'],

// Creating 'font-brand' with String format
'brand': 'Helvetica, Arial, sans-serif',
```

In the below example, I add a `font-fancy` class which will use `cursive` font family.

```javascript
// tailwind.config.js
module.exports = {
  theme: { 
    extend: {
      fontFamily: {
        'fancy': 'cursive',
      }
    }
  }
}
```

Now let us put everything we've learned so far into action:

```xml
<p class="font-sans">Font Sans - The quick brown fox jumps over the lazy dog</p>
<p class="font-serif">Font Serif - The quick brown fox jumps over the lazy dog</p>
<p class="font-mono">Font Mono - The quick brown fox jumps over the lazy dog</p>
<p class="font-['Impact']">Arbitrary font Impact - The quick brown fox jumps over the lazy dog</p>
<p class="font-fancy">Font Fancy - The quick brown fox jumps over the lazy dog</p>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1680415481925/08020467-84ef-41a0-9709-9cf3e2460702.png align="center")

## Customizing Default Font

By default, TailwindCSS's default theme Preflight's \`font-sans\` will be applied to the `html` element.

To have a different default font, you can either

1. Override `font-sans` in `theme.fontFamily`
    
2. Override it explicitly like below (don't worry about `@layer base` stuff for now, it will be covered in one of the articles later. Technically you can get away by not using it but it is the best practice, the "why" of it will be covered later).
    
    ```css
    @layer base {
      html {
        font-family: Roboto, system-ui, sans-serif;
      }
    }
    ```
    

---

# Font Size

The CSS property `font-size` sets the size of the font. Essentially, it lets you tell the browser how big you want your font to be displayed.

TailwindCSS has several in-built sizes which take the form `text-{size}` where `size` can be `xs, sm, base, lg, xl, 2xl, 3xl, 4xl, 5xl, 6xl, 7xl, 8xl, 9xl`

We can also set an arbitrary value if required. Let's say we want our `font-size` to be `150px`, we can set it as `text-[150px]`

## Theming

We can theme the font sizes through `theme.extend.fontSize` object. Like with font family, we can override the existing built-in presets like `base` or add a completely new preset like `huge`

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      fontSize: {
        base: '15px', // overriding 'font-base'
        huge: '50px' // creating 'font-huge' with font-size: 50px;
      }
    }
  }
}
```

Let us now see all that we've learned in action

```xml
<p class="text-xs">Text Extra Small</p>
<p class="text-sm">Text Small</p>
<p class="text-base">Text Base/Regular</p>
<p class="text-lg">Text Large</p>
<p class="text-xl">Text Extra Large</p>
<p class="text-2xl">Text 2xl</p>
<p class="text-3xl">Text 3xl</p>
<p class="text-4xl">Text 4xl</p>
<p class="text-5xl">Text 5xl</p>
<p class="text-6xl">Text 6xl</p>
<p class="text-7xl">Text 7xl</p>
<p class="text-8xl">Text 8xl</p>
<p class="text-9xl">Text 9xl</p>
<p class="text-huge">Text Huge</p>
<p class="text-[150px]">150px Text</p>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1680419642874/80d080f6-a475-451a-af44-27d26ab9cbbf.png align="center")

---

## Font Style

There are only two classes - `italic` and `non-italic` with the latter used to reset `italic` at different breakpoints or states which we'll see later.

```xml
<p class="non-italic">Non italic</p>
<p class="italic">Italic</p>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1680419968579/6b743db9-ab8a-4ef4-a1d6-8b7f0ea7ff79.png align="center")

---

## Font Weight

| Class Name | Font Weight |
| --- | --- |
| font-thin | 100 |
| font-extralight | 200 |
| font-light | 300 |
| font-normal | 400 |
| font-medium | 500 |
| font-semibold | 600 |
| font-bold | 700 |
| font-extrabold | 800 |
| font-black | 900 |
| font-\[1100\] (arbitrary value) | 1100 (arbitrary value) |

Arbitrary font-weights like `font-[1100]` are only applicable if the font supports it. Let us see the different font weights in action.

```xml
<p class="font-thin">Font Thin - 100</p>
<p class="font-extralight">Font Extra Light - 200</p>
<p class="font-light">Font Light - 300</p>
<p class="font-normal">Font Normal - 400</p>
<p class="font-medium">Font Medium - 500</p>
<p class="font-semibold">Font Semibold - 600</p>
<p class="font-bold">Font Bold - 700</p>
<p class="font-extrabold">Font Extra Bold - 800</p>
<p class="font-black">Font Black - 900</p>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1680420324417/51092f24-dff2-47ea-83cc-4de215541115.png align="center")

## Theming

Like others, you can theme font weight by `theme.extend.fontWeight` object. You can

1. Override existing font-weight presets like `'thin': '200'`
    
2. Create a new font-weight preset like `'thick': '900'`
    

---

# Advanced

There are some rare-use cases where you might need to use Font Smoothing and Font Variant Numeric. It is left as an additional reading or an exercise.

---

# Code

To make it easier to follow the series, I've created a Github Repository at [AmitJoki/Learn-Tailwindcss](https://github.com/AmitJoki/Learn-Tailwindcss)

The code used in this article can be found [here.](index.html)