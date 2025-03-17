---
layout: post
title: Computer History
description: Let's explore where computers came from, and how we got to the current stage in computing
date: 2025-03-13 15:01:35 +0300
image: '/images/dennis-ritchie-ken-thompson-bell-labs.jpg'
image_caption: 'Dennis Ritchie and Ken Thompson Bell Labs(dennis-ritchie-ken-thompson-bell-labs.jpg) Courtesy of [historyofinformation.com](https://www.historyofinformation.com/image.php?id=6430)'
tags: [History]
---

Modern computing traces itself to AT&T Bell Labs in NY / NJ, academic powerhouse MIT in Boston and the US Naval facilities in the Bay Area. Let's explore how these forces shaped our computers.

## Bell Labs Era

Bell Labs founded by a famous American inventor Alexander Graham Bell and his assistant Watson (himself an interesting character, and a name for a lot of later assistants). His wife and mother were deaf, and he spent a large amount of time thinking about speech and sound, and even worked to teach and integrate deaf people into society.  This passion led him to his work on telephone and telegraph.

Initial idea for the telephone evolved from the telegraph, and the hope of sending multi-tonal telegraph messages on a single line to cut costs. Eventually the idea became transmitting voice tones over the phone wire. 

Bell Telephone Company became a large corporation focused on telephony. On January 1st 1925 Bell Labs was created to consolidate all R&D activity for the company. Switching between various phone cables, and routing phone calls between various locales was the original driving factor for computing devices.

ATT took over American Bell, creating a large organization providing telephony services. To enable research and development, engineers were centralized in a single building originally in NYC, and later in NJ.

![Bell Labs in NJ](/images/BellLabs.jpg)

