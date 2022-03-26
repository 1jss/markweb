```
   _     _
 _| |   | |_
|_   \_/   _|
  | |\_/| |
 _| |   | |_
|_  |   |  _|
  |_|   |_|
```
# MarkWeb
MarkWeb is a less distracting alternative to the modern web

## Manifesto
* MarkWeb is lightweight and intends to stay so
* In MarkWeb websites are written in `markdown`
* MarkWeb websites should be readable without javascript
* MarkWeb browsers only *need* to understand `markdown`

## First steps
I've created a minimal [demo website](https://1jss.github.io/markweb/) where all the content is written in `markdown`, but gets parsed to `HTML` if the browser has javascript enabled. If not, the user sees an unstyled markdown website that can be read even in the simplest terminal web browser. See code below:

```html
<html>
 <head>
  <title>MarkWeb</title>
 </head>
 <body>
<pre id="markdown">
## Markdown Content
**All** the *common* [markdown](https://en.wikipedia.org/wiki/Markdown) ~~text~~ formatting ***works***!
</pre>
 <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script><!-- Include markdown parser -->
 <script>
  /* Replaces <body> content (including the parser) with parsed markdown from the element with the id "markdown" */
  document.body.innerHTML = marked.parse(document.getElementById("markdown").innerText.toString())
 </script>
 </body>
</html>
```

## Logo
The MarkWeb logo consists of a broken hashtag (used for headings in markdown). It also resembles a dancing couple.
![MarkWeb Logo](./markweb.svg)

## Other initiatives
I've been pondering this idea for quite some time but got to it again as I read Garrett Albrights piece on [KyuWeb](https://github.com/GarrettAlbright/KyuWeb). I think it was an inspiring text, but I frankly don't like (1) the name KyuWeb and (2) the focus on CommonMark. My demo website above somewhat implements Albrights "HTML-wrapped Markdown documents" but opts out on the `<!-- KyuWeb Doc Start /-->` tag. I'd much rather have a more generic `<!-- markdown start /-->` tag instead.
