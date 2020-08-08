---
title: Category Theory in Clojure, Clojure-Provo Meetup Notes
date: 2020-07-31
tags: ['post', 'coding', 'clojure']
---

This evening I attended a virtual meetup for the Clojure-Provo titled,
"Category Theory in Clojure- installment 1" given by Brian Abbott. 

A few of my coworkers had been following along with 
[MIT's Programming with Categories](https://www.youtube.com/playlist?list=PLhgq-BqyZ7i7MTGhUROZy3BOICnVixETS)
course earlier this year during our open source time. Because of that, I wanted to attended
this meetup and report back any interesting links or thoughts. Here are some of my notes
from attending the meetup for future reference:

Category theory is an abstractions of abstractions. Abbott referred to it multiple times as
"an assembly language of mathematics." A category is a labelled, directed graph with nodes and
morphisms (seen often as arrows in an operation).

He shared a "History of Category Theory" timeline ("history is a morphism with from and to")
starting with David Hilbert in 1890 and continuing to the mid-20th century. He highlighted 
Saunders MacLane and Samuel Eilenberg's work in 1942 as the birth of category theory as we know it.
When I skimmed the list, I noticed at least one woman's name: Emmy Noether. I'll have to look her up 
later.

Abbott listed a few synonyms for category theory that may make it easier to search for papers: topos
theory, topoid theoyr, sheaf theory, algebraic topology. 

As a resource for papers, presentations, libraries, etc., about category theory and functional discipline,
Abbott recommended Clojure-Provo's repo, 
[functional-discipline-content-cats](https://github.com/clojure-provo/functional-discipline-content-cats)

Dragon Djuric's work was highlighted as examples of category theory in clojure. Fluo Kitten is a category 
implmentation on clojure.
[Fluo Kitten on Github](https://github.com/uncomplicate/fluokitten)
[Fluo Kitten's documentation](https://fluokitten.uncomplicate.org/codox/)

Neanderthal is a Clojure library that uses Fluo Kitten to do linear algebra and matrix computations.
[Neanderthal on Github](https://github.com/uncomplicate/neanderthal)
[Neanderthal's documentation](https://neanderthal.uncomplicate.org/)

"Category thoery ends up being a set of adjunct functor operations"

There was also a mention of [funcool's cats](https://github.com/funcool/cats) which is also a library for 
using category theory in Clojure.

Fluo Kitten's implementation of category theory uses Haskell-style left assocation binding.

Also mentioned was [Stephen Wolfram's Physics Project](https://www.wolframphysics.org/) which describes physics using hypergraphs.

At the end of the meeting, there was some discussion of what people would like in the future from these meetups.
It seems many people are interested in intermediate examples of category theory in the practice of Clojure.
There are many "simple" examples and many more complicated examples, but where would you reach for 
category theory when you are doing your every day programming?

"What category theory allows you to do is what higher level functions allow you to do, but on steroids"

Abbott also voiced the concern that category theory is too bound to Haskell and that the community needs to
get away from equating category theory in programming with Haskell and perhaps these meetups can 
bring Clojure into category theory more.

Personal thoughts: every time I venture into category theory I think about how I missed this in my BS degree. 
I understood mathematics was growing, but I didn't see where it was growing- topology and algebra were presented
in history and not as something growing. I ended up doing research in number theory. My roommmate Melissa did
reserach in topology and I wonder if I had chosen a different discipline, I would have run into category theory
sooner. Oh well, I can learn it now.
