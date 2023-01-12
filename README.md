![image](https://user-images.githubusercontent.com/5563341/212169242-115c7ad2-4ae9-4aed-99b7-e5f85fb06e4e.png)

Screenshot: Random melody filled in LMMS; under Bhuplai pattern.

# sargam-blog.lmms
A blog on how I achieved random sargam (hence, the melody) generation

(plese notify me if something is wrong, or misleading in the below text).

## Random Melody
I spent several weeks in search of random melody to be created with [LMMS](https://lmms.io/).
For this, I came up with a new software that fills the notations.

Notes have to stay within a limited range as defined by their pattern rule called the [Raaga System](https://en.wikipedia.org/wiki/Raga).

## What is a SARGAM?
SARGAM is a short form created from the first basic musical notes - SA RE GA MA (PA DHA NI).
There are 12 notes. C, C#, D, D#, E, F, F#, G, G#, A, A#, B.

## What is a SARAGM generation?
Sargam generation is a ranom pick up of notes to create a melody.

Each English note corresponds to a sargam note.

Sargam notes are variable. You can assume any key on a piano as starting note - SA and continue by counting.

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

## Why Bhupali?
It is a simple melody pattern with the major pentatoic notes. It's ascending and descending notes are similar.
Data entry to this Raag is easy, and the human ear can find out if something is not right.
Since the usage of major notes (no shaprs, no flats) it is a perfect pick up for the project.
