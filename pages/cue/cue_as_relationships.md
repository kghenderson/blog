# Cue as relationships, declarative vs imperative

cue requires a new way of thinking: i.e. declaratively and with composition vs imperatively and/or with inheritance

programmers know a bit about this, but it's a very foreign topic for many

but my own take on it is that: you first say all the things that you want, and how all of those things: relate to each other, and which things have commonalities

there are many, many directions to take this, but in regards to things like bret victors work, there's math in terms of 2*3 =6, but there's also a relationship between the thing that 2 represents and the thing that 3 represents, and that 6 is the outcome, you're defining 3 thing-values and 3 relationships in the example

i remember my mind being blown seeing a Prolog (lang) demo, which could do math "backwards", just by making statements

i.e. (paraphrasing) that that x*y=z, then x=2 & z=8, then it can give you 4 as being x even though you didn't express it that way

prolog is still cool but performance is a problem, and more importantly, it has a very steep learning curve and strange syntax & syntax holes that make it too unweildy to get others on board using it - same goes for haskell and idris and many other very cool languages as well

for those who might not know: datalog is prolog's data-oriented cousin and is used by several tools such as datomic for doing this kind of thing, also terminus db's WOQL and other semantic web tools and graph query languages

far and away, by accepting some chosen constraints, cue is the easiest to use and understand and read/write/interchange between multiple formats

using *Cue* is squarely in the range of mere mortals and using the most basic and universally accepted building blocks: the type, the value, the list, the struct, and the map (maybe missing some, lol, don't forget that other primitive - the regular expression! /s ), but these are just so easy to explain

i want to make a shopping list: so ... i'm going to make a list of items to buy at the store ... what kind of store? the grocery store ... so each is a grocery item, and if i try to put plywood on the list, it should fail and tell me it's not a grocery item ... we can build up from these blocks

there's a much lower barrier to entry and in a practical and pragmatic way

wouldn't it be great if you could check your list against the store's list (which you don't need to maintain, you can just reference), and know if it's in stock and/or if it's going to continue to be), etc.

back to the number formulas above, cue can help easily define both the things and the relationships, and permit values to change and know (generally) if the new values have the same meanings, since change over time and alternate/what-if scenarios are ultimately the real challenge)

>  I've been in conversations about logic-oriented programming languages and how this paradigm is being used for the problem space. Rego (the policy language for OPA) is Datalog inspired.
>  Also: the imperative vs declarative, this feels well-worn in the "Infrastructure as Code" space, sometimes, but not mentioned at all in others. So if CUE is to be as universally useful for everyone, we need to be mindful of knowledge "pockets" and "gaps" in the ecosystem

> Also: math backwards?!?!

haha, re: math backwards: i don't have a goto talk: but like this: **"Production Prolog" by Michael Hendricks** https://www.youtube.com/watch?v=G_eYTctGZw8  (even just the first few minutes)

in most programming: you say func z(x, y), then myZ = z(2,3), and myZ=6 ... it performs exactly the function you *tell* it

with prolog, once you've established that z=x*y ... you can give it any 2 values and it will know and tell you the 3rd

the *math* isn't backwards, it's more like a reversable function, by describing the relationship
