---
layout: post
title:  "The ROLI Seaboard RISE 49"
date:   2016-5-12 00:13:00
tags: music midi
categories: notes
---

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Just setting up my <a href="https://twitter.com/WeAreROLI">@WeAreROLI</a> seaboard. <a href="https://t.co/TtKVHYgMDr">pic.twitter.com/TtKVHYgMDr</a></p>&mdash; kaushik (@ksrenev) <a href="https://twitter.com/ksrenev/status/728793038001053696">May 7, 2016</a></blockquote><script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

On a whim, I purchased a [ROLI](https://roli.com/) [Seaboard RISE](https://roli.com/products/seaboard-rise) last week. You can see it in
all its glory above. These are my brief notes - the answers to a bunch of questions
I was asked, when I told my friends about it, and some of my own
research to satisfy my curiosity about how multi dimensional MIDI
input works.

- The model I bought was the [Seaboard RISE 49](https://www.youtube.com/watch?v=cMdNDyW0dos). The RISE is a [MIDI](https://en.wikipedia.org/wiki/MIDI)
  controller that transmits MIDI over USB. (It does not have an
  in-built sound engine.) One key difference in the way it does that
  however is, that it transmits multiple channels of MIDI
  simultaneously. (See MPE below.)

- Setting it up involved what I thought was a rather elaborate setup
  process on the computer that included creating an account and
  registering the product before I was allowed to download [Equator](https://roli.com/products/seaboard-rise/software).

- I tried  both the wired (USB) and wireless (bluetooth) mode. While I
  didn't (and don't) care for the wireless mode, I didn't,
  comparatively speaking, observe an appreciable latency
  difference. In my experience the battery, on a full charge lasted
  for about nine hours.

- I haven't been able to get Equator to work outside a DAW at any
  sample rate other than 44.1 Khz. (I'm using a UAD Apollo interface.) The
  moment I set the sample rate to 96 Khz (which is normally the sample
  rate I use for all of my work) it starts buzzing. Equator works
  flawlessly within my DAW (Logic X) though.

- I haven't yet had the chance to hook it up to (say) Omnisphere or
  the like. Can't wait to play Trillian's acoustic bass using the
  Seaboard.


- MPE
  - MPE stands for [Multidimensional Polyphonic Expression](http://expressiveness.org/2015/04/24/midi-specifications-for-multidimensional-polyphonic-expression-mpe). It is a
    relatively new (what will, in the future be a) standard that is
    being worked on since late 2015 [^1].
  - It standardizes how MIDI controllers like the Seaboard, that are
    able to control multiple parameters of a note at the same time,
    talk to MPE compatible software.
  - MPE takes a backwards compatible approach by assigning every note
    its own channel, so as to be able to have fine grained control
    over the application of channel-wide messages such as modulation
    and pitch bend. It uses a range of channels, of which, the lowest
    is used for global messages while the remaining are used to
    transmit notes and expression data. On Equator these would be
    channel 1 for global messages and channels 2-16 for notes and
    expression data.

Here's a short piece I wrote and performed on the Seaboard, based on
the carnatic raga Senjurutti.

<iframe width="100%" height="166" scrolling="no" frameborder="no" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/264135591&amp;color=ff5500&amp;auto_play=false&amp;hide_related=false&amp;show_comments=true&amp;show_user=true&amp;show_reposts=false"></iframe>

[^1]: [https://docs.google.com/document/d/1-26r0pVtVBrZHM6VGA05hpF-ij5xT6aaXY9BfDzyTx8/edit?pref=2&pli=1](https://docs.google.com/document/d/1-26r0pVtVBrZHM6VGA05hpF-ij5xT6aaXY9BfDzyTx8/edit?pref=2&pli=1)
