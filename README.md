[![CI](https://github.com/tseemann/cirkit/workflows/CI/badge.svg)](https://github.com/tseemann/cirkit/actions)
[![GitHub release](https://img.shields.io/github/release/tseemann/cirkit.svg)](https://github.com/tseemann/cirkit/releases)
[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Conda](https://img.shields.io/conda/dn/bioconda/cirkit.svg)](https://anaconda.org/bioconda/cirkit)
[![Language: Perl 5](https://img.shields.io/badge/Language-Perl%205-blue.svg)](https://www.perl.org/)

# cirkit

Identify signal peptides in protein sequnces

## Description

When assembling bacterial genomes from 
long read ONT data, the Flye assembler
will often generate single contig plasmids,
but they are longer than they should be.
This is due to various reasons, but incoudes
read overhang and lack of trimming of 
circular elements in the graph. This results
in concatemers of the plasmid, where you will
get a contig with 2-3 tandem repeats of the
true plasmid. This software will automatically
extract the best single copy from that output.

## Installation

```
conda install -c bioconda -c conda-forge cirkit
```

## Quick start

```
% cirkit test/test1.fna

### FIXME ###

```

## Usage

### Input

You must provide a single-conmtig plasmid DNA FASTA files:
```
>Plasmid
CACCGTGAAGTTATGATCAACGATGTAGTCCACATCATTGTCGAAATGTGCGTTCAGCTA
GTCTTCGGTGTTTTCTGCTTTATTTCTAGCGGCGATTCTCGCGTCTGCCCATGCGGCAGA
CTTTTTAGCCTGTTCTCGTTGTTCTTCGGTTGAAGACTCGCTGTTGAGAACTTTGTTGCT
...
```
They can be compressed with `.gz` or `.bz2`.
You can provide multiple files if you like.
```
% cirkit test/test.ffa.gz test/pos.faa test/neg.faa.bz2 
```
Each sequence (not file) will be treated independently.

### Output

FIXME.

### Options

```
  -h       Print this help
  -v       Print version and exit
  -C       Show citation and exit
  -q       No output while running, only errors
```

## References

* [Circlator](https://github.com/sanger-pathogens/circlator)
* [Flye](https://github.com/mikolmogorov/Flye)

## Feedback

File questions, bugs, or ideas on the 
[Issues page](https://github.com/tseemann/cirkit/issues)

## License

[GPLv3](https://raw.githubusercontent.com/tseemann/cirkit/master/LICENSE)

## Author

[Torsten Seemann](https://tseemann.github.io)
