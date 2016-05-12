---
layout: post
title:  "Writing a multiboot PE kernel: part 2"
date:   2005-10-2 14:51:35
tags: programming kernel multiboot
categories: notes
---

Update [1/29/2012]: Source code now available [here](http://github.com/kaushiks/multibootpe).

Part I is [here]({% post_url 2005-10-1-multiboot1 %}).

While my earlier post explained the "how?", this will explain the "why?".

- The linker (link.exe) puts machine code of functions in the source text into the .text section in the order it finds them in the source.
- All PE headers never add up to a total size that exceeds 4K. So when file alignment is 4K (== memory alignment), the .text section is guaranteed to start at offset 4K (4096) in the PE file. This is a good place to put the multiboot header (which anyways needs to be present in its entirety within the first 8192 bytes.)
- The multiboot header forms the first 48 bytes of the .text section.
- declspec(naked) is an attribute that makes the compiler generate code without a prolog or an epilog. This is important because we want the multiboot header to start at offset 4096. Without the naked attribute, the function (and hence the .text section) would start with the bytes 55 8B EC which stand for the following instructions:
{% highlight nasm linenos %}
push ebp      ;; 55
mov  ebp, esp ;; 8B EC
{% endhighlight %}
which is the prolog. Because of this the multiboot header would be pushed to offset 4099 and Grub would refuse to load the kernel because the multiboot header isn't 4K longword aligned. [Updated: 10/6/2005, 12:23 PM].

Compiler switches:

- /Gd: forces the use of cdecl calling convention.
- /Fm: names the map file which might be useful when the kernel gets large.
- /Tc: compile the file as C source.
- /c: compile only, no link.

Linker switches:

- /safeseh:no: disables generating the symbols related to Safe SEH handlers (\_\_safe\_se\_handler\_table and \_\_safe\_se\_handler\_count.)
- /filealign:0x1000: this is an undocumented switch that aligns sections in the file based on this value. I've set it to 0x1000 (4K) so that sections are aligned on a 4K boundary on the image also (this is the default in-memory alignment). This is required because, Grub doesn't seem to load images whose file alignment is different from in-memory alignment.
- /base:0x100000: this makes the linker generate code assuming that the .text section starts at physical address 0x101000 and .data section at physical address 0x102000. This is what we want because Grub actually loads the image at 0x100000 which forces the .text and .data section into these addresses automatically and we need not relocate the kernel. (Now you probably understand why we set the file alignment to 4096 bytes as well).
- /entry:\_\_multiboot\_entry\_\_: sets the entry point.
- /nodefaultlib:libc: forces the linker to ignore libc while resolving external references. The idea is to be able to use names like memcpy etc in the kernel, and make sure the libc's functions don't get linked in.
- /subsystem:console: This sets a bit in one of the headers that tells windows which subsystem to use to execute this application. This doesn't make any sense here, but I included this to keep the linker happy.
- /out: kernel.exe: the name of the kernel.