Early research of Bell Labs included:
- 1920s - Statistical Process Control - to use statistics to monitor manufacturing quality
  - This lead the way to another phone company establishing (Motorola) [6 sigma](https://en.wikipedia.org/wiki/Six_Sigma) for quality control
- 1947 - Transistor was invented at bell labs, and will serve as the basis for modern microchips
- 1948 - Mathematic theory of communication was invented, paving way for modern information theory
- 1954 - First computer based on transistors, installed on B-52 stratofortress and was used for bombing calculations
- 1954 - First solar cell (for solar batteries was invented)
- 1957 - MUSIC is the first program to create sound (music) via a digital computer
- 1958 - Technical paper on lasers (which later lead to the creation of the first laser at hughes labs). Laser of course is an acronym for light amplification by stimulated emission of radiation.
- 1960s - First digital movies were made at Bell Labs, via computer animation language called [BEFLIX](https://en.wikipedia.org/wiki/BEFLIX) (sounds a bit like a certain modern company)
- 1969 - Unix was created by Dennis Ritchie and Ken Thompson for telecommunication switching control, and general purpose computing. This operating system is at the heart of most of today's internet and Mac and Linux computers.
- 1970 - Tactile force feedback system is invited and coupled with a screen (a bit like a certain iPhone)
- 1972 - Dennis Ritchie develops a compiled C Programming language, whose descendants are still around today, and whose syntax expired Java, C# and Javascript amongst others
  - It's predecessor was B, which was interpreted. Funny enough B was the first lettered programming language (which aligns with the bible beginning with the letter B rather than A, but that's for another blog post)
- 1976 - Bourne Shell (sh) for unix
- 1985 - C++ was crated at bell labs to be a replacement for C, and is still used in many trading firms here in Chicago.

As you can see we owe most of our foundational computer science concepts (as well as cool laser stuff) to Bell Labs. Most of it happened on the east coast in cities like NY, Boston etc. So what happens once computers are more or less established? We will explore this after going over the personalities and universities that played a role in creation of modern computing, and how it migrated west.

## Going Weest => Personalities + Universities + Navy
There were a few major players in the computer space when it first took off, let's look at them one by one

### Dennis Ritchie and Ken Thompson and Unix
Unix is the core operating system of our time. It influences linux (built with GNU components), BSD any other popular non windows operating systems in use today. You can see the handy chart below:

![image](https://upload.wikimedia.org/wikipedia/commons/7/77/Unix_history-simple.svg)

They built it largely on their own time, and contributed many tools to the operating system. Really these two men paved the way for the modern computer software.


### MIT AI Lab and Richard Stallman
MIT AI Lab and Richard Stallman are intricately linked. Richard is a free software aficionado. He is the creator of GNU foundation (Gnu is Not Unix), and the FSF (free software foundation). 

MIT AI Lab today:

![MIT AI Lab](/images/MITAiLab.jpg)

Gnu name is said to have been inspired by the [Gnu Song](https://www.youtube.com/watch?v=OPgo6s1lBbw) below:

[![Gnu Song](https://img.youtube.com/vi/OPgo6s1lBbw/0.jpg)](https://www.youtube.com/watch?v=OPgo6s1lBbw)

His idea was to create a version of Unix built entirely on free software.

Contributions of the GNU Foundation were:
- 1987 - GCC or gnu compiler collection, originally used for C and C++, and now supports many different languages including RUST
- 1984 - `Gnu Emacs` - one of the most widely used code editors
- 1989 - `bash shell` - Bourne Again Shell, the most widely used terminal application on unix like operating systems
  - bash was a free alternative to the original Bourne Shell (sh), made by Brian Fox in FSF
  -  `Z-Shell` was also a derivative of bourne shell, named after professor Zhong Shao at Princeton

The tools of GNU being unencumbered by software licenses paved way for Linus Torvalds to develop Linux.

### Linux and Linux
Linux began as a personal project in 1991 by a Finish-Swede student Linux Torvalds at University of Helsinki.

His intro for the kernel was addressed to minix user group ([minix](https://en.wikipedia.org/wiki/Minix) was another unix like os developed in 1987 to run on Intel 8086 architecture):

```
Hello everybody out there using minix -

I'm doing a (free) operating system (just a hobby, won't be big and professional like gnu) for 386(486) AT clones. This has been brewing since april, and is starting to get ready. I'd like any feedback on things people like/dislike in minix, as my OS resembles it somewhat (same physical layout of the file-system (due to practical reasons) among other things).

I've currently ported bash(1.08) and gcc(1.40), and things seem to work. This implies that I'll get something practical within a few months, and I'd like to know what features most people would want. Any suggestions are welcome, but I won't promise I'll implement them :-)

Linus (torvalds@kruuna.helsinki.fi)

PS. Yes - it's free of any minix code, and it has a multi-threaded fs. It is NOT portable (uses 386 task switching etc), and it probably never will support anything other than AT-harddisks, as that's all I have :-(.

— Linus Torvalds[18]
```

He even included a helpful [audio file](https://upload.wikimedia.org/wikipedia/commons/transcoded/0/03/Linus-linux.ogg/Linus-linux.ogg.mp3) with the kernel source code on how to pronounce the name.

Linus ends up working at Transmeta which was working on a more energy efficient CPU, and ends up moving to the West Coast. But how did we get to California hosting chip manufacturing if all the innovation so far is driven by large east coast companies and universities?



### UC Berkeley + Navy = Western Computing Hub
UC Berkeley (named weirdly enough for an Irish priest [George Berkeley](https://en.wikipedia.org/wiki/George_Berkeley), considering the current attitudes of the university) is an interesting and really unnatural university to be so involved in the development of computers. As we saw before, most of computer science came from the east coast universities and research labs. So how did computers come to the west?

Unlike the East Coast, which was driven by large mega corporations like Bell Labs and old established universities like MIT, Bay Area, the bastion of entrepreneurship and disdain for the military ironically got into the computing game thanks to government investment in the military.

Founded as a land grant university by the Abraham Lincoln's [Morris Act](https://en.wikipedia.org/wiki/Morrill_Land-Grant_Acts), it initially focused on the farming sciences, which were the mainstay of the bay area economy. 

However, in the 20th century the navy had an air force base and many shipyards in the Bay Area, which was an ideal geographic location for a west coast military port.  The navy required a lot of mechanical and electronic devices. Berkeley got into that in the 1920s, and became more involved with the needs of the naval aviation.

Initially the navy needed a lot of radar and navigational equipment, which companies like Varian Associates were created to provide.

The navy was eventually kicked out for leaving a large pile of radioactive waste, but it's impact on making the Bay Area and Berkeley a center of computer science research remains.

Here is picture of major aircraft carrier servicing at hunters point in San Francisco:

![Hunters Point Shipyard](/images/HuntersPoint.jpeg)

There was also the naval station at Treasure Island

![Naval Station Treasure Island](/images/TreasuryIsland.jpg)

Since the 1930s, berkeley hosted facilities for nuclear research, Bay Area being really the middle of nowhere at the time, far from the war in Europe and close to testing facilities in pacific and Nevada, and therefore a perfect nuclear research location.

Earnest Lawrence established his lab at Berkeley at that time.  Robert Openheimer was a physics professor at Berkeley in the 1930s as well. This laid the groundwork for Berkeley's involvement in computers.

In the 1950s Bekeley worked with the office of naval research to create their first computer, called [CALDIC](https://en.wikipedia.org/wiki/CALDIC).

![CALDIC](/images/CALDIC.jpg)

In 1967 Doug Engelbart filed the patent for the computer mouse. He too was involved with the US navy, specifically their Ames research center in the bay area.

![Computer Mouse](/images/SRI_Computer_Mouse.jpg)

In 1966, Ken Thompson (of Bell Labs) graduated with a degree in CS from no other than university of California, Bekreley. He shipped a copy of Unix to UC Bekereley in the 70s, allowing the university to being playing and improving it.

In 1977 university of california in Berkeley began to develop their own version of Unix. Because Unix contained code to which ATT had a license, ATT filed a lawsuit against the university. This limited the development of BSD. 

This led to a period called the Unix wars, where ATT tried to cement control over unix, making life difficult for the open source community. This period led to the creation of Open Software Foundation.

The research at Berkeley was focused on improving the ATT Unix, and was funded by DARPA, which will be focus of another article.

The fact that California was so far away from DC and East Coast, but had such a good tie in with the military gave it a huge boost in development of software in later stages. They could take, modify and play with software far far away from places where big corporations could sue them left and right.

Once the reputation was established, many young engineering minds went to the west coast. Famous Berkeley grads include:

- Intel's Paul Otellini and Andrew Grove
- Eric Schmidt
- Steve Wozniac

### Standford - Transistors and Silicon Valley
Standford is heavyweight university that was very involved in computer developemnt.  It strangely became a center of technology for the same reason that Bell Labs left New York City for NJ - remoteness and available space. It benefitted from being in the sparsely populated San Francisco Bay Area and an ideal location for naval aviation research at Moffett Field.

Standford success lends itself to 3 distinct individuals:
- 1970s - Niels J. Reimers, director of Office of Technology Licensing at Standford, who paved the way to monetizing inventions that were coming out of Standford's research labs.
  - His vision began with some work in biotech by Boyer (Berkeley) and Cohen (Stanford) on Recombinant DNA technology, which Reimers thought he could turn into huge profit.
- Leland Standford - the founder of the university, and the person who imbued it with the mission of building out the west coast.
- Frederick Emmons Terman - provost who needed to save a financially struggling university (who was also involved in US navy)
  - Was trained at MIT, but did not like the ivory tower mentality
  - He introduced the founders of Varian Associates, one of the first high tech companies in the Bay Area, where David Packard and Clara Jobs (mom of Steve Jobs)

Under their leadership stanford made it easy to:
1. Take your invention to market (funding)
2. Have space for your company (cheap leases around standford as last was cheap and plentiful)
3. Have a network (Via the Office of Technology Licensing)

The key ingredients to what became Silicon Valley.

Many of standford's professors were originally from Cornell, and a lot of it's early development was based on that of Cornell. 

Most of Standford's early computer development however was focused on hardware rather than software with names like:
- Shockley Semiconductor
- Fairchild Semiconductor
- Hewlet Packard
- Sun Microsystems

Standford also benefitted from that Navy's presence in the region, specifically the Moffett Federal Airfield, where the naval aviation was experimenting with Blimps and therefore also radio, radar and other electrical equipment.

![Moffett Airfield](/images/MoffettAirfield.jpg)

Eventually the navy also contracted with it to become one of 4 nodes of it's arpanet, but that will be for a separate article.



### Sources
* https://en.wikipedia.org/wiki/Thomas_A._Watson
* https://en.wikipedia.org/wiki/Alexander_Graham_Bell
* https://en.wikipedia.org/wiki/Bell_Labs
* https://en.wikipedia.org/wiki/Statistical_process_control
* https://en.wikipedia.org/wiki/Six_Sigma
* https://en.wikipedia.org/wiki/Transistor
* https://en.wikipedia.org/wiki/Information_theory
* https://en.wikipedia.org/wiki/A_Mathematical_Theory_of_Communication
* https://en.wikipedia.org/wiki/TAT-1
* https://en.wikipedia.org/wiki/MUSIC-N
* https://en.wikipedia.org/wiki/Laser
* https://en.wikipedia.org/wiki/MOSFET
* https://en.wikipedia.org/wiki/BEFLIX
* https://en.wikipedia.org/wiki/C_(programming_language)
* https://en.wikipedia.org/wiki/B_(programming_language)
* https://en.wikipedia.org/wiki/Blit_(computer_terminal)
* https://en.wikipedia.org/wiki/TAT-8
* https://en.wikipedia.org/wiki/GNU_Compiler_Collection
* https://en.wikipedia.org/wiki/GNU#GNU_as_an_operating_system
* https://en.wikipedia.org/wiki/Z_shell
* https://en.wikipedia.org/wiki/Bourne_shell
* https://en.wikipedia.org/wiki/Bash_(Unix_shell)
* https://en.wikipedia.org/wiki/History_of_Linux
* https://en.wikipedia.org/wiki/Stanford_University
* https://en.wikipedia.org/wiki/Frederick_Terman
* https://web.archive.org/web/20160623234754/http://www.iphandbook.org/handbook/ch17/p13/