# Building CUE from source

wanted to mention something else here as well though (for that ticket)

that one a common way to develop is to use a virtual machine, e.g. linux on parallels or vmware, and then have that whole environment be for a specific project and using the global GOPATH where `go install` will place your compiled cue binary and then you'd have that path in your .bashrc/.zshrc environment. this is very clean way to develop. (not trying to start a flame war or anything, just saying it's one particular setup)

as i happens, my work environment restricts the use of virtual machines locally, and i *could* use a dedicated cloud-based virtual machine (similar to the above) but i'm old school and prefer to have files locally (in this case, on a mac).

so, i create a CueWs workspace directory, and then clone the cue project into a subdirectory there. This is mainly so that the editor files for GoLand/VSCode get created outside of the cue directory because the cue .gitignore has a warning about only including generated files and the editor subdirectories will show as changed files and mess with your git syncing by making it 'dirty'

then within a terminal inside the cue project, i'm using `go build -o "../_bin/cue" "./cmd/cue"` to create an `_bin` directory in the *parent* path (again, so as not to clutter the cue repository). the underscore in the naming is my own personal convention that some might disagree with, but it indicates to me that it's a *local* directory and therefore excluded from source control, same goes for things like `_logs` and `_temp` and `_archive` to keep them out of the way so to speak.

anyway, then i use the direnv [https://direnv.net/] utility, to add this compiled cue/bin directory into the path - most importantly, on a *per project basis*

this allows me to use homebrew [https://brew.sh/], to keep the cue command at the latest version which is what my users will be using, and what i need to use for some projects to *use* that version (e.g. the "real" cue)

but if i'm testing something for a particular project, i can use the PATH_add directive within a `.envrc` file to override the homebrew version, and use my custom-compiled version instead

note that there's a tool called asdf: https://asdf-vm.com/ which aims to do this too (and i've created a ticket for cue-lang to someday support this), but still that will only be for *published* versions of cue, and not those you might build or be testing yourself, so even *with* that, you might still need something like the above (for this janky dev setup) :-)

also, should be noted that `go build` and `go install` aren't quite exactly the same, but you can use direnv, or put in the same command to redirect GOPATH for the directory that `go install` will place your file.


^ this isn't *the best* setup, but if you're stuck on a single machine and need to support multiple versions of cue, this is just one way to handle it ... i.e. i'm supporting an application that uses cue and needs 0.4.3, also testing the 0.5.0-alpha, and also now looking to test features from the latest *master,* so this is one way to keep multiple versions on a per-project basis

FYI something you can also do is `go run ` `cuelang.org/go/cmd/cue@version` - that version can be a semver tag, a git commit, a git branch, `latest`, etc. It will be reasonably fast, because source downloads and builds are cached. The binary itself is not cached yet, so you'll still re-link a binary, but that shouldn't be *too* slow - in the order of hundreds of milliseconds.

if you want to show how one command behaves differently across four CUE versions, for example, this can be a nice way to do it - anyone can run the same commands without relying on an external tool like asdf.

for completeness (to the previous ramble), something like `GOBIN="$(pwd)/../_bin" go install "./cmd/cue"` will also work, but uses go install instead of build

i also have to work offline sometimes, and it's nice if you're developing external scripts & things that just running `cue cmd my_command` works the same way, and unfortunately direnv doesn't support creating aliases

asdf would still definitely be ideal for a number of reasons, it works with other languages like ruby, python, go, etc. and really we want our cue version to match what's installed on our *servers* and not necessarily the latest release from homebrew (or go install), of course 'vendoring' and/or storing a binary in the git repo directly can work too, but that also complicates things

anyway, just wanted to document what i have now, for better or worse, for consideration in future docs-and-content, it's actually really awesome that we have so many options and support so many use cases

i think these setups should be a community supported thing, because i agree that cue itself shouldn't care, and you don't necessarily want to have to *support* and maintain these various setups ... but i think community-supported guides for all different types of use cases will lower the barrier to entry and ease adoption. windows for example will also require different things, but we wouldn't want to leave people hanging and confused. or worse, accidentally breaking their "working" setups and then leaving them scrambling to figure out how to "fix" it (edited)
