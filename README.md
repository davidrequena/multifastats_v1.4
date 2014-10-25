multifastats
============

Multifastats: Multi-Fasta Sequence Stats. Free program based in a python
script, to calculate basic statistics and filters (N50, %GC, length, types,
molecular weight) for a set of 'fasta' sequences (and optionally for each
single sequence too).

-------------------------------------------------------------------------------

>Version 1.4.2, 24-Oct-2014.
Made by David Requena. Laboratory of Bioinformatics and Molecular Biology.
Universidad Peruana Cayetano Heredia. Lima, Peru.
This code will be updated and freely available in GitHub:
https://github.com/lbbm-upch/multifastats

-------------------------------------------------------------------------------

*** HELP INFO ***
-------------------------------------------------------------------------------
Multifastats: Multi-Fasta Sequence Stats

Python script to calculate basic genomic statistics for a set of sequences,
and optionally for each single sequence, too.

- - - - - - -
REQUIREMENTS:
- - - - - - -
To run this program, python 2.7 and the following packages are required:
* biopython - http://biopython.org/wiki/Download
* pyreadline (for Windows and Mac) - https://pypi.python.org/pypi/pyreadline/

Preferably, use python v2.7 32-bits because Biopython is only compatible with
x86 but not x64 (a numpy issue). So, you have to use the pyreadline 32-bits
version. I made this program with biopython v1.64 and pyreadline v2.0, but
other versions will be compatible.

- - - -
USAGE:
- - - -
The script multifastats.py has to be in the same directory of your file to analyze.
If you want to use the program from any location, please read the 'Optional' section.

There are two modes:

a) 'User-Interactive':
The program will ask for a file or option in each step.
To use in this mode, run the script with NO arguments. The program will ask
you the name of the file you want to analyze (autocomplete allowed in LINUX).
To use the program in this mode, just run the script with doble-click or call
it from command-line as follows:

>>~$ python multifastats.py

b) 'Command-Line':
File name, length cut-off and single analysis options have to be given from the
beggining. To use the program in this mode, run the script from command-line as
follows:

>>~$ python multifastats.py -f (inputfile)

* -f (or --file)	:	Allows to give an input file name. In the above line, replace
				(inputfile) with the name of your file (including the extension).
				An example file name would be: myseq.fasta

You will add some options after the (inputfile) name, like:
	
* -l (or --length)	:	Add a cutf-off for the sequences length to be analyzed: greater
				or equal to this value. Only positive numbers allowed! If you
				give 0, all sequences will be analyzed.
* -s (or --single)	:	Add the single sequence analysis. IMPORTANT: This option has to
				be the last given.
As example, one command line with all options will be:

>>~$ python multifastats.py -f inputfile.fasta -l 500 -s

- - - - - - -
INFO OPTIONS:
- - - - - - -
You will give some arguments to get some program info:

* -h (or --help)	 :	General description and usage of the program.
* -v (or --version)	 :	Version and revision of the program.
* -i (or --info)	 :	Information about the parameters calculated.
* -n (or --notes)	 :	Notes about the current and previous versions program.

- - - - -
Optional:
- - - - -
Maybe you will have more fun if you copy the script to '/usr/local/bin' 
and give some permisions (chmod +xr). This will allow you to call it and use
directly from the terminal in any directory of your computer and allow to
autocomplete the name of any file (not only python scripts).
You will do that with the following commands in the linux terminal:

>>~$ sudo chmod +xr multifastats.py

>>~$ sudo mv multifastats.py /usr/local/bin

Then, you will call the program from any location in your user. So, instead to
write '~$ python multifastats.py' you just need to write '~$ multifastats.py'

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
REALLY IMPORTANT TO DECLARE:
- - - - - - - - - - - - - - -
Some parts of the code was adapted from multiple sources freely available
developed by the scientific community, like SQUID's seqstat, Peter 'maubp' N50
(seqanswers.com) and biopython packages. This code is free to use, modify and
distribute under the MIT License.

***Thanks to my lab friends by the exhaustively testing as intended bad users.

And please, share your doubts, comments, request to add new options or
improves with us! Write to: david.requena.a@upch.pe

Thank you!
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

*** PARAMETERS INFORMATION ***
-------------------------------------------------------------------------------

For sets of sequences, the parameters calculated are:

- Num of Sequences: Count the total number of sequences in the multifasta file.
- Min, Max and Average length: Gives the minimum, maximum and average sequence
  length in the multifasta file, respectively.
- N50 value: This parameter is calculated using the Broad Institute definition:
  https://www.broad.harvard.edu/crd/wiki/index.php/N50
- Number of residues: Count the total number of nucleotides (or aminoacids) in
  all the sequences in the multifasta file.
- Total %GC in file: This parameter calculates the percentage of G, C or S (G
  or C) nucleotides (no case sensitive) in the complete set of sequences.

For each sequence, the parameters calculated are:

A .csv file is write in the current working directory:
sganl_(FILENAME)_(TIME).csv
This contains each single sequence stats:

- N: Number of the sequence in the set of sequences.
- ID: ID (header) of the sequence.
- Length: Number of nucleotides (or aminoacids) in the sequence.
- %GC: Percentage of G, C or S (G or C) nucleotides (no case sensitive) in the
  sequence.
- Mol Weight: Molecular weight of the sequence, calculated according the
  molecular_weight() function from Biopython SeqUtils:
  http://biopython.org/DIST/docs/api/Bio.SeqUtils-module.html#molecular_weight

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

*** VERSION NOTES ***
-------------------------------------------------------------------------------
History:
- Version 1.4.2 (D.R. 24-Oct-2014):
  Adding autocomplete using tab in Windows and MAC OS.
- Version 1.4.1 (D.R. 23-Oct-2014):
  Including the revisions after testing of many users.
- Version 1.4 (D.R. 23-Oct-2014):
  Adding length cut-off, indicate type(s) of sequences and Windows compatibility.
  Public available in GitHub, under the MIT License.
- Version 1.3 (D.R. 22-Oct-2014):
  Adding command-line mode with -f, -s and info options.
  Adding version, notes, help and full documentation.
- Version 1.2 (D.R. 21-Oct-2014):
  Adding autocomplete using tab, single sequences analysis and time-csv output
  in current directory.
- Version 1.1 (D.R. 21-Oct-2014):
  Adding user-interactive mode, min, max, average length and 0.00 format.
- Version 1.0 (D.R. 20-Oct-2014):
  The basic version, just calculate the N50, %GC, number of sequences and total
  residues in the multifasta by a given file name inside the script.

***For the Version 1.5, I'm implementing the following new options:
- Filter by sequence type.
- Upper length cut-off.
- Filter by any string in sequence name.
- A fasta output of the selected subset of sequences.
- The pseudomolecule output.
- Top Blast-Hit for each single sequence (given certain parameters).

...Available coming soon!!!

Requests for new options are welcome!
