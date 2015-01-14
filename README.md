Maven Release Tools
===================

The built in maven-release-plugin has been known to be fragile and problematic
for a long time.

These are some tools for doing releases without using the maven-release-plugin
at all.

These tools were meant to help implement a process similar to the one mentioned
in Alex Fontaine's blog post, [*Maven Release Plugin: The Final Nail in the
Coffin*](http://axelfontaine.com/blog/final-nail.html).

The output of these scripts are meant to imitate `mvn` output so you can parse
it or highlight it with your normal maven logging tools. For example, in
Jenkins we use a plugin that marks `[ERROR]` lines red for easy scanning.

mvn-version-release-bump
------------------------

This tool removes the `-SNAPSHOT` part of the version from the `pom.xml`.

If the version already doesn't include `-SNAPSHOT` it will quit with an exit
code 42.

mvn-version-snapshot-bump
-------------------------

This tool increments the version and adds the `-SNAPSHOT` part in the
`pom.xml`.

If the version already includes `-SNAPSHOT` it will quit with an exit code 42.

mvn-reject-release-version
--------------------------

If the version already doesn't include `-SNAPSHOT` it will quit with an exit
code 42.

This tool is meant to prevent building non`-SNAPSHOT` builds when running
code-verification (for example, with Gerrit).

mvn-current-version
-------------------

Echoes the current version from the `pom.xml`.
