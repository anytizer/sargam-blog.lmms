![image](https://user-images.githubusercontent.com/5563341/212169242-115c7ad2-4ae9-4aed-99b7-e5f85fb06e4e.png)

Screenshot: Random melody filled in LMMS; under Bhuplai raag pattern.

# sargam-blog.lmms
A blog on how I achieved practically random SARGAM, (hence, the melody) generation for LMMS.

(plese notify me if something is wrong, or misleading in the below text).

## Random Melody
I spent several weeks in search of random melody to be created with [LMMS](https://lmms.io/).
For this, I came up with a new software that fills the notations.

Notes have to stay within a limited range as defined by their pattern rule called the [Raaga System](https://en.wikipedia.org/wiki/Raga),
which will automatically fall under one of the 10 parent scales called [thaat](https://en.wikipedia.org/wiki/Thaat).

You can find this database at various websites including Wikipedia, [Sharda.org](https://www.sharda.org/raga-taal/) and some other websites blogging musical notes.

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
* Random note generation
* Creating XPT file for LMMS
* Displays the SARGAM Notes and English Scales

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

[More on Bhupali](https://en.wikipedia.org/wiki/Bhoopali)

## Interface

![image](https://user-images.githubusercontent.com/5563341/212173212-d9da35c9-4f06-453a-828a-08ada9a0052d.png)

# Melody Structure
A user can self-define a melody combination. There are 10 different varieties of notation timing available.

![image](https://user-images.githubusercontent.com/5563341/212174928-c9c20afd-eacd-495f-8a97-1ce7ae26769f.png)

Each letter (from A to J) corresponds to one line of lyrics through out the melody.
You have to make a combination of these lines to create the structure for your melody.

For example, the [song structure](https://en.wikipedia.org/wiki/Song_structure) ABAACB would give:
```
 1: D     E     C     C     D     C     D,E   G     -     G     E     C     D     E     E     D,E  
 2: E     -     D,C   E,E   D     G     G     E     D     C     C     D,D   C     E     -     E    
 3: D     E     C     C     D     C     D,E   G     -     G     E     C     D     E     E     D,E  
 4: E     -     D,C   E,E   D     G     G     E     D     C     C     D,D   C     E     -     E    
 5: D     D     -     E     A     C*    A     -     C*    A     C*    C*    G     A     A     -    
 6: E     -     D,C   E,E   D     G     G     E     D     C     C     D,D   C     E     -     E    
 ```
 
 And it feels like as in this audio file - [listen](random.ogg) | [XPT File](random.xpt) for LMMS (import this file in piano roll editor).
