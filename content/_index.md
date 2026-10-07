
+++

title = "Guide for writing markdown slides"
description = "A Hugo theme for creating Reveal.js presentations"
outputs = ["Reveal"]
aliases = [
    "/guide/"
]

+++

{{% accentify "top-left" %}}
Today's date! `{{% today %}}`
{{% /accentify %}}

# Short guide to Markdown slides
### This has much potential

{{% pdf %}} <small> — <strong>Author</strong>: Paperon De Paperoni</small>

---
{{% section %}}

# Typography

{{% accentify %}}
Slide down!
{{% /accentify %}}

$\downarrow$

---

{{% multicol %}}
{{% col%}}
# Headers
{{% /col%}}
{{% col%}}

# H1
## H2
### H3
#### H4
##### H5
###### H6

{{% /col%}}
{{% /multicol %}}

---

{{% multicol %}}
{{% col %}}
# Text
{{% /col %}}

{{% col %}}
normal text

`inline code`

*italic*

**bold**

**_emphasized_**

*__emphasized alternative__*

~~strikethrough~~

[link to google](http://www.google.com)
{{% /col %}}

{{% /multicol %}}

---

{{% multicol %}}
{{% col %}}
# Lists
{{% /col %}}
{{% col %}}

1. First ordered list item
1. Another item
    * Unordered sub-list.
    * with two items
        * another sublist
            1. With a sub-enum
            1. yay!
1. Actual numbers don't matter, just that it's a number
  1. Ordered sub-list
1. And another item.

{{% /col %}}
{{% /multicol %}}

{{% /section %}}

---

{{% section %}}

{{% accentify "top-right" %}}
# UI Blocks
{{% /accentify %}}

Slide down!

$\downarrow$

---

{{% multicol %}}
{{% col %}}
# Callouts

{{% callout title="A wise man once said" type="cite" 
src="Confucio, ''lettere d'amore''" %}}
skrr skrr blea blea
{{% /callout %}}

{{% callout title="A wise man once said" type="cite" 
src="Confucio, ''lettere d'amore'' (con link)" srcLink="https://www.google.com" %}}
skrr skrr blea blea
{{% /callout %}}

{{% /col %}}

{{% col%}}
{{% callout title="Tip" type="tip" %}}
this must be a great tip
{{% /callout %}}

{{% callout title="Note" type="note" %}}
this is an information, or a note
{{% /callout %}}

{{% callout title="Success" type="success" %}}
Yay!
{{% /callout %}}

{{% callout title="Danger!" type="danger" %}}
something went possibly wrong :/
{{% /callout %}}

{{% callout title="Warning!" type="warning" %}}
just a warning
{{% /callout %}}

{{% /col %}}
{{% /multicol %}}

---

# Code Blocks
pt#01

## inline

You can play around with this `code` or `pwd`

---

{{% multicol %}}

# Code Blocks
pt#02

## inside code blocks
{{% col %}}

```java { linenos=inline hl_lines=["4-6"] }
import System;

class Program {
  public static void main(string[] args) {
    System.out.println("Hello, World!");
  }
}
```
{{% /col %}}

{{% col %}}
{{% callout type="note" %}}
You can even highlight some lines of code!
{{% /callout %}}
{{% /col %}}

{{% /multicol %}}


---

{{% code path="static/files/code.cpp"  %}}
## from file

{{% /section %}}

---


![Alternative text](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcdn.mos.cms.futurecdn.net%2FCcD2hbxVtfyvg5Q923eebM.jpg&f=1&nofb=1&ipt=8478f0cb985c8f3a744229931c01e03eca07c37df471f14807cfd2f817c67faa)

#### Inline images

---

## Fallback to shortcodes for resizing

Autoresize specifying

* `max-w` (percent of parent element width) and/or `max-h` (percent of viewport height) as max sizes , and
* `width` and/or `height` as *exact* sizes (as percent of viewport size)

---

{{% section %}}
{{< slide background-iframe="animations/8bitmoon.html" background-interactive=false >}}

## **With background!**

Explore the `static/animations` folder to find out more!

---

{{< slide background-iframe="animations/hexagons.html" background-interactive=false >}}

## **Hexagons everywhere**

---

{{< slide background-iframe="animations/melting-lines.html" background-interactive=false >}}

## **Melting lines**

---

{{< slide background-iframe="animations/ribbons.html" background-interactive=false >}}

## **Ribbons**

---

{{< slide background-iframe="animations/particles.html" background-interactive=false >}}

## **Particles**

---

{{< slide background-iframe="animations/grainient.html" background-interactive=false >}}

## Grainient

{{% /section %}}

---

## Tick and Cross

* {{% tick %}} This is something good
* {{% cross %}} This is something bad

---

## Chart.js

{{< chart >}}
{
    type: 'bar',
    data: {
        labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
        datasets: [{
            label: 'Bar Chart',
            data: [12, 19, 18, 16, 13, 14],
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)',
                'rgba(54, 162, 235, 0.2)',
                'rgba(255, 206, 86, 0.2)',
                'rgba(75, 192, 192, 0.2)',
                'rgba(153, 102, 255, 0.2)',
                'rgba(255, 159, 64, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)',
                'rgba(54, 162, 235, 1)',
                'rgba(255, 206, 86, 1)',
                'rgba(75, 192, 192, 1)',
                'rgba(153, 102, 255, 1)',
                'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1
        }]
    },
    options: {
        maintainAspectRatio: false,
        scales: {
            yAxes: [{
                ticks: {
                    beginAtZero: true
                }
            }]
        }
    }
}
{{< /chart >}}

