![Version](https://img.shields.io/github/v/release/DCMLab/peri_euridice?display_name=tag)
[![DOI](https://zenodo.org/badge/503810048.svg)](https://doi.org/10.5281/zenodo.14996445)
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/peri_euridice)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/peri_euridice](https://github.com/DCMLab/peri_euridice) and the corresponding
* documentation page [https://dcmlab.github.io/peri_euridice](https://dcmlab.github.io/peri_euridice)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/peri_euridice/introduction).

# Jacopo Peri – Euridice (1600) (A corpus of annotated scores)

This is, decisively, the oldest surviving opera; the first opera, the lost Dafne, was written by the same composer. The
Greek myth of Orpheus and Eurydice was a powerful inspiration for the earliest opera composers, having also been adapted
in the few years after by Giulio Caccini (Euridice, 1602) and Claudio Monteverdi (Orfeo, 1607, the most widely performed
of these). Peri, Caccini, and (likely) librettist Ottavio Rinuccini were all members of the Florentine Camerata, a group
which sought to return Western music to its Ancient Greek roots by supplanting the lush choral counterpoint of the day
with bare solo singing over simple accompaniment, often using speech-like prosody. It is interesting to observe,
compared to later opera, how seldom vocal virtuosity is highlighted: we do not see the contrast of elaborate aria and
dry recitative that would be established as a convention of the form soon after. This is one of the oldest works in the
DCML corpora (Sweelinck's Fantasia cromatica may or may not be older), and its analysis reflects, in nearly the simplest
of possible uses, the frameworks that continued to emerge in tonal harmony for centuries after.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/peri_euridice/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [peri_euridice.zip](https://github.com/DCMLab/peri_euridice/releases/latest/download/peri_euridice.zip)
  * [peri_euridice.datapackage.json](https://github.com/DCMLab/peri_euridice/releases/latest/download/peri_euridice.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/peri_euridice.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the *Prologo* has the following files:

* `MS3/peri_euridice_scene_0.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/peri_euridice_scene_0.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/peri_euridice_scene_0.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/peri_euridice_scene_0.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/peri_euridice_scene_0.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/peri_euridice_scene_0.harmonies.tsv")
notes = ms3.load_tsv("notes/peri_euridice_scene_0.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/peri_euridice/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/peri_euridice/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Jacopo Peri – Euridice (1600) (A corpus of annotated scores) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.14996445

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## Overview
|      file_name      |measures|labels|standard| annotators  |reviewers|
|---------------------|-------:|-----:|--------|-------------|---------|
|peri_euridice_scene_0|      14|    31|2.3.0   |Davor Krkljus|ST       |
|peri_euridice_scene_1|     119|   342|2.3.0   |Davor Krkljus|ST       |
|peri_euridice_scene_2|     288|   732|2.3.0   |Davor Krkljus|ST       |
|peri_euridice_scene_3|     135|   323|2.3.0   |Davor Krkljuš|ST       |
|peri_euridice_scene_4|     304|   721|2.3.0   |Davor Krkljus|ST       |
|peri_euridice_scene_5|     260|   735|2.3.0   |Davor Krkljus|ST       |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
