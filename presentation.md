Explore Reddit comments with <span class="sigma">sigma.js</span>
================================================================

---

Who I am...
===========

<div style="padding-top: 50px; padding-left: 150px;">

**Alexis Jacomy**
-----------------

JavaScript developer @ [Linkfluence](http://linkfluence.net)

 - [jacomyal](http://github.com/jacomyal) on **github**
 - [jacomyal](http://twitter.com/jacomyal) on **twitter**

**Linkfluence**
---------------

 - [linkfluence](http://github.com/linkfluence) on **github**
 - [linklabs](http://twitter.com/linklabs) on **twitter**

</div>

---

What is <span class="sigma">sigma.js</span> ?
=============================================

---

<span class="sigma">sigma.js</span> is a <br> JavaScript **graph drawing library**
==================================================================================

---

A *very* brief historic of <br> **graph drawing tools**
=======================================================

---

**Pajek** (1996):
-----------------

<br>

![Pajek screenshot](img/pajek.gif)

<span class="right">*[website](http://vlado.fmf.uni-lj.si/pub/networks/pajek/)*</span>

---

**Gephi** (2008):
-----------------

The "Photoshop" for graphs
--------------------------

![Gephi screenshot](img/gephi.png)

<span class="right">*[website](http://gephi.org)*</span>

---

**But what about online tools?**
================================

---

Linkfluence Maps
----------------

<br>

![Linkfluence map screenshot](img/linkfluence-maps.png)

<span class="right">*from the awesome [Linkfluence Atlas](http://us.linkfluence.net/insights-2-0/atlas/)!*</span>

---

<span class="thirty">*definitely great, but not open, not generic and in Flash*</span>
======================================================================================

---

**SeaDragon** export from **Gephi**
-----------------------------------

<br>

![Seadragon screenshot](img/seadragon.png)

<span class="right">*[CPAN explorer, by Linkfluence](http://cpan-explorer.org/)*</span>

---

<span class="thirty">*but it's not that much interactive*</span>
=================================================================

---

**Protovis.js** and **d3.js**
-----------------------------

<br>

![d3.js force-directed graph screenshot](img/d3.png)

<span class="right">*[example with d3.js](http://mbostock.github.com/d3/ex/force.html)*</span>

---

<span class="thirty">*but it's in SVG - not so scalable*</span>
================================================================

---

And here comes <span class="sigma">sigma.js</span>
--------------------------------------------------

<div class="twentyfour" style="padding-top: 100px; padding-left: 120px;">

 - written in JavaScript
 - dedicated to **graph drawing** - and nothing else
 - scalable (*until ~2000 nodes ~30000 edges*)
 - fluid (frames are injected during the drawing process)
 - open-source
 - interactivity / user oriented

</div>

---

Quickly, some use cases:
========================

---

<span class="thirty">**Facenuke** (by Greenpeace):</span>
---------------------------------------------------------

![Facenuke screenshot](img/facenuke.png)

<span class="right">a network of people - *[link](http://greenpeace.fr/facenuke/)*</span>

---

<span class="thirty">**French OpenData Viz** (by Data-Publica):</span>
----------------------------------------------------------------------

![French OpenData Viz screenshot](img/datapublica.png)

<span class="right">a network of websites - *[link](http://french-opendata.data-publica.com/)*</span>

---

<span class="thirty">**NameGenDev** (by Bernie Hogan/Oxford):</span>
--------------------------------------------------------------------

![NameGenDev screenshot](img/namegendev.png)

<span class="right">displays your ego-centered Facebook network - *[link](https://apps.facebook.com/namegendev/)*</span>

---

<span class="thirty">**Movie Galaxies**:</span>
--------------------------------------------------------------------

![Movie Galaxies screenshot](img/moviegalaxies.png)

<span class="right">"the social interaction graph in movies" - *[link](http://moviegalaxies.com/)*</span>

---

Now, let's explore some data!
=============================

---

**Reddit API:**
===============

---



---

**Play with <span class="sigma">sigma.js</span>:**
======================================================

---

**Fill the graph (1):**
-----------------------

Assume we have an object `graph` describing our graph:

    var graph = {
      nodes: [
        {
          id: 'node1',
          label: 'Node 1'
        //  [...]
        },
        {
          id: 'node2',
          label: 'Node 2'
        //  [...]
        }
        //[...]
      ],
      edges: [
        {
          source: 'node1',
          target: 'node2',
          id: 'edge1'
        //  [...]
        }
        //[...]
      ]
    };

---

**Fill the graph (2):**
-----------------------

Then, here is the code to show our graph in a <span class="sigma">sigma.js</span> instance (named `sigInst`):

    var i, n, e,
        N = graph.nodes.length,
        E = graph.edges.length;

    // Add nodes:
    for (i=0; i<N; n = graph.nodes[i++])
      sigInst.addNode(n.id, n);

    // Add edges:
    for (i=0; i<E; e = graph.edges[i++])
      sigInst.addEdge(e.id, e.source, e.target, e);

---

**Navigate in the graph:**
--------------------------

    var p = sigInst.position();
    // Returns an Object:
    // {
    //   stageX: The X position of the stage,
    //   stageY: The Y position of the stage,
    //   ratio:  The zoom ratio of the graph
    // }
    

    sigInst.goTo(
      p.stageX + 10,
      p.stageY + 10
    );
    // Moves the graph by 10 pixels left and
    // 10 pixels top.

---

**Modify the nodes:**
---------------------

    sigInst.iterNodes(function(node) {
      node.color = '#fc0';
    });

---

**Modify specified nodes:**
---------------------------

    // Here is an array containing ids of nodes if the graph:
    var ids = ['node1', 'node2'];

    sigInst.iterNodes(function(node) {
      node.color = '#fc0';
    }, ids);

---

**Catching mouse hover/down nodes:**
------------------------------------

<span class="sigma">sigma.js</span> has its own `EventDispatcher` class, with the methods `bind` and `unbind`:

    sigInst.bind('overnodes', function(event) {
      console.log('Over nodes:', event.content.join(', '));
    }).bind('downnodes', function(event) {
      console.log('Down nodes:', event.content.join(', '));
    });

Available events:

 - `downgraph`
 - `upgraph`
 - `downnodes`
 - `upnodes`
 - `graphscaled`
 - `draw`

---

**Catching mouse hover nodes:**
-------------------------------
