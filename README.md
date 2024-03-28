# PortableIIMemBoard
Reverse engineering of the System Memory Board for the Compaq Portable II

[Interactive BOM](https://btb.github.io/PortableIIMemBoard/bom/ibom.html)

## About

I discovered the existence of this board from reading the 
[Maintenance and Service guide for the Portable II](https://minuszerodegrees.net/manuals/Compaq/Compaq%20Portable%20II%20-%20Maintenance%20and%20Service%20Guide.pdf). 

The Portable II has only two ISA slots to spare, and only one of those is 16-bit, so being able to expand the memory without using one up is a very attractive option.

But with web searches turning up no photos or any other info about the board, all I had to go on was this enticing image:

![manual_image](https://github.com/btb/PortableIIMemBoard/assets/149551/8caa59ac-5f61-4fac-9d43-a98e400a5695)

It shows that the board is almost entirely just memory chips, and only a small handful of other components, 
which implies all the heavy lifting is done on the motherboard itself, and this board might be simple enough 
that _even I_ could implement it. I started 
[a thread](https://forum.vcfed.org/index.php?threads/compaq-portable-ii-recreating-the-512-1536-kbyte-system-memory-board-104176-001.1247283/) 
on the Vintage Computer Federation forums, and mused 
about whether this board ever even existed.

By studying the motherboard, I located the various RAS and CAS lines for the onboard RAM banks, 
and the logic which controlled the transceivers that facilitated access to the data lines. 
Eventually I found the analogous lines going to the expansion connector, 
where there must necessarily be more or less the same transceivers and logic gates, and started my own schematic of the Memory Board itself.

I couldn't account for every signal on the connector though, and was somewhat stuck. Then HoJoPo replied to my thread that they had one of those boards, and sent [photos](photos/)! 

Using those photos, and HoJoPo's testing of certain connections, I was able to confirm most of the speculative schematic I'd been drawing, and get those logic gates to match precisely what was on the real board. 

Over on Youtube, Nick Silvestro had [a video](https://www.youtube.com/watch?v=IMVrAlZOAtU) about the reproduction of a similar memory expansion for the Portable III. I left a comment there, and they came over to help out as well, spotting some more differences and implementing a complete board layout and artwork that faithfully matches the original.

![render](https://github.com/btb/PortableIIMemBoard/assets/149551/e07547b9-84e4-47d6-9307-5962e177f68f)
