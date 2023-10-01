# Learning CUE Part 2: the Value, the List and the Lookup

ok, so i had this story worked out and wanted to capture it before forgot or lost motivation to capture it, so here goes ...

also, please bear in mind that this is for newcomers and has some intentional oversimplifications, but the goal is to start simple with something relatable and gradually build up in complexity as we go along, assuming really almost no foreknowledge of computer science ... that said, this is also a first cut (in writing) and so it can improve over time and with feedback

because i'm too lazy or tired to come up with a better name right now, I'm going to imagine Blake who is making a cake

... this story is going to have to be revisited because it's before work, so i perhaps like Tenacious D's: Greatest Song in the World .... *Tribute,* so too will this ramble be ... a tribute to some of the general build up and points

a a quick shout-out to another awesome influentional book for me: [The Little Schemer](https://www.goodreads.com/book/show/548914.The_Little_Schemer) (or LISPer) ... which was designed to do on paper and which i went through and read with both my kids (using a small piece of cardstock to hide & reveal the right side of the page), but i digress ...

i'm going to be going with some Lispy terminology to draw some comparisons, but of course those can be worked out later.

so blakey learns about atoms, which are single values, like a string in quotes or a number, but it's essentially a standalone group of one isolated thing (remember the story part will be worked out later, not feeling it this morning, just capturing some points for later)

"flour" and "baking soda"

also quantities like 2

obviously these are just types of values, but to make them more useful we need to put them together

so we start by making a list ... like a list on paper, initially we're going to group the numbers and text into a single string (don't worry, they'll be split out later)

so to make a list we use the square brackets: ["1 lb flour", "2 eggs", "1 teaspoon baking soda"] and so on just like you'd write them down in a little notepad

blakey ends up with a list like ["1 lb flour", "2 eggs", "1 cup cream", "2 cups sugar", "1 tsp baking soda", "1 cup creme (for frosting)", "1 cup sugar for frosting"] ... so, now we have duplicated items on the list ... later we can separate these into 2 lists and join them, but not yet

so, obviously blakey wants a shopping list to take to the store and just buy the right amount of stuff ...

so we need to separate the number and text parts, we're not going to deal with units of measure yet (but later), so we'll just stick that part in the text, but we're going to introduce a *lookup* - i.e. a way to look up how many eggs need

for that we're going to use a little alphabetical paper notebook (no cringing yet, the complexity will build) ... but for now...

flour goes to the first line of the 'f' page, and eggs goes to the first line of the 'e' page and so on, with the number of how many, we're not going to add or tally them them yet, we're just going to have "flour, lbs": 1, "eggs": 2, "sugar, cups": 2 with another row for "sugar, cups": 1 - with a comment in the margin to say what for ...

also, don't worry, blakey will have to convert to metric because it adds better, so we can do the imperial to metric later on

so the list is really fast to write down, and it's easy to have duplicates, and it's all in the same order you wrote it down in

our lookup notebook is alphabetised, but that takes longer to write down, and there can only be one entry group (page?) for eggs

of course realising that this could still be a little tricky with cue, but ... we'll get there ... i was actually originally thinking like a rolodex style with one 'card' ... so perhaps that is actually better ... but there's another bit of important information here

continuing with the rolodex, we have an 'E' category (flipper), and an 'eggs' card whose title has to be unique ...

but blakey has a unique system ... rather than filing every card alphabetically throughout the whole category, they're instead grouped by E, but within E, just stick any card you edit back at the front (again, not strictly true but it's a functional metaphor)

by filing the cards this way, blakey can get to the 'E's really fast and it only takes a second or two to find the right card there, but would take way longer to sort them every time you put them in ... also, you could pull 5 cards out from different categories and work on them, then just stick them back at the front of the category section versus having a *secondary* scan through every card to put them back in the right spot

so this card system makes it really easy to look things up and put them back, but you only get one card per topic and you don't necessarily know what order things will come back in, "sugar" and "syrup, maple", because those are both "S" cards, may get retrieved in any order, so ... if you do want them in a particular order, either alphabetical or by aisle in the supermarket, blakey's just going to need one extra step after retrieving them, and that's just to sort them

so: by first writing out the list of ingredients, blakey can convert that list to a lookup (map)

key takeways: lists are ordered, fast to write to, but slow to search, allow duplicates

lookups are unordered (effectively), and a little slower to write to but much faster to search, but no dupes

also with the list being a page, you can't go back and erase the whole page to insert something into the middle, to make the final shopping list, blakey's going to have to go from list to lookup, then *back to list,* it's just a *new,* i.e. second list

whereas with the cards, you can have any number of things that start with 'S' or 'E' and can just grab a new card and just insert it at the front of the 'E' section ... i.e. it's easily appendable

both have pros and cons and depend on the context of what they're trying to do

quick sidenote re: blakey putting the card at the front vs anywhere in the section, i know about hash-maps and hash algorithms and rotational strategies and bucketing (i forget all the very specific terms i'm out of practice), and they'll typically run backwards to the next open 'slot', so it's not *literally* true, but blakey doesn't care about how computers store it ... blakey's system is *smart* for a rolodex (like our systems are *smart),* and also kinda leads alludes to caching and indexing strategies which *can* make fresher values faster to access ... so front of the list is like a redis cache or something it can check before going to disk ... just saying ...

this is a metaphor for blakey to understand when/why to use a list, and when/why to use a lookup in very real-world terms

for the experts, a list ... sheesh, is that a singly-linked list data structure or doubly-linked? is it uniformly typed? are there pointers? ... or if they're uniform, might as well be an array but is it fixed sized? what are the data types, maybe instead is a resizable array like a slice, but then what's the growth strategy, does it fit in memory ... blakey doesn't need to know or care about this .... ever (edited)

what about those lookups: well, in cue from blakey's perspective there isn't really much perceivable difference between a struct and a map, save for perhaps some curly braces, but even then it's subtle and are the curly braces (suspenders) that different from the square ones?

there's a lot going on under the hood for structs and maps, but blakey shouldn't care about these either

what human would use the term 'array' to describe a series of words in rows on paper who hasn't studied comp sci data structures?

in human, it might be that's quite an array of collectible spoons you have, so it's not unheard of, but it's not the obvious term

for structs and maps well ... there isn't a great non-computer term for this besides a *dictionary* but that's not quite it either imho, nobody ever writes their *own* dictionary ... i think the box of index cards with the dividers is the best, but maybe alphabetical filing folders work too

but language seem to all have different names for these whether they're 'structs' or 'objects' or 'dictionaries' or 'maps' or 'hash-maps' or 'key-value pairs' or whatever, and i get there are subtleties in how these are stored in the computer: whether they're fixed or variable size or adjacent in memory as 'records'/'structs', or whatever, but blakey doesn't need to know this either

if blakey's cakes takes off and now has a huge catalog of products and orders then blakey can hire a specialist in these systems to design just the right thing that's provably correct and optimised ... but blakey just wants to focus on making better cakes

so, that's also the beauty of *declarative* programming like cue, in that it decouples the *what (*and *why)* from the *how -* which specifically allows the how to improve and evolve over time

anyway, more to say on all of this, but that seems to be the gist of it for now ... thanks for coming to my ted talk :-)
