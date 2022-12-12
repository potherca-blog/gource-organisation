# Creating an organisation-wide gource animation

[Gource](https://gource.io/) is a tool that creates animations of the changes in a projects.

The most common usage scenario is to show git commits over a period of time, but it can display any kind of information[^1] that follow the defined format.

Although gource is easy to use when called for a single repository, it can be a bit more complicated to create an animation for an organisation with multiple repositories.

This guide will show you how to create an organisation-wide gource animation, both an all-hands overview, and individual videos per contributor.

- ### 📄 [Getting Gource](01.getting.md)
  - [Installing Gource](01.getting.md#installing-gource)
    - [On Linux](01.getting.md#on-linux)
    - [On macOS](01.getting.md#on-macos)
    - [On Windows](01.getting.md#on-windows)
  - [Using Docker](01.getting.md#using-docker)
  - [Install from source](01.getting.md#install-from-source)

- ### Creating Logs
  - Preparations
    - 📄 [Cloning all repositories](02.logs.before.repos.md)
    - 📄 [Adding a `.mailmap` file](03.logs.before.mailmap.md)
      - [Creating a `.mailmap` file](03.logs.before.mailmap.md#creating-a-mailmap-file)
      - [Checking the `.mailmap` file](03.logs.before.mailmap.md#checking-the-mailmap-file)
      - [Using the `.mailmap` file](03.logs.before.mailmap.md#using-the-mailmap-file)
  - 📄 [Generating a Gource log file](04.logs.creating.md)
    - [Generating log files for all repositories](04.logs.creating.md#generating-log-files-for-all-repositories)
  - 📄 [Cleaning up the log files](05.logs.after.cleanup.md)
    - [Adding a common root](05.logs.after.cleanup.md#adding-a-common-root)
    - [Removing submodule / subtree](05.logs.after.cleanup.md#removing-submodule--subtree)
    - [Removing third-party code](05.logs.after.cleanup.md#removing-third-party-code)
    - [Dealing with deprecated repositories](05.logs.after.cleanup.md#dealing-with-deprecated-repositories)
  - 📄 [Combining the log files](06.logs.after.combine.md)

To keep things clearly arranged, the following directory structure is used:

```
project/
  ├── avatars/
  │   ├── ...
  │   └── default.png*
  ├── logs/
  │   ├── clean/
  │   ├── full/               <-- To be filled by gource
  │   ├── with-paths-ignored/
  │   ├── with-root/
  │   ├── combined.log
  │   ├── ignore-paths.txt
  │   └── ignore-vendors.txt
  ├── repos/
  │   ├── ...
  │   └── repository-name/
  ├── videos/           <-- To be filled by gource
  │   └── user/
  ├── captions.txt
  ├── deprecated-repos.txt
  ├── gource.config
  ├── logo.png
  └── .mailmap

* = or default.jpg
```

[^1]: Some examples form the [Custom Log Format page](https://github.com/acaudwell/Gource/wiki/Custom-Log-Format) are
Bugzilla, DocuWiki, JIRA, MediaWiki but there are also visualizations
of [the COVID19 Corona virus](https://github.com/sulmar/gource-covid19).
