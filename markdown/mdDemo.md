# Demo

Author: Zhaojiacheng Zhou

Description: Demo doc for markdown grammar.

---

## Headers

# This is Header 1

## This is Header 2

### This is Header 3

#### This is Header 4

##### This is Header 5

###### This is Header 6

####### There is no Header 7

## Text Formatting

You can use \_ or \* to control the text format. E.g.

_Italic_, _Italic_, **Bold**, **Bold**, **_Italic&Bold_**, **_Italic&Bold_**

You can also mix start and underscore though it is not recommended. _**Italic&Bold**_, _**Italic&Bold**_, _**Italic&Bold**_, but mixing star and underscore won't take effect *\_*Italic&Bold*\_*.

## Hyperlink

Here is demo for hyper link

[baidu](https://www.baidu.com)

You can also create link in the doc like

[Title](#demo)

You can create a toc(table of content) by extension markdown all in one automatically and do some customization.

Type ctrl shift p or command shift p and enter `table of contents`, vscode will automatically generate a toc for you.

## Photos

You can insert photos to the markdown document like:

![foo](src/wave.png)

Markdown also support some html grammar to create more complex layout.

<div style="display: flex; justify-content: center;">
  <img src="src/yes.png" alt="Image 1" style="width: 10%; margin-right: 30%;" />
  <img src="src/no.png" alt="Image 2" style="width: 10%;" />
</div>

<div style="display: flex; justify-content: center;">
  <img src="src/meow_photo.gif" alt="Image 2" style="width: 10%;" />
</div>

## Block Citation

Use `>` to create block citation.

For example:

Prof. Manuel once said:

> Deduction will follow!

You can create double quotation like using `>>`

E.g.

> ZZJC claims on VSCode Wksp that Prof. Manuel once said:
>
> > Deduction will follow!

## List

List is sth. can record your idea in a neat way.

Plz don't write a list like essay, it may lead to heavy deduction :)

### Unorderer List

Here is a list of editors:

- VSCode
- Vim
- Neovim
- Emacs

To create sublist you can watch the following demo

How to configure the editors

- Vscode
  - Json
- VIM
  - Vimscript
- Neovim
  - Vimscript
  - Lua
- Emacs
  - Emacs lisp

### Orderered List

Orderered List is quite similar to the unordered list

1. Open vscode
2. Write some code
3. Save
4. Quit

OR

1. Open vscode

   1. Open your terminal
   2. cd to your target dir
   3. Open vscode with command:

      `code .` for windows user, `vs .` for macos and linux user with plugin vscode

2. Write some code
   1. Write macro
   2. Write function
   3. Write main
3. Save
4. Quit

## Table

| Name | ID  | Age |
| ---- | --- | --- |
| A    | 0   | ??? |
| B    | 1   | !!! |

You can set align for the table with :

Left align

| Name | ID  | Age |
| :--- | :-- | :-- |
| A    | 0   | ??? |
| B    | 1   | !!! |

Right align

| Name |  ID | Age |
| ---: | --: | --: |
|    A |   0 | ??? |
|    B |   1 | !!! |

Center align

| Name | ID  | Age |
| :--: | :-: | :-: |
|  A   |  0  | ??? |
|  B   |  1  | !!! |

## Emoji

Use `:white_mark_button:` for :white_check_mark:

Search on [Emojipedia](https://emojipedia.org/) for more.

## Paragraph

Sometimes you write paragraph like: foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo. (P1)

Sometimes you write paragraph like: foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo foo. (P2)

However, sometimes we may want style like

foooo1  
foooo2  
foooo3

You can do so by add 2 \<Space\> at the end of the line.

## Code

Sometimes you may want add some code in your readme (search on github for examples). If you want to insert code in line, you can use \` . eg. `gcc test.cpp -o test`. Or you can insert a code block like

```c
#include <stdio.h>

int main()
{
  printf("Markdown\n");
  return 0;
}
```

And you can see the highlight of code.

## Formula

Markdown has built Katex support so that we can insert some math formula. e.g. $\displaystyle \sum_{i=0}^{n} i$

OR

$$
\begin{pmatrix}
   a & b \\
   c & d
\end{pmatrix}
$$

## Split

Use `---` to create split.

---

This is a split line.

## Comments

You can comment the FOO by `<!-- FOO -->` <!-- FOO -->

Demo for multilines

<!--
Foo1
Foo2
Foo3
-->
