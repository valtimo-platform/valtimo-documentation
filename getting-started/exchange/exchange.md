# Exchange

The Exchange is an umbrella term to refer to  blueprints and building blocks, which can be used to speed up
development.

## Process blueprints

Process blueprints are generic processes that can be used to cover a certain type of scenario. For example, a process
that deals with City Pass applications. This is a process that in broad strokes is the same for a lot of municipalities.
Redeveloping such a process for every municipality would take a lot of time, so this process blueprint can be copied
and customized to fit the needs of that particular municipality. Information on how to use
process blueprints or how to contribute to the repository can be found [here](blueprints.md).

## Building blocks

Building blocks, unlike blueprints, are smaller in scope and do not contain a process. These can be code snippets or
other reusable parts that can be shared between different projects. For example, a plugin that allows sending messages
to Slack. This can then be used by an implementation to remind people on Slack there is an outstanding task. It can also
be used by another implementation to notify an administrator when an external API is unavailable. Information on how to
use building blocks or how to contribute to the repository can be found [here](building-blocks.md).