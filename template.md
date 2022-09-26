# The Title: It will be commented out in the generated HTML but should be provided to marketing so they can set the post title

----

# tl;dr

Write your markdown and run:

```
pandoc -t json template.md | python3 ./pandoc.py html | pandoc -f json -t html -o template.html
```

# First Section

This is some text and stuff. Lorem ipsum is fine for filling space but it
doesn't self document like this template does. But pretty much everything
is vanilla markdown unless otherwise noted. Even references[^1] work.[^2]

***Note:*** That thing above the first section is a line spacer. They look nice. Use them.

[^1]: Look, it's a <https://www.nccgroup.trust/us> link!
[^2]: Another reference!

## Subsection

Et voila!

### SubSubSection

_bwongggg!_

#### Inception

Four! Count them. A four-levels deep sub-sub-sub-section.
You should try to stick to three though.

# Section Section: Equilibrium

If you want to link to a section, you just put in a link like
[this](#section-four-breakdown) that's named exactly after a
(sub)*section, but replacing the spaces with hyphens and removing special
characters. It's time to get listy:

1. One
1. Two
    * a
    * b
        1. one
        1. two
        * a
        * b
    * c
1. Three
    1. one
    2. two
    3. three

* A
    * a
    * b
* B
    1. one
    1. two
* C

# Section Three: Code Snippets

The standard GitHub/GitLab formatting applies.

If you want vanilla terminal output, don't set a language, or use `txt`.

```
$ # testing 1, 2, 3
$ ./exploit 0xffffff
# whoami
root
```

However, if you want to just have your terminal output highlighted, use `console`.
When you do, you'll need to replace `#` with `$$` for root shell prompts if you don't want the line commented out.

```console
$ # testing 1, 2, 3
$ ./exploit 0xffffff
$$ whoami
root
```

```bash
#!/bin/sh

read -r SANITIZER <<"EOF"
s/'/'\\''/g
EOF

ESCAPED=`echo "${1}" | sed "${SANITIZER}"`

echo "echo '${ESCAPED}'"
/bin/sh -c "echo '${ESCAPED}'"
```

```C
#include <stdio.h>

int main(int argc, char** argv) {
  puts("hello");

  return 0;
}
```

You can also use the `` ```{.langname} `` syntax if you want as long as the name is the first one listed.

```{.c}
#include <stdio.h>

int main(int argc, char** argv) {
  puts("hello");

  return 0;
}
```

# Section Four: Breakdown

Sometimes, you might have a lot of content that doesn't need to be seen 100%
of the time, and takes up a bunch of page space to scroll through it.

You can use the GitLab/GitHub-style `<details>` tag to make collapsible
sections.

<details><summary>Summary Text</summary>

```
                    `.------.`
               ./oshhhhhhhhhhhhso/-
           `:oyhhhhhhhhhhhhhhhhhhhhyo:`
         `+yhhhhhhhhhhhhhhhhhhhhhhhhhhy+`
       `/hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh+`
      .yhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhy+
     -yhhhhhhhhhhhhhhhhhhhhhhy+:-.``..-..
    .yhhhhhhhhhhhhhhhhhhhhho.     ``
    shhhhhhhhhhhhhhhhhhhhh:  `:oys:`
   -hhhhhhhhhhhhhhhhhhhhy- .ohhy:    .-:::-.
   +hhhhhhhhhhhhhhhhhhho.`+hhh+`  :shhhhhhhhhs:
   ohhhhhhhhhhhhhhhyo/..+yyo:`   `..-:/osyys+-
   +hhhhhhyo+++:-----....`  `-:::-`
   -hhhhyssyhysyhhhhhho- ./shhhhhhhys+:.
    shysoo++/+ossso+:`./shhhhhhhhhhhhhhhhyssyy
    .yhhhhhhhyso+++osyhhhhhhhhhhhhhhhhhhhhhhh-
     -yhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh-
      .yhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhy.
       `/hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh+`
         `+yhhhhhhhhhhhhhhhhhhhhhhhhhhy+.
           `:oyhhhhhhhhhhhhhhhhhhhhyo:`
               -/oshhhhhhhhhhhhso/-
                    `.--::--.`
```

</details>

You can also embed them in lists.

1. Hello

1. World.

<details><summary>Summary Text</summary>

```
                    `.------.`
               ./oshhhhhhhhhhhhso/-
           `:oyhhhhhhhhhhhhhhhhhhhhyo:`
         `+yhhhhhhhhhhhhhhhhhhhhhhhhhhy+`
       `/hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh+`
      .yhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhy+
     -yhhhhhhhhhhhhhhhhhhhhhhy+:-.``..-..
    .yhhhhhhhhhhhhhhhhhhhhho.     ``
    shhhhhhhhhhhhhhhhhhhhh:  `:oys:`
   -hhhhhhhhhhhhhhhhhhhhy- .ohhy:    .-:::-.
   +hhhhhhhhhhhhhhhhhhho.`+hhh+`  :shhhhhhhhhs:
   ohhhhhhhhhhhhhhhyo/..+yyo:`   `..-:/osyys+-
   +hhhhhhyo+++:-----....`  `-:::-`
   -hhhhyssyhysyhhhhhho- ./shhhhhhhys+:.
    shysoo++/+ossso+:`./shhhhhhhhhhhhhhhhyssyy
    .yhhhhhhhyso+++osyhhhhhhhhhhhhhhhhhhhhhhh-
     -yhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh-
      .yhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhy.
       `/hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh+`
         `+yhhhhhhhhhhhhhhhhhhhhhhhhhhy+.
           `:oyhhhhhhhhhhhhhhhhhhhhyo:`
               -/oshhhhhhhhhhhhso/-
                    `.--::--.`
```

</details>

# Images

Images are great, but WordPress strips out data: URIs from img src attributes, and also removes a bunch of inline CSS style values (not to mention `<style>` elements).
You can hotlink them.

```
![](https://www.nccgroup.com/static-a/img/logos/logo-nccgroup-blue.svg)
```

![](https://www.nccgroup.com/static-a/img/logos/logo-nccgroup-blue.svg)

...but we also have a workaround using CSS escapes to load in base64 data URIs.

```
It is a mystery. <div style="background: url('\64\61\74\61\3a\69\6d\61\67\65\2f\70\6e\67\3b\62\61\73\65\36\34\2c iVBORw0KGgoAAAANSUhEUgAAABoAAAAXCAIAAACatshHAAAACXBIWXMAAAsTAAALEwEAmpwYAAAApUlEQVQ4y8WUSQ7AIAhF4cf7X5kubA1ODMakrFD5T6BUFhG6Z8U+ZuZ508ig2KylcrdPRHBZzFxzbI6ILLO2cDO0OUY8UmXq9i25cLs%2bFDhfo4VdLfrAHaAWXIUvRy9s5RAzqOoSuhD+zB3X4Vt32c23RfJdBiPerF2Z2kdqDlxDVmD3AalBdXsKumr/4dxKE7gIK4oLsqLPZ2LCd8/3wd+yxR3bAyjQhzmpM0GfAAAAAElFTkSuQmCC') no-repeat;">&nbsp;</div>
```

It is a mystery. <div style="background: url('\64\61\74\61\3a\69\6d\61\67\65\2f\70\6e\67\3b\62\61\73\65\36\34\2c iVBORw0KGgoAAAANSUhEUgAAABoAAAAXCAIAAACatshHAAAACXBIWXMAAAsTAAALEwEAmpwYAAAApUlEQVQ4y8WUSQ7AIAhF4cf7X5kubA1ODMakrFD5T6BUFhG6Z8U+ZuZ508ig2KylcrdPRHBZzFxzbI6ILLO2cDO0OUY8UmXq9i25cLs%2bFDhfo4VdLfrAHaAWXIUvRy9s5RAzqOoSuhD+zB3X4Vt32c23RfJdBiPerF2Z2kdqDlxDVmD3AalBdXsKumr/4dxKE7gIK4oLsqLPZ2LCd8/3wd+yxR3bAyjQhzmpM0GfAAAAAElFTkSuQmCC') no-repeat;">&nbsp;</div>

***Note:*** Pandoc seems to escape the single quotes by default, which causes WordPress' CSS mangler to ruin the input.
We get around this with some magic in the custom Pandoc filter script, but we also support a simple shorthand for file URI images.

```
It is a mystery. ![](file://mystery.png)
```

It is a mystery. ![](file://mystery.png)

However, due to the limitations of wordpress, getting the image to show up on the same requires some... "low-level" handling.


```
<span style="float: left;">It is a mystery.</span><span style="background: url('\64\61\74\61\3a\69\6d\61\67\65\2f\70\6e\67\3b\62\61\73\65\36\34\2c iVBORw0KGgoAAAANSUhEUgAAABoAAAAXCAIAAACatshHAAAACXBIWXMAAAsTAAALEwEAmpwYAAAApUlEQVQ4y8WUSQ7AIAhF4cf7X5kubA1ODMakrFD5T6BUFhG6Z8U+ZuZ508ig2KylcrdPRHBZzFxzbI6ILLO2cDO0OUY8UmXq9i25cLs%2bFDhfo4VdLfrAHaAWXIUvRy9s5RAzqOoSuhD+zB3X4Vt32c23RfJdBiPerF2Z2kdqDlxDVmD3AalBdXsKumr/4dxKE7gIK4oLsqLPZ2LCd8/3wd+yxR3bAyjQhzmpM0GfAAAAAElFTkSuQmCC') no-repeat; float: left; width: 40px;">&nbsp;</span><br>
```

<span style="float: left;">It is a mystery.</span><span style="background: url('\64\61\74\61\3a\69\6d\61\67\65\2f\70\6e\67\3b\62\61\73\65\36\34\2c iVBORw0KGgoAAAANSUhEUgAAABoAAAAXCAIAAACatshHAAAACXBIWXMAAAsTAAALEwEAmpwYAAAApUlEQVQ4y8WUSQ7AIAhF4cf7X5kubA1ODMakrFD5T6BUFhG6Z8U+ZuZ508ig2KylcrdPRHBZzFxzbI6ILLO2cDO0OUY8UmXq9i25cLs%2bFDhfo4VdLfrAHaAWXIUvRy9s5RAzqOoSuhD+zB3X4Vt32c23RfJdBiPerF2Z2kdqDlxDVmD3AalBdXsKumr/4dxKE7gIK4oLsqLPZ2LCd8/3wd+yxR3bAyjQhzmpM0GfAAAAAElFTkSuQmCC') no-repeat; float: left; width: 40px;">&nbsp;</span><br>

***Note:*** The Pandoc filter handler only recognizes these constructions for `div` and `span` when the `style` attribute starts with `background: url('`.
