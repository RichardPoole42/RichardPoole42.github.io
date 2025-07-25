---
layout: post
title: "Forgetfulness"
---

Today I've been back to looking at reconfiguring PGD5 clusters into
PGD6 ones. It's been frustrating, because so much of what I need to
know was in my head really quite recently but doesn't seem to come
back in very well when I want it. A key element of the
reconfiguration is reading the port settings that control pgd-proxy
and changing them to the correct settings for Connection Manager,
which replaces pgd-proxy. This isn't just about directly renaming:
they are in different sections of the configuration and they end
up stored in different places on the configured server. But I've
spend a lot of time today pulling some fairly simple mechanism back
into my head. In particular, there is the question of what configuration
ends up in files on each server - and hence can be overridden
per-server if the user wants to do that - and what ends up
in the replicated database, and hence is the same for all the
servers and can't be overridden. I think now that the read and write
ports are always in the database, in both PGD5 and PGD6, and the
http port used to be per-server information but is now global. So
when reconfiguring, I need to either refuse to reconfigure a cluster
which has a per-server override of the http port, or at least warn
the user that their configuration has been changed.

But understanding this seems to have taken most of my brain today.

Jonathan merged by PR for improving PGD-S configuration today, so
that is finally done. My other longstanding open PR was the one that
removed code related to the old repositories and that is also approved,
although it was found to be failing integration tests so it's had a
one-line fix to make it work. And at the end of the day I did a little
bit of rewriting of a release note for another PR - only two of us
on the core TPA team are native English speakers, so I sometimes get
asked to review or rewrite little things like that.
