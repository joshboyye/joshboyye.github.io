# Homework 2 Reflection

Joshua Wang
CSCI 39548: Practical Web Development

## 1. `flex-direction: row` vs. `flex-direction: column`

`flex-direction` decides which way a flex container lays out its children. That direction is called the main axis.

- **`row`** is the default. The main axis goes left to right, so the items sit next to each other.
- **`column`** makes the main axis go top to bottom, so the items stack on top of each other.

It also changes what the alignment properties do. `justify-content` always works along the main axis and `align-items` works across it. So in a row, `justify-content` moves things left and right. In a column, it moves things up and down.

## 2. Why use relative units instead of fixed pixels?

A pixel value is the same size on every screen. If I make a box `1200px` wide it fits on a laptop, but on a phone that is only 375px wide it goes off the side and you have to scroll sideways. Relative units are based on something else, so they change with the screen.

This means one rule can work on a phone, a laptop, and a big monitor, so I need fewer media queries. If someone makes the default font size bigger in their browser settings, sizes in `rem` grow with it, but sizes in `px` do not.

In my site the projects section is `width: 90%`, the hero is `min-height: 50vh`, the grid is `repeat(3, 1fr)`, and my font sizes and most of my padding are in `rem`. I still used `px` for small things like borders and rounded corners, for `max-width: 1100px` so the page does not get too wide, and for the 768px breakpoint.

## 3. AI Attribution

I used gemini for helping me with the the html function part where it will be eaiser to use. 

**Prompts I used:**

1. how to make a card section on css to put words in it? 
2. > how to make the click function and make the click function to the other page on the website?


**A logic error the AI made that I fixed manually:**

> AI helped me with a lof but it make some mistake by giving me wrong information about the html part 
> where I wanted my name to by the left hand side on the top correr but it didn't really help me with it. 
