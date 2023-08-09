# AnnoMazing
A one stop tool for annotating protein files using multiple hmm databases.
![alt text](https://github.com/BenMinch/AnnoMazing/blob/main/images/AnnoMazing.png)
## Dependencies
1. HMMER3 (3.3.2)
2. Python (3.9.12)
3. Python packages (Bio=1.76,pandas=2.0)

## Installation
All you need to do is clone this repository. Pretty easy

### Setting up Databases
For all your databases you are going to have to first download the hmm files. Below are just some of these databases
1. [Pfam](https://www.ebi.ac.uk/interpro/download/Pfam/)
2. [VOG](https://vogdb.org/download)
3. [GVDB](https://faylward.github.io/GVDB/)

After you install an hmm database, you will need to also install a corresponding annotation csv that has annotations of the protein families in the hmm database. An example of some of these is here for pfam,VOG, and GVDB if you want to see what they look like. **After installing this file for each database you intend to use, change the first column header to be "id" as it will not work without this change.**

Before using your databases for the first time, you will have to index them with `hmmpress database` . This will create many indexed database files. Make sure you don't delete these.

## Usage

`python AnnoMazing.py -i [protein_file] -o [output_name] -db database1,database2 -annot annotation1,annotation2`

**Flags**
-i: input fasta file with protein sequences
-o: name of output file, can be anything
-db: a comma separated list (no spaces) of all the databases you want to use
-annot: a comma separated list (no spaces) of all the annotation files you want to use. Must be in same order as the database list.

### Outputs
The output is a single csv file named [outname]_final.csv. This file will have all of your annotations for all of your proteins in it. An example output file is given here. 

# Copywrite
AnnoMazing Copyright (C) 2023 Benjamin Minch

This program is free software: you can redistribute it and/or modify it under the terms of the MIT License.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the MIT License for more details.
