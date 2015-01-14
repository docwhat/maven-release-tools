Maven Release Tools
===================

The built in maven-release-plugin has been known to be fragile and problematic
for a long time.

These are some tools for doing releases without using the maven-release-plugin
at all.

These tools were meant to help implement a process similar to the one mentioned
in Alex Fontaine's blog post, [*Maven Release Plugin: The Final Nail in the
Coffin*](http://axelfontaine.com/blog/final-nail.html).

mvn-version-release-bump
------------------------

This tool removes the `-SNAPSHOT` part of the version from the `pom.xml`.

If the version already doesn't include `-SNAPSHOT` it will quit with an exit
code 42.

The output of this script is meant to imitate `mvn` output so you can parse it
or highlight it with your normal maven logging tools. For example, in Jenkins
we use a plugin that marks `[ERROR]` lines red for easy scanning.
