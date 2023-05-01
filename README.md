# ⛵ Jibe CSS

**A teeny tiny CSS Custom Property framework based on Tailwind.**

With Custom Properties and CSS modules, CSS is suddenly very easy
to tame!


## Example usage

```jsx
// button.jsx
import styles from 'button.module.css'

function Button({ children }) {
    return (
        <button className={styles.button}>
            {children}
        </button>
    )
}
```

```css
/* button.module.css */

.button {
    height: var(--size-10);
    padding: 0 var(--size-6);
    font-weight: var(--font-semibold);
    border-radius: var(--radius-md);
    border: 1px solid var(--color-slate-200);
    color: var(--color-slate-900);
}
```


## How it works

1. Import jibe.css into your project.
2. Modify it to customize semantic styles, for example:

   ```css
   :root {
     --color-primary: var(--color-blue-500);
   }
   ```

3. In your project, use the variables from
   [jibe.css](https://github.com/tvst/jibe-css/blob/main/jibe/jibe.css)
   (preferably) and
   [jibe-base.css](https://github.com/tvst/jibe-css/blob/main/jibe/jibe-base.css)
   (as a fallback).


## API Reference

This framework is just a bunch of CSS Custom Properties. So just look at
[jibe.css](https://github.com/tvst/jibe-css/blob/main/jibe/jibe.css) and
[jibe-base.css](https://github.com/tvst/jibe-css/blob/main/jibe/jibe-base.css)
to see the properties that are available.


## Why not just use Tailwind?

Tailwind is awesome, and I use it all the time. I built this because
I was working on a project where the component framework
([Ark](https://github.com/chakra-ui/ark)) required the use of actual
CSS files for styling things like selected states.

My initial reaction was "Great, I'll just use Tailwind's @apply!" --
except that the app framework we were using
([Remix](https://remix.run/)) didn't support @apply inside CSS modules
out of the box, and it wasn't easy to add support.

So I built this 😃


## Reasons you may want to use Jibe

1. You're one of those people who are just averse to utility classes.
1. You want to write code that anyone who knows CSS can just pick
   up and immediately understand.
1. You want to write framework-agnostic components.
1. You want to make it easy for users to change the colors of
   your web site / web app.

   How? Just overwrite the semantic CSS variables from jibe.css using JS:

   ```js
   const root = document.documentElement;
   root.style.setProperty('--color-primary', 'var(--color-red-500)');
   root.style.setProperty('--color-secondary', 'var(--color-pink-500)');
   ```
