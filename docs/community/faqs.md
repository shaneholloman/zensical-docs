---
icon: lucide/message-circle-question-mark
---

# Frequently asked questions

!!! tip "Question not answered...?"

    We would like to thank all users who have got in touch with us and shared
    the questions they have about Zensical and about moving from Material for
    MkDocs to Zensical. If you find that you have questions that should be
    covered here, feel free to reach out to us at
    [hello@zensical.org](mailto:hello@zensical.org) or post the question on
    the [quick-thoughts] channel on Discord.

## Compatibility and transition

### Can I use Zensical in production since it is a 0.0.x release?

The versioning is primarily technical – Zensical is ready for production use,
and we continue to improve it carefully.

We're still making significant changes to Zensical's API, which is why 0.0.x
versioning is the correct choice. While the code changes a lot, we keep
user-facing changes to a minimum, so we will not break your configuration or use
of the CLI. There's currently no ETA for a 1.0.0 release.

### Will Zensical support plugins?

Zensical provides native implementations of the MkDocs plugins listed in the
[plugin support] guide. Most are built in and recognize the original plugin
configuration; integrations that require the original package include
installation instructions. A public API for native Zensical modules is planned
separately and is not required to use these compatibility implementations.

### Why do you call them "modules" and not "plugins"?

We use "plugin" for MkDocs plugins and the compatibility implementations that
recognize their configuration. "Module" refers to Zensical's future native
extension model. That public module API is not available yet, so compatibility
support should not be read as a promise that an MkDocs plugin can run as a
native Zensical module.

### How long will you support Material for MkDocs?

See [Zensical today] for the current Material for MkDocs maintenance timeline.
The [compatibility overview] explains how to assess a project before migrating.

### How long will the "classic" theme variant be supported?

We are committed to supporting both variants for the time being. That is, we will
fix bugs but our development effort will go into the "modern" variant. Pull
requests that improve the variant without introducing breaking changes are, of
course, welcome.

At the same time, our work on a [component system] will make it easier to
author variants of the Zensical theme. This will make it easier for you to build
new theme variants and use them for your projects or share them with the
community.

## Zensical Spark, business model, and licensing

### Do I need to pay for extra features in Zensical?

No, the Zensical SSG is Free and Open Source Software - and "free" here can be
read as "free beer" and "freedom". You can use our software to build unlimited
sites of unlimited complexity, with unlimited teams, and unlimited numbers of
users. There is no Insiders program like Material for MkDocs had that ties the
release of features to funding goals, nor is there an open core model.

### Does Zensical Spark mean Zensical is not Open Source?

All software we publish is Open Source.[^infra] Zensical Spark is an optional
offering for organizations to get direct support and training as well as to take
part in the early phases of our design process to make sure all requirements are
met.

Zensical Spark allows us to sustain the pace of development of Zensical, which
benefits the whole community. Everyone can engage with the project, view bug
reports and change requests, just as in many other Open Source projects. We also
maintain a public [roadmap] and [backlog], which is something few Open Source
projects of comparable size manage to do. In addition, there is lively,
community-driven Discord server created for all Zensical users, where you can
seek help and participate in discussions.

[^infra]: This does not include code we use only internally, e.g., to manage infrastructure.

[backlog]: https://github.com/orgs/zensical/projects/2/views/1
[component system]: https://zensical.org/about/roadmap/#component-system
[compatibility overview]: ../compatibility/mkdocs/index.md
[plugin support]: ../compatibility/mkdocs/plugins.md
[quick-thoughts]: https://discord.com/channels/1289187620659789824/1435275497549598770
[roadmap]: https://zensical.org/about/roadmap/
[Zensical today]: https://zensical.org/about/zensical-today/
