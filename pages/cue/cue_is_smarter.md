# Why cue is smarter than me / AR

so ... this isn't a "true" statement or something, it's just a way conveying a realization i've taken for granted in thinking about cue

it's just this: 'cue is smarter than me'

i need to of course unpack that a bit ...

this has nothing to do with self-esteem or self-view, not going there, it's all good ... but as i've talked about in earlier threads, being a developer (of a certain type) means feeling/being wrong most of the time

also, i'm not talking about things in life here either, it's not my world view (but not altogether dissimilar), but as a developer, being developer, developing systems, when there's a problem ... i tend to just start with the assumption that somehow/somewhere it's my fault (as a developer)

e.g. a use case was missed in the code or i didn't handle something somewhere properly and bad data made it somewhere it shouldn't, and i have no hard numbers (and don't even want to go down memory lane to think about it), but i'd say it's usually the case, but you know ... we work in teams and people are fallible and you just learn from it, fix it and move on, and that's all good

if you planned in the beginning for *everything:* then nothing would ever get done and it wouldn't be pragmatic because it would be immediately complicated from the beginning to prepare for things that almost certainly *won't* happen ... so you just anticipate what's likely and/or what would really be mission critical, and take frequent backups and do the best you can

anyway, i suppose as an extension to this, being a developer and writing in a multitude of different languages depending on what i'm doing ... i don't really think any software i develop with is "smarter" than me ...

oh, it is "*better* " than me *for sure* ... i could never do in my head what Excel does or SQL or Python or Go, etc. ...

sure, they were made by smarter people, but those people (or thousands of people over many decades), made tools and as such ... now matter how advanced excel may every become, i just might be having a bad day and forget to use a round function and get the wrong results

and ... that's okay ... that's what testing and UAT and such is for (hopefully), but i'm just saying that Go is brilliant, made by brilliant people (likewise for other languages), but in the end, Go (or how my dumb ass writes it), is mostly only as good as what i tell it to do, and as noted above, i'm wrong (in dev) a lot and usually i know better in the end once i realize the ~~bug~~ feature that i'm now trying to fix.

so Go is like having some amazing cyborg assistant with super speed and super strength and crazy dexterity going to the store for you and just still buying the wrong thing because that's what you told it to get for you

and again, this is a bias, i can tell CUE to do the wrong things too, but I just .... think about it differently .... because the order doesn't matter and there are universal statements and so on ... i just, in my head, think to myself that the CUE (i wrote) is probably right and i'm probably wrong

like ... if I have a problem in Go, i think to myself that i messed up writing that the Go code in the first place, and that the code is dumber than what I know now, it's a biased assumption that (my) dumb code is wrong

but even though sure, I can mess up my CUE code just as much as my Go code, because it has this memory and it's not imperative - i haven't really "told" it what to do, i just "described" things .... it's like I know that in many cases I think to myself, yeah CUE, you're right, now what did i do wrong

haha, i'm not saying this mental dialogue is normal or anything, it's just something that struck me that maybe my cue code doesn't *start out* smarter, there's a tipping point where I just implicitly trust it to check my work ...

and when I fix it in CUE, the model gets smarter, but when I fix it in Go, it *functions* better but it's still ultimately only as good as I can create, and I tend to forget things (and CUE doesn't)

of course, tests help with this, but i'd feel a lot more comfortable and confident in my work if cue could help me make those too ...

this mindset not only applies for the small projects I make myself or with a small, targeted team ....

take a big, established project and the wisdom of crowds and the test of time .... completely different ball game ... if I think I've found a bug in the linux or NT kernel or something, I didn't, it's me

0.0000001% of people can confidently know that they've actually found something there ... just trying to show an example of "dumb" imperative-style programs that *are* smarter (in perception), just that it takes a village and time

what's rapidly approaching though, and already exists in many cases is where AI, artificial intelligence and not even *general* AI / singularity kinda stuff ... just as machines and algorithms get smarter we don't call them AI anymore (except for marketing reasons) we just call it Cool Tech

do you consider the route navigation in Google or Apple Maps considered AI? is it unthinkably smarter than us to know the time and place and traffic conditions and road hazards and concert events to find the best route at a particular time? yes. is it super-intelligent then? yes. is it AI? ... maybe?! but maybe not since it seems so deterministic and algo-driven?

(some) people think: no, it's just a really cool app, a really smart algorithm, good code ... but ... machine learning and deep learning does help refine these algorithms as well ... even if the end result is "just an app"

point being, AI is already here of course, but it has some perpetual future vague-ness to it, that means we kinda never get there, even though we reap the benefits all the time, once it's useful it seems, we just call it something else ...

