# ARCHE-WD Word Rain supplementary materials

This repository contains supplementary materials associated with the forthcoming paper *Distant and Close Reading Approaches to Specialised Language in the ARCHE Strategic Research and Innovation Agenda Corpus* by Elisa Squadrito, Francesca Frontini and Vania Virgili.

The materials include visualisations and related outputs produced for the analysis presented in the article using Word Rain (Skeppstedt et al., 2024), a visualisation technique extending the classic word cloud approach. The code used as the basis for the present analysis is available from the official Word Rain GitHub repository: https://github.com/CDHUppsala/word-rain.

The study applies Word Rain to the exploration of specialised language in cultural heritage policy discourse, combining distant-reading visualisation with close-reading analysis. The visualisations were produced from ARCHE-WD, a corpus of working documents developed within the Alliance for Research on Cultural Heritage in Europe (ARCHE) and contributing to the development of the Strategic Research and Innovation Agenda (SRIA) for the domain.

The repository provides access to the full-size Word Rain outputs discussed in the article, allowing closer inspection than is possible within the constraints of the published figures. It also includes supporting files generated during the Word Rain workflow, such as newly appearing word lists, exported metrics and parameter notes. These materials are provided to increase transparency and support the reproducibility of the visualisation-based component of the analysis.

The documents analysed with Word Rain are:

1. **ARCHE D2.1 Future Trends on Cultural Heritage (Foresight Analysis)** — 69,112 tokens
2. **ARCHE D2.4 Vision and Mission** — 15,775 tokens
3. **ARCHE D2.5 SRIA Key Messages and Preliminary Findings** — 8,557 tokens
4. **ARCHE SRIA Working Group Forms** — 7,468 tokens

## Word Rain generation settings

The following settings were used to generate the ARCHE-WD Word Rain visualisations:

* **Embedding model:** `word2vec-google-news-300`
* **Stopword filtering:** NLTK English stopword list combined with a custom stopword list
* **Token pattern:** alphabetic tokens of at least two characters; numbers, including years, were excluded
* **Lowercase normalisation:** enabled
* **TF-IDF weighting:** enabled
* **N-grams:** unigrams and bigrams, `n = 1–2`
* **Minimum document frequency:** `1`
* **Unified graph layout:** enabled
* **Compact display mode:** enabled
* **Maximum number of plotted words per visualisation:** `300`
* **New-word marking:** enabled
* **Automatic title generation:** enabled
* **Page size:** `600 × 500`
* **Base font size:** `25`
* **Font-size falloff rate:** `0.7`
* **Vertical guide lines:** `4`
* **Vertical line style:** dotted

The four subcorpora were processed together in a unified graph layout so that lexical items were projected within a shared semantic space and remained comparable across visualisations. The subcorpora were ordered as follows:

1. Foresight Analysis
2. Vision and Mission
3. Key Messages and Preliminary Findings
4. Working Group Forms

The “new words” output depends on this ordering, since lexical items already appearing in an earlier visualisation are not marked as new in subsequent ones.

The Word Rain scores, raw frequencies and relative frequencies included in the output files are those exported by Word Rain. They may differ from counts obtained with other corpus tools because of differences in tokenisation, preprocessing, lowercasing, n-gram handling and corpus-processing settings.

## Repository contents

### Main visualisation

File:

* `figures/arche-wd-wordrain-aligned-visualisations.pdf`

This PDF contains the aligned unified Word Rain visualisations generated for the ARCHE-WD corpus.

### Word Rain plot-data JSON files

Folder:

* `plot-data-json/`

Files:

* `01-foresight-analysis.json`
* `02-vision-and-mission.json`
* `03-key-messages-preliminary-findings.json`
* `04-working-group-forms.json`

The `.json` files are machine-readable plot-data files exported by Word Rain for each subcorpus. Each file contains the data used to generate the corresponding Word Rain visualisation, including the plotted lexical items and n-grams, their scores, projected x-axis positions, plotted font sizes, raw frequencies, relative frequencies and display information.

In the exported JSON files, each entry in the `sorted_word_scores` field has the following structure:

`[word, score, x, fontsize, freq, relfreq, show]`

Here, `x` is the one-dimensional position used in the visualisation. The final `show` field contains display information for the plotted item as exported by Word Rain. The `score`, `freq` and `relfreq` values are Word Rain output values and may differ from counts obtained with other corpus tools, such as Sketch Engine, because of differences in tokenisation, preprocessing, lowercasing, n-gram handling and corpus-processing settings.

### Textual Word Rain output lists

Folder:

* `output-lists/`

Files:

* `01-foresight-analysis.tsv`
* `02-vision-and-mission.tsv`
* `03-key-messages-preliminary-findings.tsv`
* `04-working-group-forms.tsv`
* `all-subcorpora.tsv`

The `.tsv` files are tab-separated Word Rain output lists exported for each subcorpus and for the combined output. Each line contains a lexical item or n-gram followed by three numerical values exported by Word Rain: the Word Rain score, the raw frequency and the relative frequency per 1,000 tokens. The score corresponds to the TF-IDF value used by Word Rain.

### New-word output lists

Folder:

* `new-word-lists/`

Files:

* `01-foresight-analysis-new-words.txt`
* `02-vision-and-mission-new-words.txt`
* `03-key-messages-preliminary-findings-new-words.txt`
* `04-working-group-forms-new-words.txt`

These files contain the lexical items marked as newly appearing in each step of the aligned Word Rain visualisation. This output depends on the ordering of the subcorpora, since words that appear in an earlier visualisation are not marked as new in later ones.

## Scope of the repository

This repository includes Word Rain visual outputs and tool-generated output lists only. It does not include the raw ARCHE-WD corpus texts. The files are provided as supplementary material for inspection and transparency. They do not replace the close-reading analysis presented in the article.

## Citation

If you use or refer to these supplementary materials, please cite the archived Zenodo release of this repository and the associated paper.

```bibtex
@article{SquadritoFrontiniVirgiliForthcomingARCHEWD,
  author = {Squadrito, Elisa and Frontini, Francesca and Virgili, Vania},
  title = {Distant and Close Reading Approaches to Specialised Language in the ARCHE Strategic Research and Innovation Agenda Corpus},
  journal = {Journal of Digital Terminology and Lexicography},
  year = {2026},
  note = {Forthcoming}
}
```

Word Rain should be cited as:

```bibtex
@article{SkeppstedtEtAl2024WordRain,
  author = {Skeppstedt, Maria and Ahltorp, Magnus and Kucher, Kostiantyn and Lindstr{\"o}m, Matts},
  title = {From Word Clouds to Word Rain: Revisiting the Classic Word Cloud to Visualize Climate Change Texts},
  journal = {Information Visualization},
  volume = {23},
  number = {3},
  pages = {217--238},
  year = {2024},
  doi = {10.1177/14738716241236188}
}
```
