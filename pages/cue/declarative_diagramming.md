# Declarative Diagramming, D2

fyi, saw this for the first time yesterday (behind on the curve), but looks very, very promising: **D2: Declarative Diagramming** https://github.com/terrastruct/d2

i'm a huge fan of diagramming tools, including graphviz, mermaid, plantuml, etc, but this is a new one

it's a freemium model where the 'core' is open-source and free, but we'll pay for extra features

and bonus points for being written in Go!

it doesn't have the same markdown/browser integration as mermaid (yet)

but it does have auto-rebuild from the cli, and could probably be easily workflow-integrated with something like: https://marked2app.com/ (for mac)

note that the *marked* app is purely a markdown viewer, and is meant to be paired alongside whatever text editor you use, and has swappable/customizable markdown engines depending on your platform & theming

in practice, it means you can use say vim to edit, but see marked refresh your document preview in another window

and it does a better job than say the preview panes in vscode or jetbrains

for future reference for others, another go-to of mine is to export to a nodes list and an edges list, then import those into 2 excel tabs of all things (although xml/ged works too), then using the free version of: https://www.yworks.com/products/yed you can import this list and use its layout engine, but also then allows you to group things and collapse/expand these groups, and interactively drag & move things and explore the workspace

^ useful for having a mix of auto layout and custom layout then taking screenshots

it pains me that https://www.graphistry.com/ exists, because *i want to try it so badly* but it's a cloud service and requires sending data remotely, and i'd have to get agreement from customers/management/etc to do it

re: D2, here's the hackernews link from yesterday where it came up, but has some interesting discussions: https://news.ycombinator.com/item?id=33704254

https://www.ilograph.com/ looks pretty interesting too, for interactivity - and supports both web & desktop

i really want to use ilograph but it's fairly expensive at $11USD/month, and i just can't stomach losing access to my own work, and i can't send info to (another) cloud with jumping through lots of hoops

i've grown quite fond of: Edraw by Wondershare: https://www.edrawsoft.com/

it's cross-platform: windows+mac+linux, it's not that expensive compared to other manual diagramming tools, you keep the software after purchase, it produces SVG's, has Visio support, and layers, importable/custom shapes, and it's fast & easy to use

a bit hackish, but a trick i've done in cue is to take a base map, then make a list of the map keys, then make 2 more maps: one from the index of the key the list (ID) to the key, and a second map from the key to the ID .

i love this because it's like making a little sql table with an integer primary key, and bonus points if the key/id is sorted how you tend to use it

*why* i do this, is that some keys aren't valid identifiers in mermaid, so by creating Thing1, Thing2 as keys, and doing the relationships Thing1 --> Thing2 in mermaid as well, then it's really flexible.

also, i end up making little 'feature' structs of objects with certain properties, and i use these id's as the dummy value for the map appending trick, so that i can loop those directly and keep them here as well

so it's like lookup tables ... you can't store these id's really outside of the Matrix (haha, my own new term for the hermetic value lattice?) ... but very useful *inside* of it

D2 is interesting indeed. I'm a bit inexperienced in this space, and mermaid would have been my go-to

not go, not open source, but functional elm: this was an interesting talk i saw recently from the latest strange loop : **"Diagrammar: Simply Make Interactive Diagrams" by Pontus Granström (Strange Loop 2022)** https://www.youtube.com/watch?v=gT9Xu-ctNqI

i wish i could see the changes in *thinking* and  use cue (and diagramming) to capture decision/outcome logic paired with technical diagrams
