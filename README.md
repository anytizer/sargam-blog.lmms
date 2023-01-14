![image](https://user-images.githubusercontent.com/5563341/212216045-484fc7cd-9b6a-4c6f-a551-0525a70f02ec.png)

screenshot: Random melody filled in LMMS; under Bhupali raag pattern, with 4/4 time signature.

# sargam-blog.lmms

How I achieved practically random, though incomplete, SARGAM generation.

This page is also a bookmark to some articles in the same area.

Plese notify me if something is wrong, or misleading in the text below.
I won't accept pull requests in this project, but I will accept:
  - a [new issue](https://github.com/anytizer/sargam-blog.lmms/issues/new/choose),
  - a disucssion thread.

## Audience

* Someone who is interested in basics of classical music and raag database
* Someone who knows some programming language, like [C-Sharp](https://en.wikipedia.org/wiki/C_Sharp_(programming_language))
* Someone who knows [LMMS](https://lmms.io/) as open source music making software
* Someone interested in experimentation with [sound design](https://en.wikipedia.org/wiki/Sound_design)

## What is a melody?

It is a linear succession of musical tones percieved as single entity.

- [Wikiepdia](https://en.wikipedia.org/wiki/Melody)
- [hello music theory](https://hellomusictheory.com/learn/melody/)
- [@earmaster](https://www.earmaster.com/music-theory-online/ch02/chapter-2-3.html)
- [melody basic definitions](https://online.berklee.edu/takenote/conjunct-disjunct-melody-basic-definitions/)

I will try to create a sound piece as **melody**, with random notes permitted within a raag.

## Story of Random Melody

I spent several weeks in the year 2022 in re-search of random ambience melody to be created with [LMMS](https://lmms.io/).
Finally, I came up with a new tiny software that fills these notations.
Then immediately, it was possible to create an XML .xpt file that LMMS understands.
By this, an instant sound is possible and you can change instruments for different tonal qualities without altering the SARGAM notes generated.

The software is written in C# and uses [SQLite Database](https://sqlite.org/).
The source code will be available separately, shortly.

Other tools used are:
* C# with Visual Studio
* Entity Framework with support to SQLite
* [DB Browser for SQLite](https://sqlitebrowser.org/)

It consists of some major elements:
* Database of raag and thaat, eg. [as here](https://www.sharda.org/raga-taal/).
* Random SARGAM Generator
* [SWAR](https://en.wikipedia.org/wiki/Svara) Converter - convert SARGAM to English scales
* Ability to generate [.xpt](https://github.com/LMMS/lmms/pull/5891) pattern files for LMMS
* Song structure creator
* ~~Linking capabilities~~ to authorship roles: lyricists, musician, singer

## Raag and Thaat Database

Primarily, the notes have to stay within a limited range as defined by their melody pattern called the [Raaga System](https://en.wikipedia.org/wiki/Raga).
Any SARGAM is likely to automatically classify under one of the 10 parent scales called [Thaat](https://en.wikipedia.org/wiki/Thaat).
Today, a Thaat is fixed set of scales.
And raag is a combination of selected musical notes that fall under a Thaat.

You can find this database at various websites including:
 - [Wikipedia](https://en.wikipedia.org/wiki/List_of_ragas_in_Hindustani_classical_music)
 - [Sharda.org](https://www.sharda.org/raga-taal/)
 - [@p-sarkar](http://www.p-sarkar.com/Table%20of%20Indian%20Raags.htm)
 - [Raag Time](https://raagtime.com)
 - [Raaga-Time association](https://ayurveda-foryou.com/music/raga_time.html)
 - [Raag Index](http://www.tanarang.com/english/raagIndex_eng.htm)
 - [Tanarang](http://www.tanarang.com/english/raagIndex_eng.htm)
 - and some other websites blogging musical notes.

I had to combine information from various such links in order to identify how I should handle the notations for use with a computer.
Thus I ended up with a basic software that also reads a written pieces of notations.

## What is a SARGAM?

SARGAM is a short form created from the first basic musical notes - SA RE GA MA (PA DHA NI).
There are 12 notes including sharps and flats. C, C#, D, D#, E, F, F#, G, G#, A, A#, B.
Each English note corresponds to a variable SARGAM note.

Yes, SARGAM notes are variable.
You can assume any key on a piano as starting note - SA and keep on counting 12 notes from there.

## What is a SARAGM generation?

SARAGM generation is a picking up of those limited notes to create a melody; in a __written form__.
Not all the notes you pick in a sequence will be melodious.
There will be several factors around it like timing, tempo, and expectations of occurence of next note in the sequence.

## Terminologies

* Thaat - Parent Scale
* Raag - Melody Pattern
* Song structure - eg. ABAACB that is a structure of a song
* Note population
* Frequency
* Timing
* Notes skipping
* Tempo - How fast to play a melody
* Time Signature - eg. 4/4
* Beat
* Rhythm
* more from glossaries: [tanarang](http://www.tanarang.com/english/glossary_eng.htm), [wikipedia](https://en.wikipedia.org/wiki/Glossary_of_music_terminology)

## What is randomizing?

My randomization is based on the database of notations per Raag. It is an incomplete project though.
My limitation is to stay within pre-defined ascending and descending notes of a raag.
Luckily there is a database of Raags and their notations.

## What is a raag?

Technically, a raag could be a **named** combination of musical notes.
There is much more to [explore](https://en.wikipedia.org/wiki/Raga).
And, many of them are already been [lost permanently](https://www.indianclassicalmusic.com/what-is-raag).
They have unique [structures and evolution](https://eprints.soas.ac.uk/29748/1/10752720.pdf).

## Why Bhupali?

Bhupali is assumed to be over [4,000 years old](#) system.
It's melody pattern has been loved by many people in various generations and hence it thrived for so long.

It's ascending and descending notes are similar, as expected in reverse manner.
Data entry to this raag is easy, and the human ear can find out if something is not right.
Since the usage of major notes (no shaprs, no flats) it is a perfect pick up for the project.

[More on Bhupali](https://en.wikipedia.org/wiki/Bhoopali).

The basic notations used in Bhupali are:
SA, RE, GA, PA, DHA, SA* and returning as SA*, DHA, PA, GA, RE, SA.

Another reason I picked up this raag is due to relatively abundance of information available.
- [Influence on Human Brain Waves](https://ijettjournal.org/assets/year/2018/volume-61/IJETT-V61P221.pdf)
- [Music in motion](https://autrimncpa.wordpress.com/bhupali/)
- [Short Takes: Bhoopali](http://www.parrikar.org/hindustani/bhoopali/)
- [chandrakantha.com](https://chandrakantha.com/raga_raag/bhoopali/bhupali.html)
- [Meet Kalakar](https://meetkalakar.com/Artipedia/raga-bhoop)
- [Bansuri Bliss](https://bansuribliss.com/bhoopali/)

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
I found out some classical systems of writing these notes called [Bhatkhande](https://archive.org/search.php?query=bhatkhande) system and some other ways.
The purpose is to exactly reproduce the melody for ear by reading a written form of SARGAM.

I had another problem as well:
- the notes should have been understood by the computer.
- typing the notes should be easy using a QWERTY keyboard.
- notations should be convertible to the form understood by melody software.

I proudly happened to recreate the written notation system for use with **computer**; ultimately with slight modifications and limitations.

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

Notations from C2 octave would be:
* S.. R.. G.. M'.. P.. D.. N..
* r.. g.. M.. d.. n..

Notations from C6 octave would be:
* S** R** G** M'** P** D** N**
* r** g** M** d** n**

Number of dots or stars would decrease or increase the octave representation.
For example, C.. and C**. You can range from C-1 to G9 notes.

### Continuation

When the note extends to another time length, it will be represented with a hyphen in that time.
eg. `S - - - | S - S -`.

There are many other unicode characters that look like a hyphen. I tried include some of them.

### Time Sharing

When a beat shares a note's time with another note, sperate them with a comma.
eg. `S,R`. One comma means two notes together.
And two or more commas in a beat time is produces a glitch in the software.

The below notation is written as: `S - R,G P`.

![image](https://user-images.githubusercontent.com/5563341/212412538-9b44a60a-da7b-4d8b-ab24-eed6b516f21e.png)

Also,

* ~ and _ will be continuation markers
* x as silecne
* pipe | or a slash / as bar separator
* comma ( , ) would list notes that share the time equally.

There are some other glossaries that time-share a note.
[Meend](https://en.wikipedia.org/wiki/Meend) / [Glissando](https://en.wikipedia.org/wiki/Glissando), [Gamak](https://en.wikipedia.org/wiki/Gamaka_(music)), [Kan - Grace Note](https://en.wikipedia.org/wiki/Grace_note), Khitka, Aandolan, etc. [@realisim](https://github.com/realisim/Sargam)'s SARGAM seems to be better in this case.
I am currently unable to handle such [ornamentations](https://en.wikipedia.org/wiki/Ornament_(music)).

### Standard Markers

I noticed, many SARGAM authors use their own conventions.
And they are incompatible due to language selection, symbol selection.
They come in audio form, written/printed with pen or typed in computer, or in a digital image form, for example.

- [embedded in devanagari lipi](https://www.youtube.com/watch?v=XhQYPonLsX8)
- [typed in computer, in roman short forms](https://www.youtube.com/watch?v=nDkZ_vjgD-U)
- [in a diary, motion video](https://www.youtube.com/watch?v=2Tyk6wHqpxg)
- [photograph of a diary](https://youtu.be/xqlOL-EJeJU?t=699)
- [Live, as to show the key pressed](https://youtu.be/ojEordFqIdU?t=63)
- Oral explanations
- [PDF like display](https://www.sheetmusicdirect.com/se/ID_No/995947/Product.aspx)
- in websites
- in books
- scanned scripts from old prints

PS. these notations might have been copyrighted, registered, non-original or modified ones from the different scale.
I am concerned with the different mechanisms of their presentation only.

It would have been better, if there were one-language to write the notes and parse them in computer regardless of instrument being used.

## Software Limitations

* You have to save the note yourself if you need it to replay in the future.
* It re-generates a new set of note.
* Does not recognize the style of singing
* Does not prevent the history of how it was designed earlier.
* Usage in other beat making software has not been researched.

## Interface

![image](https://user-images.githubusercontent.com/5563341/212173212-d9da35c9-4f06-453a-828a-08ada9a0052d.png)

# Melody Structure

A user can self-define a melody structure of one's choice.
There are 10 different varieties of notations available.
Each difference is subject to change in notation's timing and frequency.
Everytime you generate a new notation, it will be random.

![image](https://user-images.githubusercontent.com/5563341/212174928-c9c20afd-eacd-495f-8a97-1ce7ae26769f.png)

Each letter (group_name from A to J) corresponds to one line of lyrics through out the melody.
A, B, C, D, E, F, G, H, I, J are the differnt parts of lyrics-line styles that you can repeat.

You have to make a combination of these lines to create the structure for your own melody.
To ease the user, I create a random lyrics per letter once while you generate your melody.
And, this lyrics is preseved in your work.

If you generate **ABABCB** song structure, then, there will be repeatitions of the notations.
The pattern A, pattern B and pattern C will be preseved.
If you are lucky enough to get more pleasing notation, you can recognize it through out rest of the the song.

For example, the [song structure](https://en.wikipedia.org/wiki/Song_structure) of ABABCB would give:

```
 1: D     E     C     C     D     C     D,E   G     -     G     E     C     D     E     E     D,E  
 2: E     -     D,C   E,E   D     G     G     E     D     C     C     D,D   C     E     -     E    
 3: D     E     C     C     D     C     D,E   G     -     G     E     C     D     E     E     D,E  
 4: E     -     D,C   E,E   D     G     G     E     D     C     C     D,D   C     E     -     E    
 5: D     D     -     E     A     C*    A     -     C*    A     C*    C*    G     A     A     -    
 6: E     -     D,C   E,E   D     G     G     E     D     C     C     D,D   C     E     -     E    
```

Notice how line #1 matches A, line 2 matches B, line 3 re-matches A, and so on.

[listen](random.ogg) to this corresponding audio. | Or, import the [.xpt File](random.xpt) in LMMS piano roll editor | [Download full project](random.mmpz)

## Other Possibilities

### Finding out raag name of an existing SARGAM

If you fill up SARGAM, it can give you the possible raags that matches it.

But there are **always** a multiple match due to:
* Some notes are skipped in your SARGAM.
* It really matches to many other raags.

When the notations match to many other raags, it is worth mentioning that a raag was also a way of singing it with various styles of stresses on the syllables.
Hence, officially, there are raags made of exactly similar set of notes, yet different names, presentation styles, different times for performance, and diffence to human ears, and serve different moods.

After all, a random melody to be created. Out of many thousands possible, here is one.

![image](https://user-images.githubusercontent.com/5563341/212273990-fa88ed52-0a6d-413b-8eb9-de897aa1ed83.png)

[Listen](https://freesound.org/s/669592/) or [download](random-improved.ogg), and view [.xpt midi clip](random.xpt).
Data for [Trance Pluck](https://lmms.io/lsp/?action=show&file=19838) instrument was random.

## Notices

* The pictures attached are for representation only.
* Randomization attempt does not supress creativity in note selection.
* This article was written by human hands, not AI generated.
* I do not have affilitions to the third party links.
* Everything in this project is an experiment.
* The included project should not match to existing melodies.