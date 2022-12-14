---
title: "Bugs & Known Issues"
permalink: /docs/known-issues/
last_modified_at: 2020-04-23T18:40:00+10:00
---

At present Berserk only provide a forum rather than a proper issue/bug tracker.

Forums are not a good solution for tracking bugs, as such the community is maintaining our own issue list that we hope is easier to navigate and keep up-to-date.

If you want to report a bug, rather than just document its existence, it's recommended that you open an issue in the community bug tracker (after ensuring the same issue doesn't already exist), then make a post in the relevant Berserk forum linking out to the issue in the community bug tracker.

## Community Maintained

| Content | Description |
| --- | --- |
| [Community Bug Tracker](https://github.com/tts-community/tts-community-bug-tracker/) | Community maintained Tabletop Simulator issues. |

## Official (Berserk Forums)

| Content | Description |
| --- | --- |
| [General Bugs](https://forums.tabletopsimulator.com/forumdisplay.php?36-Bug-Reports) | General Tabletop Simulator bugs. |
| [Scripting Bugs](https://forums.tabletopsimulator.com/forumdisplay.php?44-Scripting-Bug-Reports) | Scripting (Lua) bugs. |

# Workarounds

## Mod Development

> **My editor (Atom) can't upload scripts to the game**

*Details*

While TTS is running,
every TCP connection made to port 39999
should send a complete JSON payload.
If it matches any of the messages in the [External Editor API],
it will be accepted.
Any other message will be ignored.

Now it's easy to forget that there's another failure case
for incoming connections:
a timeout.
If a connection stays open for a long time,
its message may be outdated.
It appears TTS addresses this by
silently ignoring any messages that took over 3 seconds
to complete their JSON payload.

Things get weird when a connection
stays open for 3 seconds
without sending any packets.
In this case,
TTS **closes the TCP socket on port 39999**.
It is only reopened when
the lobby is reopened.

> Note: The timeouts may not be exactly 3 seconds. In my testing, messages sent within 2.5 seconds were always successful

[External Editor API]: https://api.tabletopsimulator.com/externaleditorapi/#tabletop-simulator-as-the-server
