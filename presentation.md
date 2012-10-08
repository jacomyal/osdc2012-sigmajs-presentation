Explore Reddit comments with <span class="sigma">sigma.js</span>
================================================================

---

Who I am
--------

Alexis Jacomy

Interface developer @ [Linkfluence](http://linkfluence.net)

 - on [github](http://github.com/jacomyal)
 - on [twitter](http://twitter.com/jacomyal)


---

What is <span class="sigma">sigma.js</span> ?
===========================================

---

<span class="sigma">sigma.js</span> is a JavaScript graph drawing library

---

A brief historic of **graph drawing tools**
===========================================

---

**Pajek** (1996):
-----------------

<br>

![Pajek screenshot](img/pajek.gif)

---

**Gephi** (2008):
-----------------

The "Photoshop" for graphs
--------------------------

![Gephi screenshot](img/gephi.png)

---

But no interactive tool <br> for the Web?
=========================================

---

Custom **Linkfluence** maps
---------------------------

<br>

![Linkfluence map screenshot](img/linkfluence-maps.png)

---

*but it's for the Flash player, and not open-sourced*
-----------------------------------------------------

---

**SeaDragon** export from **Gephi**
-----------------------------------

---

*but it's not that much interactive*
------------------------------------

---

**Protovis.js** and **d3.js**
-----------------------------

---

*but it's in SVG, and kind of overkill*

---

So...
=====

---

 - An Open-source Javascript Library
 - Interactivity oriented
 - Using the Canvas element
 - Dealing with graph drawing, and **only** graph drawing

---

<span class="sigma">sigma.js</span>




Explore Reddit comments with <span class="sigma">sigma.js</span>
---------

.notes: plop

Generates a slideshow using the slides that power
[the html5-slides presentation](http://apirocks.com/html5/html5.html).

A `python` with the `jinja2`, `markdown`, and `pygments` modules is required.

Markdown Formatting Instructions
--------------------------------

- Separate your slides with a horizontal rule (--- in markdown)
- Your first slide (title slide) should not have a heading, only `<p>`s
- Your other slides should have a heading that renders to an h1 element
- To highlight blocks of code, put !{{lang}} as the first indented line
- See the included slides.md for an example

Rendering Instructions
----------------------

- Put your markdown content in a file called `slides.md`
- Run `python render.py`
- Enjoy your newly generated `presentation.html`

---

Slide #2
========

.fx: foo bar

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean magna tellus,
fermentum nec venenatis nec, dapibus id metus. Phasellus nulla massa, consequat
nec tempor et, elementum viverra est. Duis sed nisl in eros adipiscing tempor.

Section #1
----------

Integer in dignissim ipsum. Integer pretium nulla at elit facilisis eu feugiat
velit consectetur.

Section #2
----------

Donec risus tortor, dictum sollicitudin ornare eu, egestas at purus. Cras
consequat lacus vitae lectus faucibus et molestie nisl gravida. Donec tempor,
tortor in varius vestibulum, mi odio laoreet magna, in hendrerit nibh neque eu
eros.

Unicode Characters Work
-----------------------

© é

---

Middle Title Slide
==================

---

Slide #3
========

**Hello Gentlemen**

- Mega Man 2
- Mega Man 3
- Spelunky
- Dungeon Crawl Stone Soup
- Etrian Odyssey

*Are you prepared to see beyond the veil of reason?* - DeceasedCrab

- Black Cascade
- Two Hunters
- Diadem of 12 Stars

---

Slide #4
========

First code block:

    !python
    while True:
        print "Everything's gonna be allright"

Second code block:

    !php
    <?php exec('python render.py --help'); ?>

Third code block:

    !xml
    <?xml version="1.0" encoding="UTF-8"?>
    <painting>
      <img src="madonna.jpg" alt='Foligno Madonna, by Raphael'/>
      <caption>This is Raphael's "Foligno" Madonna, painted in
        <date>1511</date>–<date>1512</date>.
      </caption>
    </painting>

---

Slide #5
========

Another code block:

    !java
    if (markdown && isEasy()) {
        return true; 
    }

---

Slide #6
========

An image:

---

Slide #7
========

Landslide can generate QR codes:

.qr: 450|http://github.com/adamzap/landslide

---

This is a slide with no heading. It works too.

---

Slide #9
========

This slide has presenter notes.

Press `p` to open a new window for the presenter with its notes.

# Presenter Notes

Hello from presenter notes