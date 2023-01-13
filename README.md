![image](https://user-images.githubusercontent.com/5563341/212216045-484fc7cd-9b6a-4c6f-a551-0525a70f02ec.png)

Screenshot: Random melody filled in LMMS; under Bhupali raag pattern, with 4/4 time signature.

# sargam-blog.lmms

How I achieved practically random, though incomplete, SARGAM generation.

This page is also a bookmark to some articles in the same area.

```
Plese notify me if something is wrong, or misleading in the text below.
I won't accept pull requests in this project, but will accept:
  - a [new issue](https://github.com/anytizer/sargam-blog.lmms/issues/new/choose),
  - a disucssion thread.
```

## What is a melody?

It is a linear succession of musical tones percieved as single entity.

- [Wikiepdia](https://en.wikipedia.org/wiki/Melody)
- [hello music theory](https://hellomusictheory.com/learn/melody/)
- [@earmaster](https://www.earmaster.com/music-theory-online/ch02/chapter-2-3.html)
- [melody basic definitions](https://online.berklee.edu/takenote/conjunct-disjunct-melody-basic-definitions/)

I will try to create a sound piece as **melody**, with random notes permitted within a raag.

## Random Melody

I spent several weeks in the year 2022 in re-search of random melody to be created with [LMMS](https://lmms.io/).
Finally, I came up with a new software that fills the notations.
Then immediately, it was possible to create an XML that LMMS understands.
By this, an instant sound is possible and you can change instruments for different tonal qualities.

The software is written in C# and using [SQLite Database](https://sqlite.org/).
It consists of some major elements:
* Database of raag and thaat
* Random SARGAM Generator
* SWAR Converter - convert to English scales
* generate .xpt pattern files
* Song structure creator
* Linking capabilities to authorship roles: lyricists, musician, singer

## Raag and Thaat Database

Primarily, the notes have to stay within a limited range as defined by their melody pattern called the [Raaga System](https://en.wikipedia.org/wiki/Raga).
Any SARGAM is likely to automatically classify under one of the 10 parent scales called [Thaat](https://en.wikipedia.org/wiki/Thaat).
Today, a Thaat is fixed set of scales.
And raag is a combination of selected musical notes that fall under a Thaat.

You can find this database at various websites including:
 - [Wikipedia](https://en.wikipedia.org/wiki/List_of_ragas_in_Hindustani_classical_music)
 - [Sharda.org](https://www.sharda.org/raga-taal/)
 - [@p-parkar](http://www.p-sarkar.com/Table%20of%20Indian%20Raags.htm)
 - [Raag Time](https://raagtime.com)
 - [Raaga-Time association](https://ayurveda-foryou.com/music/raga_time.html)
 - [Raag Index](http://www.tanarang.com/english/raagIndex_eng.htm)
 - and some other websites blogging musical notes.

I had to combine information from various such links in order to identify how I should handle the notations for use with a computer.

My randomization is based on the database of notations per Raag.

## What is a SARGAM?

SARGAM is a short form created from the first basic musical notes - SA RE GA MA (PA DHA NI).
There are 12 notes including sharps and flats. C, C#, D, D#, E, F, F#, G, G#, A, A#, B.
Each English note corresponds to a variable SARGAM note.

Yes, SARGAM notes are variable.
You can assume any key on a piano as starting note - SA and keep on counting 12 notes.

## What is a SARAGM generation?

SARAGM generation is a random pick up of notes to create a melody.
My limitation is to stay within pre-defined ascending and descending notes of a raag.

## Terminologies

* Thaat - Parent Scale
* Raag - Melody Pattern
* Song structure - eg. ABAACB that is a structure of a song
* Note population - Time graph of a note length
* Frequency
* Timing
* Notes skipping
* Tempo - How fast to play a melody
* Time Signature - eg. 4/4
* Beat
* [more glossaries](http://www.tanarang.com/english/glossary_eng.htm)

## External Software involved

* .xpt (XML file) Generation
* LMMS's XPT note import function
* C# with Visual Studio
* Entity Framework with support to SQLite
* SQLite Database

## Software Capabilities

* SARGAM representation that a computer can parse well without confusion.
* Notations to sharps, flats and other octave changes are recognized.
* Can accept any keys from C-1 to G9 ie, 127 keys piano
* Randomly melodic note generation
* Creating XPT file for LMMS
* Conversion of the SARGAM Notes into English Scales
* Easy for another user to regenerate the same melody using a real piano

## Challenges in Notations Representation

There was a clear problem of how to write the SARGAM and the English scales that match to several keys of a piano.
I found out some classical systems of writing these notes called Bhatkhande system and some other ways.
The purpose is to exactly reproduce how the melody for ear was created.
So, there needed to be a system of writing these notes. I had another problem as well:
- the notes should have been understood by the computer.
- typing the notes should be easy using a QWERTY keyboard.

I proudly happened to recreate the written notation system ultimately with slight modifications.

### Basic notations

For example, notations from C4 octave would be:
* S R G M' P D N
* r g M d n

Notations from C5 octave would be:
* S* R* G* M'* P* D* N*
* r* g* M* d* n*

Notations from C3 octave would be:
* S. R. G. M'. P. D. N.
* r. g. M. d. n.

Number of dots or stars would decrease or increase the octave representation.
For example, C.. and C**. You can range from C-1 to G9 notes.

### Continuation

When the note extends to another timelength, it will be represented with a hyphen in that time bar.
eg. `S - - -`

There are many unicode characters that look like a hyphen. I tried to pickup some.

### Other markers

Many SARGAM authors use their own conventions.
I tried to bring them all together in one place.
Hence,

* ~ and _ will be continuation markers
* x as silecne
* pipe | or a slash / as bar separator

## Software Limitations

* You have to save the note yourself if you need it to replay in the future.
* It re-generates a new set of note.
* Does not recognize the style of singing
* Does not prevent the history of how it was designed earlier.

## What is a raag?
Technically, a raag could be a named combination of musical notes.
There is much more to [explore](https://en.wikipedia.org/wiki/Raga).
But, many of them are already been [lost permanently](https://www.indianclassicalmusic.com/what-is-raag).

## Why Bhupali?

Bhupali is assumed to be over 4,000 years old system.
It's melody pattern has been loved by many people and it thrived for so long.

It's ascending and descending notes are similar, as expected in reverse manner.
Data entry to this Raag is easy, and the human ear can find out if something is not right.
Since the usage of major notes (no shaprs, no flats) it is a perfect pick up for the project.

[More on Bhupali](https://en.wikipedia.org/wiki/Bhoopali).
The basic notations used in Bhupali are:
SA, RE, GA, PA, DHA, SA* and returning as SA*, DHA, PA, GA, RE, SA.

It is that simple.

## Interface

![image](https://user-images.githubusercontent.com/5563341/212173212-d9da35c9-4f06-453a-828a-08ada9a0052d.png)

# Melody Structure

A user can self-define a melody structure of one's choice.
There are 10 different varieties of notations available.
Each difference is subject to change in notation's timing and frequency.

![image](https://user-images.githubusercontent.com/5563341/212174928-c9c20afd-eacd-495f-8a97-1ce7ae26769f.png)

Each letter (group_name from A to J) corresponds to one line of lyrics through out the melody.
A, B, C, D, E, F, G, H, I, J are the differnt parts of lyrics line that you can repeat.

You have to make a combination of these lines to create the structure for your own melody.
To ease the user, I create a random lyrics per letter once while you generate your melody.
And, this lyrics is preseved in your work.

If you generate **ABABCB** song structure, then, there will be repeatitions of the notations.
The pattern A, pattern B and pattern C will be preseved.
If you are lucky enough to get more pleasing notation, you can recognize it through out rest of the the song.

For example, the [song structure](https://en.wikipedia.org/wiki/Song_structure) ABABCB would give:

```
 1: D     E     C     C     D     C     D,E   G     -     G     E     C     D     E     E     D,E  
 2: E     -     D,C   E,E   D     G     G     E     D     C     C     D,D   C     E     -     E    
 3: D     E     C     C     D     C     D,E   G     -     G     E     C     D     E     E     D,E  
 4: E     -     D,C   E,E   D     G     G     E     D     C     C     D,D   C     E     -     E    
 5: D     D     -     E     A     C*    A     -     C*    A     C*    C*    G     A     A     -    
 6: E     -     D,C   E,E   D     G     G     E     D     C     C     D,D   C     E     -     E    
```
 
And it feels like as in this audio file - [listen](random.ogg) | [XPT File](random.xpt) for LMMS (import this file in piano roll editor) | [Project File](random.mmpz)

## Other Possibilities

### Finding out raag name of an existing SARGAM

If you fill up SARGAM, it can give you the possible raags that matches it.
There are always a multiple match due to:
* Some notes are skipped in your SARGAM.
* It really matches to many other raags.

## Differentiation with other raags

Oh, when the notes match to many other raags, it is worth mentioning that a raag was also a way of singing it with various styles of stresses on the syllables.
Hence, officially, there are raags with exactly similar notes, yet different names, different times for performance, and diffence to human ears.
