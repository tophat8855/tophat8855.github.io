---
title: Reverse Job Interview Problem
date: 2021-02-05
tags: ['post', 'coding', 'clojure']
---
Yesterday on twitter, [this tweet](https://twitter.com/Al_Grigor/status/1357028887209902088) got a lot of attention in the developer world.

It states:

>Most candidates cannot solve this interview problem:
>
>Small orange diamond
> Input: "aaaabbbcca"
>Small orange diamond
> Output: [("a", 4), ("b", 3), ("c", 2), ("a", 1)]
>
>Write a function that converts the input to the output
>
>I ask it in the screening interview and give it 25 minutes
>
>How would you solve it?

I noticed that Clojurian Gene Kim gave [this response](https://twitter.com/RealGeneKim/status/1357460688881389574). 

```
(->> (partition-by identity "aaaabbbcca")
     (map (fn [x]
            [(->> x first str) 
             (count x)])))
```

I'm a huge fan of finding a use for `partition-by`. 

On Clojurians, Savo Djuric shared his solution, which he blogged [here](https://savo.rocks/posts/a-random-job-interview-challenge-in-clojure/).
```
defn chop-chop [coll]
  (let [x (partition-by identity coll)]
    (map list (map (comp str first) x)
                (map count x))))
=> (chop-chop "aaaabbbcca")
=> (("a" 4) ("b" 3) ("c" 2) ("a" 1))
```

All of this conversation made me wonder, what if I did it backwards? I'd like to create a function with the input of 

`[("a", 4), ("b", 3), ("c", 2), ("a", 1)]`

and output of the string 

`"aaaabbbcca"`. 

So I started playing around with it. I gave myself the restriction that the input 

```
[("a", 4), ("b", 3), ("c", 2), ("a", 1)]
```

is
a vector of lists. Not a list of vecs like Kim's solution and and not list of lists, like Djuric's.

This is what I've come up with.
```
(def alpha-num-tuples ['("a" 4) '("b" 3) '("c" 2) '("a" 1)])

(defn tuple-to-chars [tuple] (repeat (last tuple) (first tuple)))

(clojure.string/join (mapcat tuple-to-chars alpha-num-tuples))
;; "aaaabbbcca"
```

The function `tuple-to-chars` takes ones of the tuples such as `("a" 4)`

and returns `("a" "a" "a" "a")`. 

The result of `mapcat`-ing all of 
the tuples-turned-chars is `("a" "a" "a" "a" "b" "b" "b" "c" "c" "a")`. 

And then simply join the chars to a string!

`"aaaabbbcca"`


There is probably a more beautiful or idiomatic way. Let me keep playing with it.
