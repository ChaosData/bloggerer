# Blog Post Template and Tooling

This repo holds a documented template Markdown blog post and a Pandoc filter
script that generates better-looking HTML than WordPress' own Markdown handling.

```
$ sudo apt-get install pandoc highlight
$ pip3 install --user panflute
$ pip3 install --user pillow
$ pandoc -t json blog.md | python3 path/to/this/repo/pandoc.py html | pandoc -f json -t html -o blog.html
```

The resulting HTML should be copied into a WordPress "Custom HTML" block.

## Features

* Handles footnotes properly

* Proper code-block formatting and syntax highlighting
    * Handled by `highlight` (https://gitlab.com/saalen/highlight)

* Support for images

## FAQ

* Why is the first top level heading removed from the HTML?
    * The first top-level heading is typically the title, this is handled by wordpress.