anyway, where's this going? well ... these "services" or "apps" that are out there which are super smart of course (thank you Spotify music recommendations!) ... are mostly out of reach beyond their mobile applications or proper developers who can code in some language compatible with their sdk's

a lot of the value that we want from these services are in fact in there somewhere, but it's not cost effective for the companies to include those things in their app and it might confuse some users who would complain it's now too complicated then tell their friends (or twitter or an app store) and it would affect sales ... so it's just really never gonna happen that way

so there's still huge value locked in these things, that won't really make it to yours because their app is "official" and needs to be kept basic

i guess i'll stick to spotify, because i heart music ...

there's a whole class of functionality and value in say a thing that can take 2 people's profiles and extract a list of their liked songs they have in common ... maybe even further ordered descending by their total actual play counts

given 2 people, count of liked songs in common, top 20 song names that they each have played the most, then make a playlist out of that and share it with both people

i have probably hundreds of other spotify/music related things like this (not saying they're good) ... but it would be cool, shout out to [@rogpeppe](https://cuelang.slack.com/team/UNP3X7ABS) who's not only a musician himself but also has very excellent musical taste

(haha, disclaimer, i've come to learn in my life that music is 100% personal and people listen to things in different ways for different reasons and that everyone hears the same song differently - but it's a great feeling finding people who hear similar things, but a topic for another time)

ok, so this 'compatibility playlist' let's call it ... and let's assume all of that data is accessible by us in their api somehow ... it's a totally valid use case and something that for corporate business reasons they wouldn't want to pair the wrong people or disclose unsolicited individual listening habits ... probably won't ever happen from them, and that's okay for them - that's not the issue

but if i have my api access token, and roger has his token, (he doesn't need to share it), but we should both be able to run and 'extractor' script, and mash them together, and get the output somehow

there are services out there working on this, and i respect that, but they're also in the "cloud" and i don't necessarily trust them to give my api key/password to ... i just want to do this locally

so, this can be done, with python or go or something, but right there you've got a huge, huge problem because as 'easy' as those my seem, there's quite a lot to get started before you even get to the script

and you probably start with importing an existing 'package' which simplifies what you want, but .... is it still current, can you really just trust anything found on github and run it like that?

you're not really discovering anything, it's still not exactly easy, and probably feels like your fighting it most of the time

with cue: (or rather the someday/future cue) ... you can just have a simple file/UI, and ask their api what it can do and it can return a response with comments, querying directly without the middleman packages

and you can kinda just start describing things and adding constraints and working rather interactively

and something else related to this being able to (eventually) just speak your constraints and cue can handle the ordering and perhaps show a visualization with your augmented reality glasses to ask back ... do you want to filter then sort or sort and then filter ?

but you can also build your own DSL (domain specific language) at runtime too, not just things that are pre-determined

you can (someday) *tell* cue 'cue: this are my kidsafe songs' or 'cue: this is not a kidsafe song' and it can decorate those things because they're simple assertions and not imperative actions (although that's a thing too it's a separate topic)

but also, your definition of 'kidsafe' can include your own personal list, but easily mesh that with spotify's (or another third party list) to exclude profanity

(of course, these aren't some magical features, just saying that cue makes this style of declarative assertions with error checking and warnings easy, and it can magically bubble them to the right place in the value lattice to know it's space in the knowledge model and if it jibes with the other things you've said about it ... and it wouldn't just kick it out, it can allow you to prioritize one statement over another or revise a statement, and keep that change to the model secure and tracked)

so ... by also being able to make cue statements and assertions based not only on your own but mesh it in with other 'super-intelligent' services, cue then becomes even way, way super smarter (but more to come on this)

just to recap: you could write code in prolog or make a knowledge graph with OWL or something to do roughly the equivalent, but's CUE's extreme simplicity: 

1: brings it into availability of non-coders (maybe power users, but there's a lot of smart kids/people out there) 

2: it makes it easy to mix your data and others data to make custom things easy

3: it easily allows you to make up and use your own vocabulary and it can handle (eventually) the background mapping so your own short-hand words translate to those outside services

4: by being so declarative, we can dictate in AR/VR our questions and assertions and have it auto-organize and help decipher our data for us

5: this can potentially generate new revenue for *companies* because users would pay extra for these capabilities ... and please services, don't make it an annual developers fee, go for scale and let more people get more value from it

i have another ramble (someday) on how the very structured nature of CUE is especially suited towards graphical representations as well, but i'll save that one for now

anyway, once again, cue rocks
