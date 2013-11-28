---
layout: site
title: Pond
---

# Pond

## [github.com/blackfisk/pond](github.com/blackfisk/pond)

Pond attempts to be an oversimpliflied wrapper on top of GPG allowing secure and metadata free communication between several peer.

You can see the [protocol specification](/pond/spec) which is only a simple
server broadcasting messages to ohter ponds.
Every message is an anonymous GPG message traveling in plain text. All the real
work is responsibility of the client that will be in charge of attempting to
decrypt each of the messages but only show the ones that are really for you.

![](/img/pond.jpg)
