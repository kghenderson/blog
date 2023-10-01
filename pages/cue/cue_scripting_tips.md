# Some CUE Scripting Tips

for scripting, i'd recommend having a non-tool file in the same package and put your lib & solve code in there, and then just refer to it in your script

my personal practice (not for everyone, and i'm pretty lazy), is to create a folder, `solve` which has a solve.cue and solve_tool.cue inside of it and a matching command called `solve`, then i use this little shell script which runs cue cmd $dirname and does both an eval and export to files for the non-tool, and keep that file open in a separate pane in my editor so i can work with the cue code on the left, rerun my script with a binding (cmd+e in my case), and see the output on the right as i'm working

don't need to use this tool of course, but the concept is pretty simple

and get nice editor features for the output file like syntax highlighting, structure pane, search, etc.

also trying to make some easy for my colleagues to use without a lot of setup

also, on cuetorials, tony points out a trick that you can store the content of a command in the matrix (my personal term for the hermetic cue lattice), and then just unify it in the tool with the actual command

e.g. your download struct, you can calculate the cmd & std in the matrix where you can see it, then download: exec.Run & yourCmd

fyi, i wrote a little shell utility to do the above: https://github.com/kghenderson/cue-companion

still a work in progress, but it works for me

oh, and for completeness, forgot the obvious, that within a script i often just use 'print' statements that yaml.Marshal whatever struct i'm playing with or other messages (but note that you need $after dependencies sometimes for them to make sense), if the output is large you can file.Create instead of print

---
credit to massive (on slack), for symlink technique 

Ha, I’ve had the same problem. It’s painful to debug _tool.cue files. One poor man’s workaround that I’ve found is as simple and stupid as:

ln -s foo_tool.cue foo.cue cue eval foo.cue

That way you can work around the odd restriction that you can’t eval tool files. Added bonus is that some times you even get error messages, whereas `cue cmd` just silently does nothing.I’ve never quite understood why tool file can’t be evaled directly.You also need to remember `rm foo.cue` before you try to `cue cmd` again or Cue gets stuck. (edited)
