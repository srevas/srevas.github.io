---
layout: post
title:  "Spectre and Meltdown"
date:   2018-01-06 20:15:00
tags: programming spectre meltdown intel amd arm
categories: notes
---

Here's a collection of articles I found to be the most informative out
of the mountain of literature that's been written since the attacks
were made public.

### Introduction
- [Why Raspberry Pi isn't vulnerable to Spectre or Meltdown](https://www.raspberrypi.org/blog/why-raspberry-pi-isnt-vulnerable-to-spectre-or-meltdown/)
- [Notes from the Intelpocalypse](https://lwn.net/Articles/742702/)
- [News and updates from the Project Zero team at Google](https://googleprojectzero.blogspot.com/)

### Spectre
- [Spectre Attacks: Exploiting Speculative Execution](https://spectreattack.com/spectre.pdf)
- [CVE-2017-5753](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5753) <br />
  Systems with microprocessors utilizing speculative execution and branch prediction may allow unauthorized disclosure of information to an attacker with local user access via a side-channel analysis.
- [CVE-2017-5715](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5715) <br />
  Systems with microprocessors utilizing speculative execution and indirect branch prediction may allow unauthorized disclosure of information to an attacker with local user access via a side-channel analysis.

### Meltdown
- [Meltdown](https://meltdownattack.com/meltdown.pdf)
- [CVE-2017-5754](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5754)<br />
  Systems with microprocessors utilizing speculative execution and indirect branch prediction may allow unauthorized disclosure of information to an attacker with local user access via a side-channel analysis of the data cache.

### Vendor material
- Apple: [About speculative execution vulnerabilities in ARM-based and Intel CPUs](https://support.apple.com/en-us/HT208394)
- ARM: [Arm Processor Security Update](https://developer.arm.com/support/security-update)
- Chromium: [CPU security bug: information leak using speculative execution](https://bugs.chromium.org/p/project-zero/issues/attachmentText?aid=287305)
- Firefox: [Speculative execution side-channel attack ("Spectre")](https://www.mozilla.org/en-US/security/advisories/mfsa2018-01/)
- Google
  - [Information for Google Cloud Customers on CPU Vulnerabilities](https://cloud.google.com/security/cpu-vulnerabilities/)
  - [Retpoline: a software construct for preventing branch-target-injection](https://support.google.com/faqs/answer/7625886)
  - [An implementation of retpolines in the LLVM x86 backend](https://reviews.llvm.org/D41723)
- Intel: [Intel Analysis of Speculative Execution Side Channels](https://newsroom.intel.com/wp-content/uploads/sites/11/2018/01/Intel-Analysis-of-Speculative-Execution-Side-Channels.pdf)
- Microsoft: [Understanding the performance impact of Spectre and Meltdown mitigations on Windows Systems](https://cloudblogs.microsoft.com/microsoftsecure/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/)
- Webkit: [What Spectre and Meltdown Mean For WebKit](https://webkit.org/blog/8048/what-spectre-and-meltdown-mean-for-webkit/)

### Prior research
- [Cache missing for fun and profit](http://www.daemonology.net/papers/htt.pdf)
- [Cache-timing attacks on AES](http://cr.yp.to/antiforgery/cachetiming-20050414.pdf)
- [FLUSH+RELOAD: A High Resolution, Low Noise, L3 Cache Side-Channel Attack](https://www.usenix.org/node/184416)
- [CacheBleed A Timing Attack on OpenSSL Constant Time RSA](https://www.youtube.com/watch?v=Fjz4dkU2N3g)