# Creating an organisation-wide gource animation

[Gource](https://gource.io/) is a tool that creates animations of the changes in a projects.

The most common usage scenario is to show git commits over a period of time, but it can display any kind of information[^1] that follow the defined format.

Although gource is easy to use when called for a single repository, it can be a bit more complicated to create an animation for an organisation with multiple repositories.

This guide will show you how to create an organisation-wide gource animation, both an all-hands overview, and individual videos per contributor.

[^1]: Some examples form the [Custom Log Format page](https://github.com/acaudwell/Gource/wiki/Custom-Log-Format) are
Bugzilla, DocuWiki, JIRA, MediaWiki but there are also visualizations
of [the COVID19 Corona virus](https://github.com/sulmar/gource-covid19).
