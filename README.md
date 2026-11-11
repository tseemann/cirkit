[![CI](https://github.com/tseemann/cirkit/workflows/CI/badge.svg)](https://github.com/tseemann/cirkit/actions)
[![GitHub release](https://img.shields.io/github/release/tseemann/cirkit.svg)](https://github.com/tseemann/cirkit/releases)
[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Conda](https://img.shields.io/conda/dn/bioconda/cirkit.svg)](https://anaconda.org/bioconda/cirkit)
[![Language: Perl 5](https://img.shields.io/badge/Language-Perl%205-blue.svg)](https://www.perl.org/)

# cirkit

Identify signal peptides in protein sequnces

## Description

I want to make an free, unencumbered tool to
identify signal peptides in protein sequences.
The existing tools are either not open source,
require an academic licence, only have a 
webserver, or not installable in Bioconda.

Ziggypep uses a very simplistic method 
which achieves
1026/1320 (72%) on a 
[positive test set](https://github.com/tseemann/cirkit/blob/main/test/pos.faa)
and 1234/1334 (93%) on a
[negative test set](https://github.com/tseemann/cirkit/blob/main/test/neg.faa.bz2).

## Installation

```
conda install -c bioconda -c conda-forge cirkit
```

## Quick start

```
% cirkit test/test.faa.gz

WP_456262590.1  0
WP_407478045.1  14      MDTLQAIILAIVEG
WP_456262591.1  0
WP_456262592.1  38      MKQLPTITDSYKKEVQKSVLSIILFFTVYFILILFSLA
WP_249063066.1  0
WP_016200366.1  0
WP_078792968.1  20      MKKIAVLITMLMTGIIFAQV

# only list those with signal peptides
% cirkit -s test/test.faa.gz

WP_407478045.1  14      MDTLQAIILAIVEG
WP_456262592.1  38      MKQLPTITDSYKKEVQKSVLSIILFFTVYFILILFSLA
WP_078792968.1  20      MKKIAVLITMLMTGIIFAQV
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

* [Circlator]](https://github.com/sanger-pathogens/circlator)
* [Flye](https://github.com/mikolmogorov/Flye)

## Feedback

File questions, bugs, or ideas on the 
[Issues page](https://github.com/tseemann/cirkit/issues)

## License

[GPLv3](https://raw.githubusercontent.com/tseemann/cirkit/master/LICENSE)

## Author

[Torsten Seemann](https://tseemann.github.io)
