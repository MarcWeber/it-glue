# it-glue
Cross platform cross language cross DSL to setup computers and dev environments

# analogies

Recipes are to cookies as it-glue is to PCs.
Nix is to packages an it-glue to dev machine

Be automatable (smart) recipes to install VMs and software for production or
development.

Give answers to the question the piece of code I have in front of me will it
run on my machine faster ?

# Problems with state of the art

Nixos fails at Windows and not being predictable how much time it will take to
package something.

Brew and conda(mamba) eventually miss out on packages

# Solution
know the package managers available on a target system.
add the packages you care about.
Solve and get a dependency tree about how to setup and install and the
configure the software so that packages not provided by the host system can be
added by whatever means.


# Features
be declarative for simple thing.
Allow imperativity if needed
Have kind of GC to remove unused features again
for each recipe allow defining some default actions such as open editor,
webbrowser, run tests whatever
target many distribution systems
Simple thing should be simple such as:
file system, PHP, mysql, install Wordpress

# Examples

Please mind these are sketches only.
The final design might differ.
Open examples and read the description to understand the intention

[story compile and run on multiple operating systems](./STORY-compile-and-run-on-multiple-operating-systems.md)

[story godot_libc_dependency_pool_example](./STORY-godot_libc_dependency_pool_example.md)
[story install and clone wordpress](./STORY-install-and-clone-wordpress.md)


