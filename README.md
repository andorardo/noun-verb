# noun-verb
This dataset contains set of English sentences that have hard cases of ambiguous tokens being noun or verb. The dataset contains ~32 examples.

## Description

The dataset contains sentences in CoNLL format. Each sentence has single token annotated as either VERB or NON-VERB. The data sources are Wikipedia, Wikihow and Search Ads. Before each sentence there is a comment line with the source of the sentence. In case of Wikipedia and Wikihow, the url of the source page for the sentence is included.

The annotations is done through crowdsourcing as described in [1]. Note that some of the examples are filtered from the dataset used in the paper. The results for all the used models in the paper is recomputed for the filtered dataset the New Results section.

The dataset is splitted into Train/Dev/Test sections. For Dev and Test sections the annotations included either VERB or NON-VERB in XPOS, UPOS  and FEATS columns. For the Train section, XPOS and UPOS columns are replaced with fine POS tag obtained by running automatic tagger and select the top tag that matched the crowdcompute label.

## Examples

Example from the Dev and Test splits:

# http://www.wikihow.com/Replace-Broken-Glass-in-a-Picture-Frame
1	Once	_	_	_	_	-1	_	_	_
2	you	_	_	_	_	-1	_	_	_
3	have	_	_	_	_	-1	_	_	_
4	the	_	_	_	_	-1	_	_	_
5	new	_	_	_	_	-1	_	_	_
6	glass	_	_	_	_	-1	_	_	_
7	,	_	_	_	_	-1	_	_	_
8	cleaning	_	VERB	VERB	POS=VERB|fPOS=VERB	-1	_	_	_
9	and	_	_	_	_	-1	_	_	_
10	replacing	_	_	_	_	-1	_	_	_
11	it	_	_	_	_	-1	_	_	_
12	is	_	_	_	_	-1	_	_	_
13	all	_	_	_	_	-1	_	_	_
14	that	_	_	_	_	-1	_	_	_
15	's	_	_	_	_	-1	_	_	_
16	left	_	_	_	_	-1	_	_	_
17	.	_	_	_	_	-1	_	_	_

Example from the Train split

# http://www.wikihow.com/Make-an-Audio-CD-With-Windows-7
1	Try	_	_	_	_	-1	_	_	_
2	to	_	_	_	_	-1	_	_	_
3	copy	_	VB	VB	POS=VERB|fPOS=VERB	-1	_	_	_
4	and	_	_	_	_	-1	_	_	_
5	paste	_	_	_	_	-1	_	_	_
6	the	_	_	_	_	-1	_	_	_
7	file	_	_	_	_	-1	_	_	_
8	instead	_	_	_	_	-1	_	_	_
9	.	_	_


## Evaluation
To evaluate a tagger output against the gold labels, we include a modified version from universal dependency eval script that can skip unlabeled tokens in the sentence and convert XPOS to either VERB or NON-VERB. Example usage:

Python eval_ud.py gold_file.conll predcited_file.conll

Please note that the evaluation is done against labels in the XPOS column.

## New Results

TODO

## License

## Contact

If you have a technical question regarding the dataset or publication, please
create an issue in this repository.

## Citation
If you use or discuss this dataset in your work, please cite our paper:

```
@InProceedings{NOUNVERB,
  title = {{A Challenge Set and Methods for Noun-Verb Ambiguity}},
  author = {Ali Elkahky, Kellie Webster, Daniel Andor, and Emily Pitler},
  booktitle = {Proc. of EMNLP},
  year = {2018}
}
```
