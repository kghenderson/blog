# A common evolution of developers wrt to managing complexity, dunning-kruger

the last ramble was on time, no more of that, but this is more of my own evolution (and something i've seen in other developers) for ways to deal with complexity a typical evolution of developers

ok ... so, i'll repeat this is *not everyone,* this is based on personal experience, ymmv

a jr developer, not feeling very creative rn, so let's call them, *devvy ...*

devvy is given a problem to solve like calculate the gross sales for a given next year, given a quantity of units, and cost rate and here's the amount dollars

so devvy reaches to excel and keys in the formula and that formula is the simplest, most obvious thing that solves the problem, and all is good

i'm quickly realizing this exact analogy will need more work than i have now to really pin down into a good example, and i want to keep this topic more related to dealing with nesting and forms of abstractions and composition most importantly to keep it relevant how exactly it relates to cue, so i'll have to ditch the formula for now, so just ... take it easy on me please, just trying to *rubber duck* it out here now

ok, the point of this first example is it's Units * Rate = Amount, and it's wonderfully (overly) simple

.... yada, yada, yada, .... now devvy realizes that well, rates have discounts and they're different in different markets/regions and have different rates at different times of the year

and they realize that units aren't so clear-cut either, at first they were just some nice whole round (positive) numbers, but now ... well ... can you buy half an apple? what about things sold by weight, or in bulk units, and well if they buy in bulk, shouldn't they get a discount, and does that affect the rate *itself* or is it really some extra thing like and adjustment to that amount?

and about that amount ... well, don't even get devvy started ...

turns out they have different local currencies which you can't add together: pesos+yen+dollars? no, also, we *do* still need to sum them up, so what should the base currency be, and omg, the rates change over time, and finance's rate is different from the treasury rate, which is different from the actual rate and different to what the point of sales system used ...

oh, and by the way it took devvy mucho time to discover that what? floating point arithmetic isn't exact?! and it compounds the more you add them up? and it compounds the more you use them in downstream calculations .... and now ....

now we have 2 versions again, because we have the versions *before* this mistake, friendly accident? happened, and the new restated versions, so we now we have 2 versions of EVERYTHING ... good times, and now we need to explain the difference! so we need to do them both, subtract the differences, and now we have a 3rd copy of those deltas ... and of course those now need merged into a 4th copy which has them also listed out in nice, neat little columns to show on a powerpoint somewhere

there are still a bunch of points to make here: 1: Units * Rate = Amount, is still useful, that actually ... still needs to remain true, even if our understanding of those things changes over time, and the granularity of how they're calculated may change over time, but in the end, every product should still ultimately have something like that

i'm overly simplifying here, but let's just take Units for the sake of this example

what started as "units" is still units, but it's be deconstructed, into smaller components: which ultimately *compose* this final units amount ... if we're buying boxes of cereal, the company making the boxes needs to make the right amount of boxes, so their "units" are individual, family-sized packages (which they probably still call units), to the shipping company, a 24 pack of boxes is tied together and to them that might be 1 shipping unit (which they just call units), and to the devvy who just bought the 4-pack at costco, er, amazon, devvy just bought 1 unit too, "i'll have 1 unit of cereal please" (edited)

haha, anyway, one inclination is to come up with a global list of vocabulary and get every to change names so get the boxing company to instead call them 'package units' shipping company to use the term 'shipping units' and store to call them ... 'store units?' ... that'll solve these miscommunications right?

no. no it won't. have simple, localized, easy to say and spell words (scribbles/symbols & fast mouth noises), let's you *not think* about what kind of units you're talking about but focus on *making* the boxes or *getting* it there or making them available to customers

in this sense, "unit" is an analogy or abstraction that is useful, and giving that meaning within whatever *context* your trying to use these is a 2-way (but still mostly one-way) agreement between parties who can choose to interpret that how they need to, and that agreement can't just be arbitrarily changed to mean something else

of course, of course, people change these meanings and terms all the time, and if you're just a downstream consumer you may have no say in what they call things, and these broken agreements/missed communications do happen *all the time* and also go through that variance analysis inception when it's sometimes later discovered, but i digress

the point is, we care here about the case where two or more parties are friends/partners/reliant on each other in some way and we want good communications and a good working relationship

ok, what has devvy learned: don't fight the tide, let everybody give you their own 'units' and devvy can rename them as needed, but devvy at least needs/wants *some way* to know if/when another party has changed their syntax (format) or semantics (meaning) of what they're being provided

another thing devvy has learned, is that if some just breaks it's obvious ... devvy has literal nightmares about the worst case scenario where the meaning is changed and other people start acting on the *wrong* values but nobody *knows* it's wrong (yet) until somebody at the very end of the train (the retailer in this example) didn't get all the cereal they paid for and wants either free boxes or their money back or they're going to find somebody else to provide their cereal instead ...

that's bad for every company in that ***shared*** data community/pipeline, everybody hurts ... the packager, the shipper, the retailer, and ultimate devvy's 5-year-old who just wants their cereal ... and really, how can you be so mean to kid, it's terrible

it's also bad for devvy and their whole dev team who now have to branch the whole system, figure out when and where this happened, and run a 'do-over' to get things corrected and so on ...

to just keep on this, we *want* the world to be more automated, we *want* to focus on harder problems, more fun games, better environments, better efficiency, etc. (of course)

and the more automated and intertwined all of this becomes and the faster things are processed, the *pace* and *scale* of these outages just become mind-boggling, i'm reminded of maybe it's 'i love lucy' with the chocolates or 'laverne and shirley' at the brewery (old tv shows) ... but the point is it goes from being an *annoyance* to be *complete disaster* if we don't get these things right

particularly because companies are outsourcing (my personal opinion is it's really good for companies/communities/disciplines to specialize), that once upon a time, devvy had all of the data and the resources in house to tackle this when the company was small, to now something that could literally involve thousands of people across hundreds of specialized systems to solve ...

to me this isn't scary, it's the right thing, these systems are *better, faster, more efficient,* having specialized the developers get to focus on particular types problems ...

it's just an example to highlight the utter *necessity* of compatible and evolving understanding of data and relationships and cooperative, community understanding of the how/when/why these operate ... and really to my next point ....

systems now require a new type of system to understand systems

it has to be able to compose (build up) from all of these small little pieces, each managed and owned and has responsibility by a different party, to be a 'trusted partner' in these ecosystems (and there's many, not one)

we're building new data societies and a trusted networks with new rules

ok, sorry, too much off into the clouds again ... bring this thread home pls

cue works with and between formats, cue can be versioned and validated (e.g. git branching and backups), cue can build up from small pieces

cue can make sure the system *errors* to avoid the *worst case* where everyone is using the wrong thing but nobody knows it yet

cue is easily readable and document and hello literate programming & structure documents

cue can easily transition in and out of code and data and markup

want to read some code out of a database and store it in a document: cue's got you. want to put some code inside of markdown and have it spit out the code to some folder when it updates? cue's got you.

want to store your cue in a database? check. want to have a plain text directory checked into git and have cue read the code out of the database so you can store it all in a zip file you can store on a thumb drive and version control? check.

want to record the audio or video of a meeting and have a web-service transcribe the audio to text and save it in the right file and email all the parties in the meeting: with a little elbow grease and an assortment of tools, yes, cue can help do this too

and it does it in a way that 'makes the easy things easy and the hard things possible' (uhh, but still in the easiest possible way)

so, i'd originally intended this thread to go in a slightly different direction, but i guess i'll have to save that one.
