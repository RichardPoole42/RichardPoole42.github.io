---
layout: post
title: "Transmogrification"
---

Today I've worked on two fronts: first, I've made the almost final changes
to a PR I've had open for a while where we improve the process of
configuring a cluster using the PGD-S architecture, the simplest way
of using the latest version of PGD, by making it easy to specify either
of the approved layouts of your cluster. I've been going back and forth
on this PR for a while making tweaks but today's have been approved by
Jonathan so now all I need to do is rebase the PR, squash some commits
together, and ensure that it satisfies formalities like including release
notes, and then we will merge it.

Along with that, I'm working on the process of upgrading a cluster from
PGD5 to PGD6, using what TPA calls a "transmogrifier" - essentially, an
automated process of changing whatever needs to be changed in your
cluster configuration to achieve some defined overall change. PGD6
handles proxies differently from PGD5, so we need to make sure that if
you've had any non-default configuration, like which TCP port you want
your proxy to listen on, then we change it so that it has the same
effect in your upgraded cluster. This is partly done now - it can't
really be tested until more of the upgraded process is ready, so the
next thing is to get my code into a state where it can be reviewed,
then see where we are with the rest of the upgrade process.
