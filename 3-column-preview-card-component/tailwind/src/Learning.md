# 📝 Frontend Mentor: 3-Column Preview Card - Learnings

**Project:** [Project Name or Frontend Mentor Challenge Link]
**Technology Used:** [e.g., Tailwind CSS, React, Vue, Vanilla JS]
**Date Started:** YYYY-MM-DD
**Date Completed:** YYYY-MM-DD


## 🔍 Problems I Faced
- Centering in the page and having background color at the back.

## Todo List
- write symentic html
- write colors as variables



### Learning
- check background-clip for background color
- learn about minmax grid, which was applied on main tag
- why to give line-height to headings

---


### Learning 1: Defining and Using CSS Custom Variables in Tailwind CSS v4
I defined custom CSS variables in Tailwind v4 using `@theme` to create utilities like bg-sunset, text-transparent-white, font-lexend, and text-body (15px font size). Initially, text-body failed because I used --font-size-body instead of the correct --text-body namespace. I fixed this by using --text-body, applying text-body in HTML (e.g., <p class="font-lexend text-body text-transparent-white">), and rebuilding with npx tailwindcss -i styles.css -o output.css. *Key Takeaway*: The --text-* namespace is critical for font size utilities in Tailwind v4, and utilities must be used in HTML to avoid purging.

---


@utility debug-border	- Integrates with Tailwind’s utilities layer.
- Supports variants (e.g., hover:debug-border, lg:debug-border).
- Consistent with Tailwind’s utility-first philosophy.
- Purges automatically if unused.	- Permanent utility in output.css unless removed.
- 	Useful if you want variants (e.g., hover:debug-border) for debugging specific interactions or breakpoints.
---

rounded-lg is purely cosmetic, but it doesn't force children to obey the new shape. Use overflow-hidden to clip any overflowing content, so it matches the rounded shape visually.

---
class="flex-1"
is a shorthand for:


flex-grow: 1;
flex-shrink: 1;
flex-basis: 0%;
This means the item will:

Grow to fill the container

Shrink when needed

Start from zero base size

✅ When to Use flex-1
Use flex-1 when:

You want equal-width items in a flex row or column

You want one item to take all remaining space

You want responsive layouts without hardcoding widths

---


The flex-1 class has no effect in your current code because the parent container of the <article> elements (<section class="flex flex-col ...">) is set to flex-col, i.e., a vertical flex direction — and by default, block-level elements like <article> already expand to fill their parent's width.
But unless the section itself has a fixed height, there's no "remaining height" to distribute — so flex-1 has nothing to work with.

---
💡 When using flex-1, you only need to set the width on the parent, and the children will automatically divide up the space equally, no matter what the parent’s width is.

flex-1->	Equal width among siblings in flex row
grow-[2]->	Grows twice as much as flex-1 siblings
basis-0->	Forces them to ignore natural content size

---

