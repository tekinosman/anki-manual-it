# Packages Distributed by Linux Distributions

We have seen a lot of issues caused by the customized versions of Anki
distributed by Linux distributions:

- Anki depends on third-party libraries like Qt, and Linux distributions often
  substitute different versions of those libraries, without testing the impact
  of those changes.
- Sometimes the version of Anki they distribute is years old, or is an
  alpha/beta version not intended for stable release. Distributions will often
  disable the built-in update check as well, to prevent you from being notified
  of newer versions.

Compiled builds of Anki are available on <https://apps.ankiweb.net>. Most of the
necessary libraries are included, and Anki has been tested to work with these
library versions. If you're experiencing issues with your distro's version, the
first thing you should try is switching to the latest packaged version we
provide.

You are welcome to continue using your distro's version of Anki if you prefer,
but if you run into any issues, you will need to report them to your
distribution's package maintainers.
