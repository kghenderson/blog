# Cue is Proficient, Fluent & Friendly

a friend mentioned something to me the other day about cue needing an elevator pitch and this has been rattling around in my brain, but so far it feels good, doesn't need to be official or anything; i can like it anyway

haha, the dad in me want to put this to song somehow, but not going to do that

Fluent = Fungible, Logical, Universal, Extensible, Natural & Typed (edited)

(although it's still a first cut, i think it embodies my favourite cue qualities)

**Fungible** speaks to its ability to interoperate with equivalent data: like if you have any kind of data: json,yaml,text,dataframes (someday), you can store it in cue and get the same thing back, you can trust it, like a bank or like a fungible token, you can freely exchange your data in and out of cue

**Logical** speaks to its ability to 'bring logic programming to the masses'. It applies the more structured world of math and logic to the world of programming. X is X and it's a placeholder value like it would be in other programming languages. It applies formal logic, but it makes it very easy and accessible - but the fact it embodies this trait is delightful. It maintains your confidence & sanity.

**Universal** in that it works with *any kind of data* and *in any environment.* Whether it's you desktop, a cloud/docker environment, a web browser, your phone, cue can work there.

**Extensible** because if you want to handle cue in with just running bare commands a terminal, that works. If you want to do shell scripting (in your shell of choice *(including cough nushell),* and using pipelines that works too. If you want to incorporate it into your Go stack, it works. Want it as a Python library or Ruby Gem or Rust Crate. Also works there too (eventually). Use it how you need to. Also permissive licensing. Also support contracts & available professional services (soon). i.e. not only can you use it where you want, but the community will also support you.

**Natural** because of it's zen-like natural beauty (yes, really, more on that to come). I learned not too long ago that traditionally a Haiku *must* refer to nature for it to be considered Haiku, and not just a poem. Regarding these zen qualities of bi-directionality, artistic placement and literate qualities of the author but with some rules (we're not heathens), e.g. the auto formatting, the grouping data structures and relationships to others, etc. (we can come back to this, but much more here - see [aquascaping](https://www.youtube.com/watch?v=lD7k6MRsTz8) for a a great calming sunday). In addition to this though, CUE just fits naturally in these other (extensible) computational environments and doesn't try to take over. CUE's a friend to your environment. (edited)

**Typed** because it's *structured* data, and this is absolutely critical, imho, to any modern data environment or platform. The data knows about itself, from multiple sources and angles. It doesn't need to say within this file, we can describe it externally, but these descriptions, and someday hopefully more to be be *literate* descriptions, mean we can visualise and understand it much more easily. Particularly once we smarten up our editors (a lot more). Then you can download a structured data file and separately download (automatically) the api descriptions, and 3rd party annotations/translations) and now the editor or AI assistant or application or whatever your interface can know what to do with it. I do love the Unix ethos of plain text files, but it's time to move to structured text files and structured pipelines. Still open, readable formats and no binary, vendor-proprietary stuff, but structured. (edited)

cue is **fluent**

cue is fluent in the same way a trusted, friendly & fluent person speaks and translates between many languages and like a good translator follows up to make sure you actually *understand* and aren't using the wrong fork or bowing too much or not enough. cue's got your covered.
it's fluent in the sense that it knows the cultural customs (contracts) of the interaction between parties. cue *understands*. (edited)

okay, okay, perhaps super sappy, but to me, ***cue is fluent and friendly*** (edited)

**Friendly** of course because it's easy to understand and easy to use. It can be worked with in small pieces using very basic and universally recognised building blocks: *the value, the list and the lookup.* (edited)

subtle note to self here on separate rant re: naming, but for this usage, a value is a literal, concrete value. the list is obvious, and the lookup is a key/value pair (map/struct). but this is way simpler terminology for regular humans to grok. (edited)

another note on the critical importance of friendly, and the topic of its own future ramble, is that prior to cue, i explored many other options (in fairness, it was before i knew cue existed, and you always find the right thing in the last place you look (jeff foxworthy joke))

anyway, i had very seriously considered using [dhall](https://dhall-lang.org/) or [nickel](https://nickel-lang.org/) and both of these also excited the inner geek in me (ok, well, maybe not so inner). but i'm excited by "functional" environments like nix and language expressiveness and so on because i want to work on and solve really, really hard problems, and go further and make working on these *hard* problems even easier for the next (and current) generation! we have hard problems to solve. in my own teeny, tiny, nerdy way, this is how i choose to spend my time because cue is making hard problems easier to work on and the more accessible that becomes, and capturing the 'why' and 'how' logic of it all, means we're collectively a step closer to solving the climate crisis or energy crisis or wealth stratification crisis or social-media/education/fake-news crisis (from either side you're on), or the kevin interrupting my weekend by continuously posting on slack all morning crisis! (edited)

anway, i've read and studied (non-professionally, strictly for interest) ... about haskell and idris (with *first class* types!) and scala and [reason](https://reasonml.github.io/) (and many more, but these are some modern super type-heavy systems) ... i truly want to love writing in *[unison](https://www.unison-lang.org/)*! (more on that as well later) ... (edited)

sorry, this isn't a humble-brag, far from it, i couldn't really get *deep* into any of them (but i do 'get it' ... mostly, it gets pretty far out there ... and further than i'm able to go before i get dragged by my ankles back to reality ) (edited)

alternatively i've also gone down the graph database & linked data route with OWL reasoners, inferences, RDF/Triples and so on in the search for capturing logic. Also things like: Java [Drools](https://www.drools.org/) (with BPM, BRL & BMRS - Business Rule Management Systems) or [Red Hat Process Automation Manager](https://www.redhat.com/en/technologies/jboss-middleware/process-automation-manager) ... (edited)

aaarrrggghhh ... unless you're ready to roll out SAP or an IBM Cloud, it doesn't really help people, and it never gets anywhere (edited)

the point is ... none of these other languages work, because the people in the business environments, and my colleagues, have zero (actually much less than zero!!) interest in them, and they aren't interested in learning them, and they aren't going to use them unless it's *supremely* low friction (edited)

but then it's *so* low friction that errors are so easy and common that it *must* be constrained locally where they can see the problem itself, and we can write nice, easy, understandable language on what to do for them ... and that git is right there (behind the scenes) to provide that also critical *undo* button (regardless of editor), and also the diffing capability to see *what's changed,* and then that streamable, workflow-readable (i.e. architect review) into a changeset pipeline before it gets applied to the bigger system ... and then the system itself can test, apply or rollback as well (edited)

hell, i'm writing here in slack because i'm too lazy or neurotic to use text editor or write a blog like a normal person, but this is the least friction and seemingly the only way to make it happen. ...we all have areas where we choose to focus and other areas where we just want things to work so we can keep our attention on the other problem at hand (edited)

and moreso, tools *shouldn't* be the focus when you're working (more on that too), but when you're *working* or *in the zone* then the tools (and language! needs to *disappear* ... the best language is the one that lets you think and collaborate most effectively _*for what you're doing*_ *without needing to think about it!* the best tool (pencil, chisel, chainsaw), is one you don't even know you're holding so you can focus on your art

of course, like how people like many of us we focus on technical tools & languages for a living, the people using those tools (including us), shouldn't need to think about them, they should *fit in*

sorry, off on another tangent ... the point is ...

absolutely critically, **CUE is Friendly,** because the entire team, both technical and non, can use it and see it and explore it. I'm using CUE and not Dhall because CUE is something regular people can use and understand.

and don't get me started on python, that's a *disaster* ... it has the *illusion* of easiness, and maybe contained within a Jupyter notebook or something it's easy, but for anything of substance ... having to explain global vs local, virtual environments & shell 'activation', dependency management, runtime environments, argh! no. (listen, i know how to do it myself, but anyone who doesn't see this has never had to explain to their mom the difference between mac's native 'python' being python 2, and homebrew's python being 'python 3', but also that's the *latest* python 3, and not the one in the project which has different dependencies ... it's not simple, nor easy ...

Cue, and Go, while they're still being refined are far, far simpler and really only need a single executable, and everything can be set up and pretty much automatic for them (more on this to come as well). This isn't no setup, but, and I know it's not turing complete or anything, but for basic data processing, CUE is perhaps the simplest and most flexible (but structured & correct) language ever. type hello in a text file, put double-quotes around it ... run it, done.

CUE gets in the door, whether others don't because it's friendly to users where others aren't

*note that cue is new and the tooling is still getting there, but is has this potential

cue works for the whole team ... as a techie, i love it, and as a systems-supporter/trainer/maintainer, i love it too

<eom> ... for now

i can't wait to add 'Graphical' to cue as well, but that's i suppose a part of the ecosystem ... we'll get there, have lots of ideas for this

^ coming back to this a bit later since i had to step away, but i've been thinking about my hiring rules for new team members (none are my own but still valid) ... 1: i think of Joel Spolsky's hiring criteria for: Smart & Gets Things Done, 2: i think of a previous company's rule for passing 'The Beer Test', which isn't any kind of hazing or anything, just ... would you want to grab a beer (or anything) with them after work. Do you *want* to interact with this person - even bonus points sometimes for eccentricity but you know, do you trust them, are they personable, etc.

anyway, smart & friendly (and trustworthy) were covered with the above, and also, things tend to go best in 3's, so ... I think the final adjective/adverb/modifier would be ...

**Proficient:** i.e. practical and efficient at getting real work done

this may seem obvious, but this is another huge draw to cue for me ... think about setting up a graph database or jboss enterprise server or a new local cloud ... not that you can't do these things, you can ... but all you need is a single binary, that's it cue.exe (really just cue on mac/linux, but that doesn't have the same ring to it without the file extension.

but download ONE file and your up and running

a file that you can have upgrade automatically or keep with your project or whatever you want to do ... but you're started in literally SECONDS being productive (assuming you have an editor set up, but then MINUTES) ... this is a far cry from setting up OpenShift

anyway, you're immediately productive and supports pretty much any tooling developers are currently using

even the language will probably be almost immediately familiar to any developer

no massive training or anything needed to get started, and this is yet another huge selling point

haha, i think it needs another 'T' word like Terrific so it can be: Pfft (sorry, did i mention i'm a dad? i just can't resist ... )

^ cue is a genius-level nerd who gets shit done and is super friendly

i realised that after talking about cue in this way that ... well, *cue's who i strive to be*

but then i also couldn't shake this elevator scene from [mad men](https://www.youtube.com/watch?v=LlOSdRMSG_k)

and thought it should toned down a bit

that said the scene itself rather emblematic of the whole cue situation ... but *BOTH* the ~~nerds~~ intellectuals (self-referencing here) can be happy, and the don draper's *don't need to think about it* (because their business operational and continuity concerns are also taken care of) ...
