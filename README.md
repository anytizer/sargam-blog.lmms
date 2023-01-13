![image](https://user-images.githubusercontent.com/5563341/212216045-484fc7cd-9b6a-4c6f-a551-0525a70f02ec.png)

Screenshot: Random melody filled in LMMS; under Bhuplai raag pattern, with 4/4 time signature.

# sargam-blog.lmms
A blog on how I achieved practically random SARGAM (hence, the melody) generation for LMMS.

(Plese notify me if something is wrong, or misleading in the text below).

## Random Melody
I spent several weeks in search of random melody to be created with [LMMS](https://lmms.io/).
For this, I came up with a new software that fills the notations. It is written in C# and using [SQLite Database](https://sqlite.org/).

Notes have to stay within a limited range as defined by their pattern rule called the [Raaga System](https://en.wikipedia.org/wiki/Raga),
which will automatically fall under one of the 10 parent scales called [thaat](https://en.wikipedia.org/wiki/Thaat).

You can find this database at various websites including [Wikipedia](https://en.wikipedia.org/wiki/List_of_ragas_in_Hindustani_classical_music), [Sharda.org](https://www.sharda.org/raga-taal/) and some other websites blogging musical notes. I had to combine information from various such links in order to indentify how I should handle the notations for use with Computer.

There are several classical raags possible and they were "named" in the past. Many of them might have been lost over the time.
Bhupali is assumed to be over 4,000 years old system. My randomization is based on the database of notations.

## What is a SARGAM?
SARGAM is a short form created from the first basic musical notes - SA RE GA MA (PA DHA NI).
There are 12 notes. C, C#, D, D#, E, F, F#, G, G#, A, A#, B. Each English note corresponds to a variable SARGAM note. Yes, SARGAM notes are variable.

You can assume any key on a piano as starting note - SA and continue by counting until another octave.

## What is a SARAGM generation?
SARAGM generation is a random pick up of notes to create a melody.
My limitation is to stay within pre-defined ascending and descending notes of a raag.
In this case, the Bhupali notations only.

## Terminologies
* Thaat - Parent Scale
* Raag - Melody Pattern
* Song pattern - eg. ABAACB that is a structure of a song
* Note population - Time graph of a note length
* Frequency
* Timing
* Notes skipping
* Tempo - How fast to play a melody

## External Software involved
* LMMS's XPT note import function
* XPT XML Generation
* C# with Visual Studio

## Software capabilities
* SARGAM representation that a computer can parse well without confusion.
* Notations to sharps, flats and other octave changes are recognized.
* Can accept any keys from C-1 to G9 ie, 127 keys piano
* Randomly melodic note generation
* Creating XPT file for LMMS
* Conversion of the SARGAM Notes and English Scales
* Easy for another user to regenerate the same melody usng piano

## Software limitations
* You have to save the note yourself if you need it to replay in the future.
* It re-generates a new set of note.
* Does not recognize the style of singing
* Does not prevent the history of how it was designed earier.

## Why Bhupali?
It is a  melody pattern with the major pentatoic notes.
It's ascending and descending notes are similar, as expected in reverse manner.
Data entry to this Raag is easy, and the human ear can find out if something is not right.
Since the usage of major notes (no shaprs, no flats) it is a perfect pick up for the project.

[More on Bhupali](https://en.wikipedia.org/wiki/Bhoopali). The basic notations used in Bhupali are:
SA, RE, GA, PA, DHA, SA*

## Interface

![image](https://user-images.githubusercontent.com/5563341/212173212-d9da35c9-4f06-453a-828a-08ada9a0052d.png)

# Melody Structure
A user can self-define a melody combination.
There are 10 different varieties of notations available.

![image](https://user-images.githubusercontent.com/5563341/212174928-c9c20afd-eacd-495f-8a97-1ce7ae26769f.png)

Each letter (from A to J) corresponds to one line of lyrics through out the melody.
You have to make a combination of these lines to create the structure for your own melody.
To ease the user, I create a random lyrics per letter once while you generate your melody.
And, this lyrics is preseved in your work.

If you generate ABAACB song structure there, will be repeatetions of the notations.
Hence, if you were lucky to get more pleasing notation, you can recognize it through out rest of the the song.

For example, the [song structure](https://en.wikipedia.org/wiki/Song_structure) ABAACB would give:
```
 1: D     E     C     C     D     C     D,E   G     -     G     E     C     D     E     E     D,E  
 2: E     -     D,C   E,E   D     G     G     E     D     C     C     D,D   C     E     -     E    
 3: D     E     C     C     D     C     D,E   G     -     G     E     C     D     E     E     D,E  
 4: E     -     D,C   E,E   D     G     G     E     D     C     C     D,D   C     E     -     E    
 5: D     D     -     E     A     C*    A     -     C*    A     C*    C*    G     A     A     -    
 6: E     -     D,C   E,E   D     G     G     E     D     C     C     D,D   C     E     -     E    
 ```
 
And it feels like as in this audio file - [listen](random.ogg) | [XPT File](random.xpt) for LMMS (import this file in piano roll editor) | [Project File](random.mmpz)

## Other possibilities

### Finding out raag name of an existing SARGAM
If you fill up SARGAM, it can give you the possible raags that matches it. There are always a multiple match due to:
* Some notes are skipped in your SARGAM.
* It really matches to many other raags.

## Differentiation with other raags
Oh, when the notes match to many other raags, it is worth mentioning that a raag was also a way of singing it with various styles of stresses on the syllables.
Hence, officially, there are raags with exactly similar notes, yet different names, different times for performance, and diffence to human ears.
