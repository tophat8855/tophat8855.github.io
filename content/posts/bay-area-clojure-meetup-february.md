---
title: Virtual Bay Area Clojure Meetup February 2021
date: 2021-02-09
tags: ['post', 'coding', 'clojure']
---

Here are my notes from today's Bay Area Clojure Meetup. They are in note form and perhaps a bit sporadic.

Zach Oakes - [O'Doyle Rules](https://github.com/oakes/odoyle-rules): a Clojure(Script) rules engine for the best of us.

Rules Engines are used for reactive programming. "Observables" "Spreadsheet-style programming"
Making values affect by changes automatically.

"Map fatigue" is related to how much in Clojure we deal with deeply nested maps.

Rules: functions that run automatically when their inputs update. Don't need to call them. The rules engine calls it.

in O'Doyle, you split your data up in tuples. Can represent almost any nested/heirarchal data as tuples to simplify it.

what/then blocks

```
[:what
  [thing :location/var binding
  [thing :other/var2 other-binding]
  [thing :other/var3 another-bnding]
  [binding :location/var4 extra-binding]
  :then
  (function-that-uses-those-bindings thing :something (-> binding other-binding another binding extra-binding))]
```

"pure functions can be reasoned about in isolation." - maybe true on small scale, but hard in the big scale of the whole system

A slide by Oakes:
```
(-> state fn-a fn-b fn-c)

;; does order matter, who knows...
;; dependencies between functions
;; are implicit
```

The `what` block makes dependencies clear and explicit. Easier to understand in isolation.

Oakes demonstrated the use of his rules engine with a dungeon crawler game he made.

Examples of reactive programming on the web: reframe, redux, airstream.

A rules engine is a more general form of those.

"O'Doyle's 10th rule: Any sufficiently complicated reactive programming library contains an ad hoc, informally-specified, bug-ridden,
slo implementation of half of a rules engine."

Example of a library using his O'Doyle rules engine: [O'Doyle Rum](https://github.com/oakes/odoyle-rum).
Also he's maintaining a rules engine for games, [Pararules](https://github.com/paranim/pararules).

Going to have to think about what I could try a rules engine on. An app or idea?

In the discussion, someone mentioned [Toon Talk](http://toontalk.com/), a gaming engine for kids.
Also Zach's [play-cljc](https://github.com/oakes/play-cljc).

Also Paul Lam talked about [clj-sqs-extended](https://github.com/Motiva-AI/clj-sqs-extended) he wanted to share.
