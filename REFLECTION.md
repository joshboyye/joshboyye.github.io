<<<<<<< HEAD
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
=======
# Homework 1 Reflection

## 1. The path of an HTTP request to my GitHub Pages site

When I type `https://your-username.github.io` into Chrome and hit Enter, this is roughly what happens:

1. **Parse the URL.** The browser splits it into the scheme (`https`), the host (`your-username.github.io`), and the path (`/`). It checks its cache first in case it already has the page or the IP address.
2. **DNS lookup.** The browser needs an IP address, not a name. It asks the OS, which asks a DNS resolver (usually my ISP's). If the resolver doesn't have it cached, it goes root server → `.io` servers → the nameservers for `github.io`, which return an IP address for GitHub Pages.
3. **TCP connection.** The browser opens a TCP connection to that IP on port 443 (the three-way handshake: SYN, SYN-ACK, ACK).
4. **TLS handshake.** Since it's HTTPS, the browser and server set up encryption first. GitHub sends a certificate for `*.github.io` and the browser checks it's valid before sending anything.
5. **HTTP GET request.** The browser sends a request like this (simplified):

   ```
   GET / HTTP/1.1
   Host: your-username.github.io
   User-Agent: Mozilla/5.0 ... Chrome/...
   Accept: text/html
   ```

6. **GitHub Pages finds my site.** GitHub Pages is served through a CDN, so the request usually hits a server close to me. Thousands of Pages sites share the same IP addresses, so the server uses the `Host` header to figure out which site I want. It maps it to my `your-username.github.io` repo, and since the path is `/`, it serves `index.html`.
7. **HTTP response.** The server sends back `200 OK` with headers like `Content-Type: text/html` and my HTML in the body.
8. **More requests.** While parsing the HTML, the browser finds `<link rel="stylesheet" href="style.css">`, the Google Fonts link, and `<img src="assets/profile.jpg">`, and sends a separate GET for each one. This is the same thing Full Stack Open part 0 shows, where loading the notes page triggers extra requests for `main.css` and `main.js`.
9. **Render.** The browser builds the DOM from the HTML and applies the CSS (this is where specificity decides which rules win), then lays out and paints the page.



## 2. AI attribution

I used gemini to give me some ideas of what I should do and helped me out to visulise what kind of code I should make then, AI helped me some of the css part since there were so many function to do css. 

**Prompt I used:**

> "Help me to deign the webiste I want to build for my cs class I do want something classic"
" Give me some css functions that can help me to build this website"

>>>>>>> 3eae65285bcaa45f670a3312e0c91e4a8a8e7ac4


**A logic error the AI made that I fixed manually:**

<<<<<<< HEAD
> AI helped me with a lof but it make some mistake by giving me wrong information about the html part 
> where I wanted my name to by the left hand side on the top correr but it didn't really help me with it. 
=======
AI coudn't help me to fix the css part where I want the style that I want so I looked up online how to use the function such as 
.skill-list since I wanted to make a fucntion to use it muitlpul times I created skill-list. 
>>>>>>> 3eae65285bcaa45f670a3312e0c91e4a8a8e7ac4
