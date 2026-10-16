---
layout: default
title: Research
permalink: /research/
---

<section class="band" markdown="1">

# Research

{% capture nonexperts %}
My research is motivated by a deep interest in the study of the relationship
between symmetry and singularities. At the most basic level, a symmetry is a
permutation of a mathematical object which preserves a desirable structure. For
example, in Newton's laws of motion one might notice that if one were to shift
the entire universe in one direction, any valid trajectory of an object would
be sent to a new valid trajectory. This is an example of *translational
symmetry*. Emmy Noether, in a monumental contribution to the study of physics,
noticed that there was a relationship between symmetries of physical systems
and conserved quantities. Going back to our example of Newtonian mechanics, it
turns out that the translational symmetry of Newtonian trajectories gives rise
to *conservation of momentum*.

In geometry, a singularity is a point in space where a mathematical model
ceases to function. The most famous example of this is perhaps the
singularities that appear in the study of Einstein's theory of gravitation. A
less mathematically intensive example of a singular geometric object might be
that of a 'teardrop': a single sharp point on an otherwise perfect sphere.
Suppose one was interested in understanding paths on such an object. Away from
the sharp point, differential geometers can easily make sense of the notion of
the 'direction' of a path on the teardrop. If one imagines that the teardrop is
sitting inside of a three dimensional space, one can define the direction of a
path at a given point by constructing the unique tangent plane which touches
the teardrop at exactly one point. However, at the 'sharp point' there are many
planes which touch the teardrop at only one point. It turns out that by
understanding the symmetries of the teardrop, one can 'unwind' the sharp point
after which geometry can proceed as usual. This process is sometimes called
*desingularization*.

In my research, I try to study singular objects not unlike the teardrop example
mentioned above. The main tool I use is the theory of Lie groupoids and Lie
algebroids which can be thought of as a very general kind of desingularization.
A common theme in my research is to try to understand how much of differential
geometry and algebraic topology can still be performed for spaces with
singularities. Other tools I occasionally make use of include sheaves,
diffeology and category theory depending on the needs of the problem. For
example, I frequently turn to Poisson and symplectic geometry and my work is
often motivated by trying to obtain a 'macro level' understanding of the
geometric constructions and objects that appear in these fields.
{% endcapture %}
{% assign nonexperts = nonexperts | markdownify %}
{% include collapsible.html title="For Non-Experts" tag="h2" class="section" body=nonexperts %}

## Papers and Preprints

<!-- The list comes from _data/papers.yml. -->
{% for p in site.data.papers %}
{% capture meta %}{% if p.coauthors %}With {{ p.coauthors }}. {% endif %}{{ p.venue | markdownify | remove: '<p>' | remove: '</p>' | strip }}{% endcapture %}
{% assign abstract = p.abstract | markdownify %}
{% include collapsible.html title=p.title url=p.url meta=meta body=abstract %}
{% endfor %}

## Expository Material

### [A geometric proof of the Fundamental Theorem of Algebra (with visualizations)](https://colab.research.google.com/drive/1A898TEOGSHCNcYKM0BWP8YmsE2PLFz9M?usp=sharing)

A brief iPython notebook hosted on Google's Colab service. It exposits a
geometric proof of the fundamental theorem of algebra. The proof is
supplemented with visualizations to illustrate the key concepts of the proof.

</section>

<section class="band dark" markdown="1">

## Recorded Talks

### On the algebraic geometry and homotopy theory of sheaves of Lie-Rinehart structures

Host: [Junior Global Poisson Workshop 2020](http://www.unige.ch/math/folks/nikolaev/JGPW2020.html)

<div class="video"><iframe src="https://www.youtube-nocookie.com/embed/VFVr4xPkDRw" title="Talk video" allowfullscreen loading="lazy"></iframe></div>

Lie-Rinehart algebras are an algebraic generalization of the notion of a Lie
algebroid. In this talk we will first survey the basics of Lie-Rinehart
algebras and the natural notions of morphisms between them. A natural spectrum
functor which sends Lie-Rinehart algebras to sheaves of Lie-Rinehart algebras
over locally ringed spaces will then be defined. In the manifold setting, we
will see that examples of non-algebroid sheaves of Lie-Rinehart algebras arise
quite naturally. In conclusion, there will be an explanation of how several
classical invariants of Lie algebroids such as characteristic foliations,
homotopy groups, and Crainic-Fernandes style integration theory might be
generalized to this setting.

### Poisson manifolds and their associated stacks

Host: [BIRS Workshop 17w5023 "Geometric structures on Lie groupoids"](https://www.birs.ca/events/2017/5-day-workshops/17w5023)

<div class="video"><iframe src="https://www.youtube-nocookie.com/embed/rEzlq8118CQ" title="Talk video" allowfullscreen loading="lazy"></iframe></div>

Lie groupoids with Morita equivalence are a convenient model for the study of
singular manifolds. This talk will explain how one can interpret a symplectic
groupoid and symplectic Morita equivalence as a model for a singular Dirac
manifold. To that end, we will define a site (a category with a topology) whose
objects are Dirac manifolds, $$\mathrm{DMan}$$, and explain how to associate a
stack over $$\mathrm{DMan}$$ to any symplectic groupoid. Furthermore, we will
relate isomorphisms of such stacks with symplectic Morita equivalences.

</section>
