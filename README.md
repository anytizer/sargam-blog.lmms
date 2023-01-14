![image](https://user-images.githubusercontent.com/5563341/212216045-484fc7cd-9b6a-4c6f-a551-0525a70f02ec.png)

screenshot: Randomly filled melody in LMMS; under Bhupali raag pattern, with 4/4 time signature.

# sargam-blog.lmms

How I experiemented and achieved practically random, though incomplete, SARGAM generation.

This page is also a bookmark to some useful articles in the same area.

Plese notify me if something is wrong, or misleading in the text below.
I won't accept pull requests in this project, but I will accept:
  - a [new issue](https://github.com/anytizer/sargam-blog.lmms/issues/new/choose),
  - a disucssion thread.

## Audience

Dedicated to experiement lovers.

* Someone who is interested in basics of classical music and raag database
* Someone who knows some programming language, like [C-Sharp](https://en.wikipedia.org/wiki/C_Sharp_(programming_language))
* Someone who knows [LMMS](https://lmms.io/) as open source music making software
* Someone who is interested in __experimentation__ with [sound design](https://en.wikipedia.org/wiki/Sound_design)

## What is a melody?

It is a linear succession of musical tones percieved as single entity.
I will try to create a sound piece as melody, by taking random notes permitted within a raag.

- [Wikiepdia](https://en.wikipedia.org/wiki/Melody)
- [hello music theory](https://hellomusictheory.com/learn/melody/)
- [@earmaster](https://www.earmaster.com/music-theory-online/ch02/chapter-2-3.html)
- [melody basic definitions](https://online.berklee.edu/takenote/conjunct-disjunct-melody-basic-definitions/)

## Story of Random Melody

I spent several weeks in the year 2022 in re-search of random ambient melody to be created with [LMMS](https://lmms.io/).
I came up with a new tiny software that fills these notations as defined in the classical way.
Then immediately, it was possible to create an XML .xpt file that LMMS understands.
It is the capability of LMMS to export and import notations in XML format, so that portion of MIDI Clips can be shared within projects.

By this, an instant sound is possible and you can change instruments and tempo, beats and effects for different tonal qualities, without altering the SARGAM notes.
Change of digital instrument would render entirely different sound experience, and mood to the listener.

The software is written in C# and uses [SQLite Database](https://sqlite.org/).
The source code will be available separately, shortly.

Other tools used are:

* Visual Studio with .net 7 (as of this writing)
* Entity Framework with support to SQLite
* [DB Browser for SQLite](https://sqlitebrowser.org/)

It consists of some major elements:

* Database of raag and thaat, eg. [as in here](https://www.sharda.org/raga-taal/).
* Random SARGAM Generator
* [SWAR](https://en.wikipedia.org/wiki/Svara) Converter - convert SARGAM to English scales
* Ability to generate [.xpt](https://github.com/LMMS/lmms/pull/5891) pattern files for LMMS
* Song structure creator
* ~~Linking capabilities~~ to authorship roles: lyricists, musician, singer, composers and directors.

## Raag and Thaat Database

Primarily, the notes have to stay within a limited range as defined by their melody pattern called the [Raaga](https://en.wikipedia.org/wiki/Raga).
Any SARGAM is likely to automatically classify under one of the 10 [Thaats](https://en.wikipedia.org/wiki/Thaat).

You can find this database at various websites including:
 - [Wikipedia](https://en.wikipedia.org/wiki/List_of_ragas_in_Hindustani_classical_music)
 - [Sharda.org](https://www.sharda.org/raga-taal/)
 - [@p-sarkar](http://www.p-sarkar.com/Table%20of%20Indian%20Raags.htm)
 - [Raag Time](https://raagtime.com)
 - [Raaga-Time association](https://ayurveda-foryou.com/music/raga_time.html)
 - [Raag Index - Tanarang](http://www.tanarang.com/english/raagIndex_eng.htm)
 - etc.

I had to combine information from various such links in order to identify how I should handle the notations for use with a computer.
Thus I ended up with a basic software that also **parses** a written piece of notations.

## What is a SARGAM?

SARGAM is a short form created from the first basic musical notes - SA RE GA MA (PA DHA NI).
There are 12 notes including sharps and flats. C, C#, D, D#, E, F, F#, G, G#, A, A#, B.
Each English note corresponds to a variable SARGAM note.

Yes, SARGAM notes are variable.
You can assume any key on a piano as starting note - SA and keep on counting 12 notes from there.

## What is a SARAGM generation?

SARAGM generation is a picking up of those notes to create a melody; in a __written form__.
Another person or software should be able to recreate the similar sound as intended by the original author.

There will be factors around a melody, like: timing, tempo, and expectations of occurence of next note in the sequence.

The different note sequences has been already documented in the classical music.

## Terminologies

* Thaat - Parent Scale
* Raag - Melody Pattern
* Song structure - eg. ABAACB that is a structure of a song
* Note population - what note to pick next is based on note population
* ~~Frequency~~ - how frequently should a note occur is not addressed
* Time length
* Notes skipping
* Tempo - How fast to play a melody
* Time Signature - eg. 4/4, 2/2, 3/4
* Beat
* Rhythm
* more from glossaries: [tanarang](http://www.tanarang.com/english/glossary_eng.htm), [wikipedia](https://en.wikipedia.org/wiki/Glossary_of_music_terminology)

## What is randomizing?

The core of the project is to create a randomized sound as melody.
Luckily the database of notes and Raags have been already documented since the old times.
I will generate sound based on [these rules](https://www.swarganga.org/articles/icmconcepts/icm13.php), and the database.

My randomization is based on the database of notations per Raag.
It is an incomplete project because I cannot address the all factors.

The randomization should create new and unfamiliar melody, yet, hoping pleasant to hear.

## What is a raag?

Technically, a raag could be a **named** combination of musical notes.
It could be a [permutation](https://www.berklee.edu/berklee-today/summer-2009/the-woodshed/power-of-permutation) of allowed notes.
There is much more to [explore](https://en.wikipedia.org/wiki/Raga).
And, many of them are already been [lost permanently](https://www.indianclassicalmusic.com/what-is-raag).
They should have unique [structures, evolved](https://eprints.soas.ac.uk/29748/1/10752720.pdf) and popularized over differnt anceint times.

Another reading on [permutaion]https://en.wikipedia.org/wiki/Permutation_(music))

## Why Bhupali?

[Raag Bhupali](https://en.wikipedia.org/wiki/Bhoopali). is assumed to be over [4,000 years old](https://drvidyahattangadi.com/serene-raga-bhupali/) system.
It's melody pattern has been loved by so many people in various generations and hence it thrived for so long.

It's ascending and descending notes are expectedly inverted.
Data entry to this raag is easy, and the human ear can find out if something is not right.
Since the usage of only major pentatonic notes (no shaprs, no flats) it is a perfect pick up for my project.

Another reason I picked up this raag is due to relatively abundance of information available.
- [Influence on human brain waves](https://ijettjournal.org/assets/year/2018/volume-61/IJETT-V61P221.pdf)
- [Music in motion](https://autrimncpa.wordpress.com/bhupali/)
- [Short Takes: Bhoopali](http://www.parrikar.org/hindustani/bhoopali/)
- [chandrakantha.com](https://chandrakantha.com/raga_raag/bhoopali/bhupali.html)
- [Meet Kalakar](https://meetkalakar.com/Artipedia/raga-bhoop)
- [Bansuri Bliss](https://bansuribliss.com/bhoopali/)

Many people know the Bhupali already in some forms.
So, it will be easier to collect feedbacks on the sound produced.

The basic notations used in Bhupali are:
SA, RE, GA, PA, DHA, SA* and returning as SA*, DHA, PA, GA, RE, SA.

## Challenges in Notations Representation

x | C | C# | D | D# | E | F | F# | G | G# | A | A# | B
-- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | --
C1 Octave Notes | S... | r... | R... | g... | G... | m... | M'... | P... | d... | D... | n... | N...
C2 Octave Notes | S.. | r.. | R.. | g.. | G.. | m.. | M'.. | P.. | d.. | D.. | n.. | N..
C3 Octave Notes | S. | r. | R. | g. | G. | m. | M'. | P. | d. | D. | n. | N.
**C4 Octave Notes** | S  | r | R | g | G | m | M | P | d | D | n | N
C5 Octave Notes | S* | r* | R* | g* | G* | m* | M'* | P* | d* | D* | n* | N*
C6 Octave Notes | S** | r** | R** | g** | G** | m** | M'** | P** | d** | D** | n** | N**
C7 Octave Notes | S*** | r*** | R*** | g*** | G*** | m*** | M'*** | P*** | d*** | D*** | n*** | N***
C8 Octave Notes | S**** | r**** | R**** | g**** | G**** | m**** | M'**** | P**** | d**** | D**** | n**** | N****

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

Number of dots or stars would decrease or increase the octave number from C4.
For example, `S.` and `S**`. You can range from C-1 to G9 key notes.
For example: `S....`

### Continuation

When the note extends to another time length, it will be represented with a hyphen in that time.
eg. `S - - - | S - S -`, and `S* - - -`.

There are many other unicode characters that look like a hyphen. I tried to include some of them.

### Time Sharing

When a beat uses two or more notes, sperate them with a comma. eg. `S,R`.
One comma means two notes together.
And two or more commas in a beat might produce a digital glitch or crackling sound in the software (quantization error).

Three commas would be too quick notes served in 1 beat.
But, it opened a new opportunity of notation like: `R,-,-,G` and `R,G,-,-` which are differently stressed sylables.
You can probably adjust the grace notes / meend here.
Unfortunately `R,-,-,-` is same as `R` but with CPU loads.

The below notation is written as: `S - R,G P`.
Combination R and G share same time length as S, -, and P.

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

I noticed, many SARGAM authors use their own conventions to write and educate.
And they are incompatible due to their choice of format selection and presention styles.
They come in audio form, written/printed with pen or typed in computer, or in a digital image form, for example.

- [embedded in devanagari lipi](https://www.youtube.com/watch?v=XhQYPonLsX8) and [this](https://www.youtube.com/watch?v=HwYojO7ykZ4)
- [typed in computer, in roman short forms](https://www.youtube.com/watch?v=nDkZ_vjgD-U)
- [in a diary, motion video](https://www.youtube.com/watch?v=2Tyk6wHqpxg)
- [photograph of a diary](https://youtu.be/xqlOL-EJeJU?t=699)
- [Live, as to show the key pressed](https://youtu.be/ojEordFqIdU?t=63)
- Oral explanations
- [PDF like display](https://www.sheetmusicdirect.com/se/ID_No/995947/Product.aspx)
- in interactive websites and animations
- in books
- in verbal trainings and recitements
- scanned pages from old scripts / print outs
- staff notations

Note: these notations might have been copyrighted, registered, non-original or modified ones from the different scale.
I am concerned with the different mechanisms of their presentation only.

It would have been better, if there were one-language to write these notes and parse them in computer regardless of instrument being used.
I am not talking about staff notes but SARGAM in written form.

## Software Capabilities

* SARGAM representation that a computer can parse well without confusion.
* Notations to sharps, flats and other octave changes are recognized.
* Can accept any keys from C-1 to G9 ie, 127 keys piano
* Randomly melodic note generation
* Creating XPT file for LMMS
* Conversion of the SARGAM Notes into English Scales
* Easy for another user to regenerate the same melody using a real piano

## Software Limitations

* You have to save the note yourself if you need it to replay in the future.
* It re-generates a new set of notes.
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

![image](https://user-images.githubusercontent.com/5563341/212450263-a5720fc3-1b40-420b-a1cf-6a0ad26797e1.png)

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

## Explaining the partial source code

Check the code below to determine how the randomization has been implemented.

```
int[] steps = new int[] { -3, -2, -1, +0, +1, +2, +3 };
int[] percentage = new int[] { 0, 1, 1, 2, 5, 1, 0 };

int s = 0;
foreach (int step in steps)
{
    int random_count = percentage[s++];
    for (int rc = 0; rc < random_count; ++rc)
        hops.Add(step);
}
```

A `step` is a note's jump distance (hop) from one pitch to another.
In case of Bhupali, with a random step of `+2`, next note after `S` would be `G`.
But if the step was `-1` the next note selected will be `D.`.
The percentage chances of appearance of `-1` is 10%.
The percentage chances of appearance of `+1` is 50%.
The population of note being -3 and +3 are 0% in this particular example.

So, after `S`, the next note could be something between -2 and +2 note away, with a maximum chance of being `R` (+1, 50%).
But it might yield anything out of -2: `P.`, -1: `D.`, +0: `S`, +1: `R`, +2: `G`.
For the next loop, the starting note will the the one just selected.
And again, another random note is picked up from new point.

A biger jump distance, eg: -4 or +4 would create a very different/nasty pitch.
It can include notes from another octave.
-3 and +3 aren't even polite to ears.
So, the maximum population of notes has to stay within -2, -1, -, +1, +2 range.

Meanwhile, I am unable to address:
* [vaadi](https://en.wikipedia.org/wiki/Vadi_(music))
* [samvaadi](https://en.wikipedia.org/wiki/Samavadi)
* nyaasa (landing) notes.

## Raaga SQL table structure

```
CREATE TABLE "classical_raags" (
	"raag_id"	TEXT NOT NULL,
	"thaat_id"	TEXT NOT NULL,
	"raag_number"	INTEGER NOT NULL,
	"raag_name"	TEXT NOT NULL,
	"raag_thaat"	TEXT NOT NULL,
	"raag_ascending"	TEXT NOT NULL,
	"raag_descending"	TEXT NOT NULL,
	"raag_varjit"	TEXT NOT NULL,
	"raag_pakad"	TEXT NOT NULL,
	"raag_chalan"	TEXT NOT NULL,
	"raag_vaadi"	TEXT NOT NULL,
	"raag_samvaadi"	TEXT NOT NULL,
	"raag_vivadi"	TEXT NOT NULL,
	"raag_nyasa"	TEXT NOT NULL,
	"raag_timing"	TEXT NOT NULL,
	"raag_notes"	TEXT NOT NULL,
	"raag_processed"	TEXT NOT NULL,
	PRIMARY KEY("raag_id")
);
```

Population data is store as:

```
CREATE TABLE "population" (
	"population_id"	TEXT NOT NULL,
	"population_name"	TEXT NOT NULL,
	"population_lines"	TEXT NOT NULL,
	"step_minus3"	TEXT NOT NULL,
	"step_minus2"	TEXT NOT NULL,
	"step_minus1"	TEXT NOT NULL,
	"step_zero0"	TEXT NOT NULL,
	"step_plus1"	TEXT NOT NULL,
	"step_plus2"	TEXT NOT NULL,
	"step_plus3"	TEXT NOT NULL,
	"group_name"	TEXT NOT NULL UNIQUE,
	PRIMARY KEY("population_id")
);
```

step_minus3 means -3, and its datbase value is the population count.
Similar for other populations of -2, -1, +0, +1, +2, +3 notes.

Unique column group name is associated in the song struture.
For example, my example data has:

Population Name | Group Name
----------------|-----------
[Aalap](https://en.wikipedia.org/wiki/Alap)             | A
Aalap Closer                                            | B
[Chorus](https://en.wikipedia.org/wiki/Chorus)          | C
Sthaai                                                  | D
[Antaraa](https://en.wikipedia.org/wiki/Antara_(music)) | E
Bridge          | F
Closer          | G
Sanchaari       | H
Aabhog          | I
Outro           | J

The purpose of pushing these population configuration to database is to allow a user too change the behaviour/reaction of the application, without having to rewrite/compile the code.

However, you can now write a lyrically recitable poetry with these group names. Please see melody structure above.

## Incompleteness

The raag database would serve the list of possible notes (I considerd ascending notes only; and hence the implementation is incomplete.)

The random number generated between -3 and +3 is a swinging index.
It's purpose is to help us pick a note from the array of notes.
Notes are aligned circulalry in the array. `S*` and next +1 note should have been: `R*`.
But since I have not implemented the descending notes and there is no new jump into higher octave ([taar saptak](https://en.wikipedia.org/wiki/Tar_Saptak)), it is underterministic.
Sometimes, notes stay static at `S*` for few times, yielding notes like: `S* S*,S* S* -` in the peaks.
Same thing happens at the valleys of the notes: `S` repeats in bottom instead of going into lower octave ([mandhra saptak](#)).

![image](https://user-images.githubusercontent.com/5563341/212498847-99dbc9c8-944f-47b5-b5f6-ab2d90d388a7.png)

## Will the sound be useful?

I am just looking for some ambience in the final output.
But, you can regenerate your own varieties and use then in different ways.

It should ideally support other raags as well.

Plese let me know your interests in the un-sanitized source codes I have now.

## What did I achieve?

In this experientation, I:

* solved the problem of parsing SARGAM notations.
* got more skills on C# and xml handling.
* built APIs around this theme.
* enhanced skills on LMMS instrumentation.
* gained more information about classical music in theories.
* brought up a [software](#) to write SARGAM notations that can be conveted into melodious audio.
* opened an opportunity of Raag detection for a given SARGAM.
* collaborated with some authors.
* gained confidence in the areas covered.

## Notices

* The pictures attached are for representation only.
* Randomization attempt does not supress creativity in note selection.
* This article was written by human hands, not AI generated.
* I do not have affilitions to the third party links.
* Everything in this project is an experiment.
* The included project is at some point, generated randomly, and it should not match to existing melodies.
