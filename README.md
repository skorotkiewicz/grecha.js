# Grecha.js

![KashaHard](KashaHard.gif)

Simple Front-End JavaScript Framework. Originally designed for [emoteJAM](https://github.com/tsoding/emoteJAM). The name basically means [buckwheat](https://en.wikipedia.org/wiki/Buckwheat) in russian.

## Quick Start

https://tsoding.github.io/grecha.js/example.html

```html
<!DOCTYPE html>
<html>
  <head><title>Grecha.js</title></head>
  <body>
    <div id="entry"></div>
    <script src="./grecha.js"></script>
    <script>
      const kasha = img("Kasha.png");
      const kashaHard = img("KashaHard.gif");

      let count = 0;
      let hard = false;
      const r = router({
        "/": () => div(
          h1("Grecha.js"),
          div(a("Foo").att$("href", "#/foo")),
          div(a("Bar").att$("href", "#/bar")),
          div(a("Something").att$("href", "#/something-notfound")),
          div("Counter: "+count),
          div(hard ? kashaHard : kasha).onclick$(function () {
            count += 1;
            hard = !hard
            r.refresh();
          }),
        ),
        "/foo": () => div(
          h1("Foo"),
          p(LOREM),
          div(a("Home").att$("href", "#")),
        ),
        "/bar": () => div(
          h1("Bar"),
          p(LOREM),
          div(a("Home").att$("href", "#"))
        ),
        "/404": () => div(
          h1("404 Not Found"),
          p("The page you are looking for does not exist."),
          div(a("Home").att$("href", "#"))
        ),
      });
      entry.appendChild(r);
    </script>
  </body>
</html>
```
