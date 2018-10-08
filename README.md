# Noun Verb Dataset
This dataset contains over 30,000 naturally-occurring English sentences that include non-trivial noun-verb ambiguity.

## Description

The dataset contains sentences in CoNLL format. Each sentence has single token annotated as either VERB or NON-VERB. The data sources are Wikipedia, Wikihow and Search Ads. Before each sentence there is a comment line with the source of the sentence. In case of Wikipedia and Wikihow, the url of the source page for the sentence is included.

The annotations is done through crowdsourcing as described in the paper in the citation section. Note that some of the examples are filtered from the dataset used in the paper. The results for all the used models in the paper is recomputed for the filtered dataset the New Results section.

The dataset is splitted into Train/Dev/Test sections. For Dev and Test sections the annotations included either VERB or NON-VERB in XPOS, UPOS  and FEATS columns. For the Train section, XPOS and UPOS columns are replaced with fine POS tag obtained by running automatic tagger and select the top tag that matched the crowdcompute label.

Example of a training sentence is shown below:

```
# https://www.wikihow.com/Not-Get-Bored-on-a-Long-Car-Ride
1	License	_	NN	NN	POS=NON-VERB|fPOS=NON-VERB	-1	_	_	_  
2	plates	_	_	_	_	-1	_	_	_  
3	of	_	_	_	_	-1	_	_	_  
4	cars	_	_	_	_	-1	_	_	_  
5	from	_	_	_	_	-1	_	_	_  
6	your	_	_	_	_	-1	_	_	_  
7	area	_	_	_	_	-1	_	_	_  
8	or	_	_	_	_	-1	_	_	_  
9	your	_	_	_	_	-1	_	_	_  
10	destination	_	_	_	_	-1	_	_	_  
11	.	_	_	_	_	-1	_	_	_  

```

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