---

## FontAwesome

<i class="fa-solid fa-mug-hot"></i>
<i class="fa-solid fa-lemon"></i>
<i class="fa-solid fa-flask"></i>
<i class="fa-solid fa-apple-whole"></i>
<i class="fa-solid fa-bacon"></i>
<i class="fa-solid fa-beer-mug-empty"></i>
<i class="fa-solid fa-pepper-hot"></i>

---

## Bootstrap 1

<div class="card w-100" >
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e9/View_of_Cesena_from_the_Abbey.jpg/1920px-View_of_Cesena_from_the_Abbey.jpg" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>

---

## Bootstrap 2

<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-secondary">Secondary</button>
<button type="button" class="btn btn-success">Success</button>
<button type="button" class="btn btn-danger">Danger</button>
<button type="button" class="btn btn-warning">Warning</button>
<button type="button" class="btn btn-info">Info</button>
<button type="button" class="btn btn-light">Light</button>
<button type="button" class="btn btn-dark">Dark</button>

<button type="button" class="btn btn-link">Link</button>

---

## Low res, plain markdown

![](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6c/Scavolino_innevata.jpg/260px-Scavolino_innevata.jpg)

---

## Hi res, plain markdown

![](https://upload.wikimedia.org/wikipedia/commons/6/6c/Scavolino_innevata.jpg)

---

{{< slide background-image="https://upload.wikimedia.org/wikipedia/commons/6/6c/Scavolino_innevata.jpg" >}}

# Large images as background
## (May affect printing)

---


{{< slide background-video="https://github.com/DanySK/slides-2024-acsos-imageonomics/raw/master/content/nonnadir.mkv" background-video-loop="true" background-video-muted="true" background-opacity="0.95">}}

# Video background

---

{{% multicol %}}
{{% col %}}
{{% accentify "top-right" %}}
# $$\LaTeX{}$$
{{% /accentify %}}
{{% /col %}}

{{% col %}}

$\textbf{Exercise}$ 

Prove that $a_n = \frac{2n + 1}{n + 2} \xrightarrow[n \to +\infty]{} 2$.

$\textbf{Proof}$ 

Given $\varepsilon > 0,\ \exists m_\varepsilon \in \mathbb{N}:$
<div>
\begin{equation}
    \begin{split}
        \left\lvert a_n - l \right\rvert &= \left\lvert \frac{2n + 1}{n + 2} - 2 \right\rvert \leq \varepsilon, \qquad \forall n \in \mathbb{N} \\
        &= \left\lvert \frac{2n + 1 -2n - 4}{n + 2} \right\rvert \leq \varepsilon \\ 
        &\Longleftrightarrow \frac{3}{n + 2} \leq \varepsilon \\
        &\Longleftrightarrow n + 2 \geq \frac{3}{\varepsilon} \\
        &\Longleftrightarrow n \geq \frac{3}{\varepsilon} - 2
    \end{split}
\end{equation}
</div>

I can choose $m_\varepsilon = \left[\frac{3}{\varepsilon} - 2\right] + 1$ in order to satisfy the limit. $\\#$
{{% /col %}}
{{% /multicol %}}


---

# Code snippets

```kotlin { linenos=inline }
val x = pippo
```

```go { linenos=inline, hl_lines=["5-7"]  }
package main

import "fmt"

func main() {
    fmt.Println("Hello world!")
}
```

You can highlight some lines of code!

---

# Tables

Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the
raw Markdown line up prettily. You can also use inline Markdown.

---

# Quotes

> Multiple
> lines
> of
> a
> single
> quote
> get
> joined

> Very long one liners of Markdown text automatically get broken into a multiline quotation, which is then rendered in the slides.

---

# Fragments

* {{< frag c="pluto" >}}
* {{< frag c="pluto" >}}
* {{< frag c="pluto" >}}

---

# Stacking images with Fragments
{{% multicol %}}
{{% col %}}
<p class="fragment" data-fragment-index="0">Pippo</p>
<p class="fragment" data-fragment-index="1">Pluto</p>
<p class="fragment" data-fragment-index="2">Paperino</p>
{{%/ col %}}

{{% col %}}
<div class="r-stack">
  <img
    class="fragment current-visible"
    data-fragment-index="0"
    src="https://www.topolino.it/wp-content/uploads/2019/12/pippointera.png"
    width="450"
    height="300"
  />
  <img
    class="fragment current-visible"
    data-fragment-index="1"
    src="https://www.topolino.it/wp-content/uploads/2019/12/plutointera.png"
    width="300"
    height="450"
  />
  <img
    class="fragment current-visible"
    data-fragment-index="2"
    src="https://it.wikifur.com/w/images/thumb/6/6f/Donald_Duck.png/362px-Donald_Duck.png"
    width="400"
    height="400"
  />
</div>
{{%/ col %}}

{{%/ multicol %}}


---

# Graphs via Gravizo

{{< gravizo "Example Gravizo graph" >}}
  digraph G {
    aize ="4,4";
    main [shape=box];
    main -> parse [weight=8];
    parse -> execute;
    main -> init [style=dotted];
    main -> cleanup;
    execute -> { make_string; printf}
    init -> make_string;
    edge [color=red];
    main -> printf [style=bold,label="100 times"];
    make_string [label="make a string"];
    node [shape=box,style=filled,color=".7 .3 1.0"];
    execute -> compare;
  }
{{< /gravizo >}}

---

# Graphs via mermaid.js

```mermaid
classDiagram
  Class01 <|-- AveryLongClass : Coosssl
  Class03 *-- Class04
  Class05 o-- Class06
  Class07 .. Class08
  Class09 --> C2 : Where am i?
  Class09 --* C3
  Class09 --|> Class07
  Class07 : equals()
  Class07 : Object[] elementData
  Class01 : size()
  Class01 : int chimp
  Class01 : int gorillasaaaaaaaaaaaaaaaaaaaaaa
  Class08 <--> C2: Cool label
```

---


# Graphs via mermaid.js with options

```mermaid
%%{init: {'theme':'default', 'themeVariables': { 'fontSize': '.34em', 'fontFamily': 'verdana' }}}%%
classDiagram
  Class01 <|-- AveryLongClass : Coosssl
  Class03 *-- Class04
  Class05 o-- Class06
  Class07 .. Class08
  Class09 --> C2 : Where am i?
  Class09 --* C3
  Class09 --|> Class07
  Class07 : equals()
  Class07 : Object[] elementData
  Class01 : size()
  Class01 : int chimp
  Class01 : int gorillasaaaaaaaaaaaaaaaaaaaaaa
  Class08 <--> C2: Cool label
```


---
# Graphs via mermaid.js 2

```mermaid
graph TD
  SL([fa:fa-user second level]) --> L[solution]
  L -- solution email --> db[(mysql)]
  db --> X[automatic]
  X --> CM([fa:fa-users first level])
  db -- Email --> c([customer support]);
```

---

# Graphs via mermaid.js 3

```mermaid
gitGraph
  commit id: "Initialize project"
  commit id: "Make some changes"
  branch develop
  checkout develop
  commit
  commit
  checkout main
  merge develop
  commit
  commit
```

---

# Keystrokes

<kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Del</kbd>

---

# QR code

{{% qrcode data="https://www.google.com" %}}

---

# Import shared slides

<!-- write-here "shared-slides/devops/devops-intro.md" -->
<!-- end-write -->
