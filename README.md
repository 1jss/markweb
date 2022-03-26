# ![MarkWeb Logo](./markweb.svg)

# MarkWeb
MarkWeb is a less distracting alternative to the modern web

## Manifesto
* MarkWeb is lightweight and intends to stay so.
* In MarkWeb websites are written in `markdown`.
* MarkWeb websites should be readable without javascript.
* MarkWeb browsers only *need* to understand `markdown`.

## First steps
I've created a minimal [demo website](https://1jss.github.io/markweb/) where the content is written in `markdown`, but gets translated to `HTML` if the browser has javascript enabled. If not, the user sees an unstyled markdown website that can be read even in the simplest terminal web browser. See code below:

```
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
  document.body.innerHTML = marked.parse(document.getElementById("markdown").innerText.toString())
  /* Replaces <body> content (including the parser) with parsed markdown from the element with the id "markdown" */
 </script>
 </body>
</html>
```

## Other initiatives
I've been pondering this for quite some time but got to it again as I read Garrett Albrights piece on [KyuWeb](https://github.com/GarrettAlbright/KyuWeb).
