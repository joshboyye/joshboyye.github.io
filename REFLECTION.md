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



**A logic error the AI made that I fixed manually:**

AI coudn't help me to fix the css part where I want the style that I want so I looked up online how to use the function such as 
.skill-list since I wanted to make a fucntion to use it muitlpul times I created skill-list. 
