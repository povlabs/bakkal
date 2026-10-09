# bakkal

Small part-of-speech models for reading apps. One model file per language,
trained with a plain averaged perceptron on Universal Dependencies treebanks
that allow commercial use.

## Models

| Language | File | SHA-256 | Licence |
| --- | --- | --- | --- |
| Italian | [`models/it.json`](models/it.json) | `55ed305a4825d0db64554b4c8d337ba8a30a051a2e8e34d0cd3c5c27ca9484e3` | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) |

Check a download with `shasum -a 256 models/it.json`.

A model file is one JSON object. Its `provenance` header lists every training
source, with its release, commit, archive SHA-256 and licence, the Lexema
release its lexicon features were read from, and the command that trains it
again. Its `model` field holds the tagger's weights. The file holds no word
list from Lexema.

## Italian model: training sources and attribution

The Italian model was trained on five treebanks from
[Universal Dependencies](https://universaldependencies.org/) release r2.18.
Each row names the exact commit and the SHA-256 of the release archive
(`https://github.com/UniversalDependencies/<treebank>/archive/refs/tags/r2.18.tar.gz`).

| Treebank | Licence | Commit | Archive SHA-256 |
| --- | --- | --- | --- |
| [UD_Italian-MarkIT](https://github.com/UniversalDependencies/UD_Italian-MarkIT/tree/957127de2b1d10303dc1a1fdd132598ba708d705) | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | `957127de2b1d10303dc1a1fdd132598ba708d705` | `c2e076e016d022d0bfd0171f768e4d134abf126c4a3a1a565e8e4cd5639aaf63` |
| [UD_Italian-TWITTIRO](https://github.com/UniversalDependencies/UD_Italian-TWITTIRO/tree/2546072afed14d204052f4210eee94110f4ff467) | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | `2546072afed14d204052f4210eee94110f4ff467` | `5fce7ea1345cb3ada51f56574f331026ba823c5accda0d941e5dc60e0372f770` |
| [UD_Italian-ParlaMint](https://github.com/UniversalDependencies/UD_Italian-ParlaMint/tree/45c92e77b6163e8aa311c205aa510896a66e0654) | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | `45c92e77b6163e8aa311c205aa510896a66e0654` | `1858c066a0c815ed48b2baf064d06e4f6612d635f7bee1dd2ba4c7b6fbfe2cf7` |
| [UD_Italian-PUD](https://github.com/UniversalDependencies/UD_Italian-PUD/tree/bae2181e24fef395d662b22190e7eb5725dac3b5) | [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/) | `bae2181e24fef395d662b22190e7eb5725dac3b5` | `12f6fc7e5eda8124649639ea7780664a92032985bfa0039faf1a9b001802e69c` |
| [UD_Italian-Valico](https://github.com/UniversalDependencies/UD_Italian-Valico/tree/487cc1674ec42b6af933a9e0c7b54d7d99333ea8) | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | `487cc1674ec42b6af933a9e0c7b54d7d99333ea8` | `aa255b544d9dd9f0ff35269ea63270fdde9a175567bc6f817071df266de1090e` |

Credit, as each treebank's README names its authors:

- **UD_Italian-MarkIT**: Teresa Paccosi, Alessio Palmero Aprosio and Sara
  Tonelli. "It is MarkIT That is New: An Italian Treebank of Marked
  Constructions", CLiC-it 2021.
- **UD_Italian-TWITTIRO**: Alessandra T. Cignarella, Cristina Bosco and
  Manuela Sanguinetti. "Presenting TWITTIRÒ-UD: An Italian Twitter Treebank in
  Universal Dependencies", Depling (SyntaxFest) 2019.
- **UD_Italian-ParlaMint**: Chiara Alzetta, Marta Sartor, Simonetta
  Montemagni and Giulia Venturi, from the ParlaMint-IT corpus (Agnoloni et al.,
  ParlaCLARIN III, LREC 2022).
- **UD_Italian-PUD**: Hans Uszkoreit, Vivien Macketanz, Aljoscha Burchardt,
  Kim Harris, Katrin Marheinecke, Slav Petrov, Tolga Kayadelen, Mohammed Attia,
  Ali Elkahky, Zhuoran Yu, Emily Pitler, Saran Lertpradit, Antonio Stella,
  Davide Rovati, Martin Popel, Daniel Zeman, Maria Simi and Manuela
  Sanguinetti. Part of the Parallel Universal Dependencies treebanks of the
  CoNLL 2017 shared task.
- **UD_Italian-Valico**: Elisa Di Nuovo, Manuela Sanguinetti, Cristina Bosco
  and Alessandro Mazzei. "VALICO-UD: Treebanking an Italian Learner Corpus in
  Universal Dependencies", IJCoL 8(1), 2022.

The lexicon features were read from Lexema's public dump, release
`it-0c432803`
([povlabs/lexema-data](https://github.com/povlabs/lexema-data)), a
Wiktextract extract of the Italian Wiktionary by its contributors, under
[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). The model
keeps no word list from it.

No other source was trained on. UD_Italian-ISDT (CC BY-NC-SA 3.0) was used to
score the model only; none of its sentences were trained on, and none are in
this repository.

## Licence

Model files are released under
[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) (see
[LICENSE](LICENSE)), because some of their training data is CC BY-SA. Each
model adapts the works listed above. When you share a model or a work built on
it, credit those works and keep the same licence.
