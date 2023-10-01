# Turtles all the way down, infinity train zoo, the ants on yggadrasil

there's a story/expression/quip which many who deal with recursion are familiar with, called '[turtles all the way down](https://en.wikipedia.org/wiki/Turtles_all_the_way_down)' whereupon all the world exists on the back of a great turtle, which stands on another turtle, and it's turtles all the way down

this is sometimes used, not just for infinite regression, and infinite loops, but also sometimes for the ladder of abstraction

by that i mean along the lines of an excel document where someone thinks & writes in excel formulas, but that's built in a language called C#/.NET, which rests on an operating System called Windows written in C++, which coordinates working with Device Drivers and BIOS written in C, which works with Hardware/Firmware written in Assembly, which emits electrical signals and voltages across a motherboard and various buses, which then gets down into the material sciences and transistors/capacitors/resistors/semiconductors, which then gets down to atoms and electrons, and down to the quantum sciences and so on ... turtles all the way down (also, this is just an analogy, probably missing some steps)

while the turtles phrase is still valuable as a way to indicate the base of a discussion, something that's always bothered me (and i'm sure others too), is that there being *turtles* all the way down seems to imply that the various levels of perspective are somehow homogeneous

i'm aware that this understanding of the phrase is not the original, and why put any thought to something so trivial, but what *does* bother me with it is that i've heard it used by non-technical people to just lump the 'nerd stuff' of 'how things work' into just a nerd stack

but regardless, even within the nerd-verse, each of these layers has drastically different thought patterns, idioms, priorities, software, and so on

in that regard, it could be thought of as a stack of different animals, who have different views and perspectives of their worlds: land animals, sea animals, flying animals, etc. ... all optimized for very different things

there was an interesting sci-fi cartoon called [infinity train](https://en.wikipedia.org/wiki/Infinity_Train), which followed characters who traversed the train where each car was a completely different and bizarre universe

alas the show itself would seem to be a victim of covid, but hopefully we'll get to see more someday

however, one last analogy that has somehow always stuck with me ... is that of ants on yggadrasil

as far as i know this is of my own devising, but i'm sure it's probably been said before but here goes

there exists (in this metaphor), a tree of knowledge (not exactly yggadrasil of norse legend, but it sounds cooler and has some other implications) ...

we are like ants that crawl around this tree and discover and learn new things as we crawl around

most of the food and nutrients come from the ground and need to be delivered up the tree, but the leaves and warmth and otherwise good stuff tends to exist on the outer branches where there's sunlight

the further you get up the tree or further out to the far branches, the more we as ants depend on other ants to fire brigade the food and nutrients we need

but the ants form networks and communities to allow this because the far-reaching ants bring back leaves for them too and are helpful in their own way of exploring and finding new leaves

so the further you get up or out, the less attached or 'grounded' you are to the hard work and 'real life' of the other ants

but something else rather strange happens, as these exploratory ants get higher and farther, and as they get more specialized in exploring that world/domain, the harder it gets for them to communicate and connect with ants at the core because the further out you get, the more *different* things get

all ants the ants of course have certain things in common and no ant *started* way up the tree or out on those branches, these are universal commonalities (although some had better support networks and easier ways to climb than others)

but out on the limbs, each extending to a different universes, it tends to take over form these mental models

some ants are rather lethargic and are cool to not travel too far and things are good enough, and being too far out means there aren't as many ants and it's a less social and more isolating space out there as things branch out (and simultaneously narrow)

some ants want to see how far out they can get and just keeping walking in one direction, first zipping along the common and well-worn path and then gradually beginning to form their own (forging the way and marking the trail for others)

there's a phrase in consulting i tend to like, but extends to other fields as well that: ***we know more and more about less and less, until we know everything about nothing at all***

anyway, i've always imagined this like an ant way out on very thin branch cutting & collecting fresh leaves (earning money) and then bringing those back for the upstream network of ants

as for me ... i've always imagined myself as an ant who lost his keys somewhere and has had to drift through all these different layers and branches and not speaking any of their languages and just trying to explain what *keys* are to other ants using only mime (which is rather hard and frustrating for an ant to pull off!) ... but ... the search for my keys continues ...

ok, ok, that's the gist of the metaphor, what does this *possibly* have to do with cue?

well ... the cue community right now is very smart and very far out on some very special branches, but that makes it that much harder to relate to those on other branches, and some are very locked in to their various modalities

some universes that spring to mind are web devs, which are further branched into front-end/UI, API Endpoints & (Micro)services - consumers & producers, also WASM and other sub-areas

html/javascript/css, frameworks like angular/react/elm, graphql, etc., etc.

backends being mostly Go now (due to cue's relationship, but this will branch out) and producing these mutex'd servers and endpoints with JSON/Protobufs/RPCs/etc., etc.

also the ops crowd creating docker clusters with kubernetes and doing resource allocations and connecting various ports and service coordinations

also the policy/security/data management crowds who look down on those networks to ensure only the right ants have access and that the ants are being optimally utilized and that the branch as a whole stays healthy

but there's also the formal logic and programming language theory crowd with their own lexicon and ideologies constructing the language that these other groups use

there's also an overlapping unix/linux/plan9 community concerned with shells and streams and keeping things simple, (tree management?)

separately there's also crowds/communities for: AI/Machine Learning, Data Science, Grammar/Language/Linguistics, Graph Databases, Linked Data/Semantic Web, Relational DBA's, NoSQL DBAs, Pythonistas, Literate Programmers, VR/AR Developers, etc., etc. (edited)

okay, okay: it's no surprise to anyone that's there's lots of kinds of developers, but this tree of ours is growing and and the complexity is increasing, but that's a good thing because there are rewards in that, but logistics becomes an increasing complex challenge and also of increasing importance because of the severe risks to mismanagement

so, the issue then is one of communication and knowledge representation so that information can be better curated and shared

but there isn't one universal language*, nor should there be,* that would harm those outer communities which have specialized for a *reason*

what's needed, instead imho, is a *transformable* language, or *interop*

it can be a dictionary in a jupyter notebook for data scientists, which can be a struct for go api developers, it can be a object for javascript developers, it can be an svg vector image, or a lottie animation, and it can transform between these things by having transformations between these

but more than just a transform, it's also a *contract* between these parties that describes what things are and knows if/when things change, and it's describable in each of the languages of these parties which they both agree and understand

using not only prosaic words, but math and logic and pictures which show its structure

i think of lego's excellent universal visual language, or ikea's assembly instructions or bandai's gundam instructions

some might say that what i'm describing is plain text (e.g. unix) or json or pure mathematics & symbolic logic (e.g. haskell smart contracts) or something

json has kind of emerged as the standard in terms of: value, list, lookup - even simpler than xml

but it's a format for machines and not for humans

cue not only makes it human friendly but allows for the (type) checking and patterns/groups at many layers of abstraction - i.e. high/low level), it allows for *shapes*

and it allows for gradual build up and composition in (nearly) any sequence

i think of cue as a data language, or a description language, or a knowledge representation language

i cringe every time i hear it described as a 'configuration language'

because, while true, and it's original and defined purpose, it's much more than that, and this term is particular limiting in it's scope and in its value

modern business is run on excel (or excel+other systems)

(perhaps better to say spreadsheets, but most would say excel like kleenex)

and excel is 100% configuration

unless you are writing .NET code and *making* excel (which 99.999% of people are not)

you are filling out data in a particular way with particular shapes, patterns, and rules - defined by a 'configuration language' called excel formulas

anyway, i have to run but more on this later, happy sunday
