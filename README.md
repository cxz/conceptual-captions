# Conceptual Captions Dataset

Conceptual Captions is a dataset containing (image-URL, caption) pairs designed
for the training and evaluation of machine learned image captioning systems.

## Motivation

Automatic image captioning is the task of producing a natural-language
utterance (usually a sentence) that correctly reflects the visual content of an
image. Up to this point, the resource most used for this task was the
[MS-COCO dataset](http://http://cocodataset.org), containing around 120,000
images and 5-way image-caption annotations (produced by paid annotators).

Google's Conceptual Captions dataset has more than 3 million images, paired
with natural-language captions. In contrast with the curated style of the
MS-COCO images, Conceptual Captions images and their raw descriptions are
harvested from the web, and therefore represent a wider variety of styles. The
raw descriptions are harvested from the Alt-text HTML attribute associated with
web images. We developed an automatic pipeline that extracts, filters, and
transforms candidate image/caption pairs, with the goal of achieving a balance
of cleanliness, informativeness, fluency, and learnability of the resulting
captions.

More details are available in this paper (please cite the paper if you use or discuss this dataset in your work):
</p>
<div class="highlight highlight-source-shell"><pre>
@inproceedings{sharma2018conceptual,
  title = {Conceptual Captions: A Cleaned, Hypernymed, Image Alt-text Dataset For Automatic Image Captioning},
  author = {Sharma, Piyush and Ding, Nan and Goodman, Sebastian and Soricut, Radu},
  booktitle = {Proceedings of ACL},
  year = {2018},
}
</pre></div>

## Dataset Description

Conceptual Captions dataset release contains two splits: train (~3.3M examples) and validation (~28K examples).
See Table 1 below for more details.

<p align='center'>Table 1: Dataset stats.</p>

<table>
  <tr>
    <td colspan="3"></td>
    <td colspan="3"><center><b>Tokens per Caption</b></center></td>
  </tr>
  <tr>
    <td><b>Split</b></td>
    <td><b>Examples</b></td>
    <td><b>Uniqe Tokens</b></td>
    <td><b>Mean</b></td>
    <td><b>StdDev</b></td>
    <td><b>Median</b></td>
  </tr>
  <tr>
    <td>Train</td>
    <td>3,318,333</td>
    <td>51,201</td>
    <td>10.3</td>
    <td>4.5</td>
    <td>9.0</td>
  </tr>
  <tr>
    <td>Valid</td>
    <td>28,355</td>
    <td>13,063</td>
    <td>10.3</td>
    <td>4.6</td>
    <td>9.0</td>
  </tr>
  <tr bgcolor="#808080">
    <td>Test (Hidden)</td>
    <td>22,530</td>
    <td>11,731</td>
    <td>10.1</td>
    <td>4.5</td>
    <td>9.0</td>
  </tr>
</table>


## Hidden Test set

We are not releasing the official test split (~22.5K examples) used to report the official results in the paper.
Instead, we are hosting a competition (TBA) dedicated to supporting submissions and evaluations of model outputs on this blind test set.

We strongly believe that this setup has several advantages: a) it allows the evaluation to be done using an unbiased, large number of images b) it keeps the test completely blind and eliminate suspicions of fitting to the test, cheating, etc. c) it overall provides a clean setup for advancing the SoTA on this task, including reporting reproducible results for paper publications, etc.


## Data Format

The released data is provided as TSV (tab-separated values) text files with the following columns:

<p align='center'>Table 2: Columns in TSV files.</p>

| Column   | Description                                                       |
| -------- | ----------------------------------------------------------------- |
| 1        | Caption. The text has been tokenized and lowercased.              |
| 2        | Image URL                                                         |


## Contact us

If you would like to share feedback or report concerns, please email us at conceptual-captions-contact@google.com
