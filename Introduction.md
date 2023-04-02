# Introduction

> TailwindCSS is a utility-first CSS framework packed with classes that can be composed to build any design, directly in your markup.

That's a lot of words to take in, isn't it? That's how TailwindCSS is defined by the official documentation.

[Tailwindcss Documentation](https://tailwindcss.com/docs/installation) is excellent and should serve as your go-to manual for anything Tailwindcss. But its top-down structure, i.e. covering the high-level concepts first and then drilling down to the basics may intimidate people new to it.

In this series, we will take a bottom-up approach where we'll learn the rudimentary details in an opinionated structure and progress gradually to the high-level concepts. This helps in avoiding cognitive overload. Imagine having to write an essay on Shakespeare without knowing what the alphabets are!

I'll assume you have a basic working knowledge of CSS. If you want a refresher or are completely new to CSS and want to learn, you can do so with these excellent linked resources before hopping right back here to continue your journey towards mastering TailwindCSS.

1. [Learn CSS - web.dev](https://web.dev/learn/css/)
    
2. [Learn to style HTML using CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS)
    

---

# Classes

TailwindCSS is built on classes. We design by combining different classes. And what's more? TailwindCSS is clever enough to only include the styles for the classes we've used - which means faster load times, yay!

Let's take a quick look at what classes are.

The syntax of a class is as follows.

```css
.className { /* It starts with a period followed by the class name */
   propertyName: proptertyValue;
   ....
   ....
}
```

A class is a way to combine different CSS properties and values under a single name. We can then apply all those styles to elements using the `class` attribute (or `className` attribute if you're working with React/JSX).

It is important to note we can add as many classes as we want, separated by a space and styles will be applied after rules of [specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity) are taken into consideration.

```xml
<div class="className anotherClassName"></div>
```

---

We now know the building blocks of TailwindCSS. It's just a bunch of different classes doing different things which when combined correctly can result in a beautiful design without having to write any of our own CSS.

Starting from the next article of the series, we will deep dive into the beautiful world of TailwindCSS and get some hands-on experience with its classes.