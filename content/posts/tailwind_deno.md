+++
title = "Import custom fonts with Tailwind CSS fresh"
date = "2024-09-22"

[taxonomies]
tags=["deno", "tailwind"]
+++
# Prologue

I was working in a project that used [deno](https://deno.com/) as javascript runtime alongside [fresh](https://fresh.deno.dev/) as web framework. And I couldn't find easly how to import a front.

## Prerequisites
This post assumes you are working on a fresh project and use Tailwind CSS for styling library. 
### 1. Find Your Font


To choose your font you can go to [Google Fonts](https://fonts.google.com) and search the one you want, for the sake of this tutorial we will be looking for the [Fredoka](https://fonts.google.com/?query=fredoka) font.
### 2. Get the Embed Code

Once you have chosen your font:
- Click on the font.
- Hit the `Get font` then `Get embed code` button
- Navigate to the "Get embed code" section
- Select `@import`.
- Copy the `@import url('https::/fonts/googleapis.com ... display=swap');` code  snippets

### 3. Edit tailwind configuration

Open your `tailwind.config.ts` file and add the following:

```typescript
import { type Config } from "tailwindcss";

export default {
  content: [
    "{routes,islands,components}/**/*.{ts,tsx}",
  ],
  theme: {
    extend: {
      fontFamily: {
        'fredoka': ['"Fredoka"', 'sans-serif'],
      },
    },
  },
  plugins: [],
} satisfies Config;
```


### 4. Import the Font

Finally, open your `styles.css` file and add the following line:

```css
@import url('https://fonts.googleapis.com/css2?family=Fredoka&display=swap');
```



## Conclusion

You now can add your font to you tsx 🚀!