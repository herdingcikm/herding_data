# herding_data
Data for "Driving the Herd: Search Engines as Content Influencers" paper

# Dataset description
The collection contains 2250 documents, 
30 initial relevant documents (round 0) - located in initial_documents.trectext file. 
2100 documents (rounds 1-5) created by competitors.
120 documents are the example documents that were manually promoted in the herding method experiments.


This dataset is divided w.r.t. the different experiments for content effect, described in the paper.


Format: trectext.
DOCNO Format: ROUND-<round_number>-<query_id>-<author_id>


# Relevance Judgments (qrels):
All documents in the collection were judged for relevance. 
Annotators were presented with both the title and the description of each TREC topic
and were asked to classify a document as relevant if it satisfies the information need stated in the description.

A document judged relevant by less than three annotators was labeled as non-relevant (0).
Documents judged relevant by at least three, four or five annotators 
were labeled as marginally relevant (1), fairly relevant (2) and highly relevant (3), respectively.
For each experiment the relevance judgment file has ".rel" suffix.
# Quality judgements:
All documents in the collection where judged for quality by five annotators. 
Annotators were presented with the text of the document and were asked to classify the docuemnt as:
(1) Valid, (2) Keyword-stuffed, (3) Spam.

A document is deemed as keyword-stuffed if it contained excessive repetition of words 
which seemed unnatural or artificially introduced.

A document is considered as spam if its content could not possibly satisfy any information need.

If a document is not spam or keywordstuffed, it is considered as valid.
Documents judged valid by at least three, four or five annotators 
were labeled as marginally high-quality (1), fairly high-quality (2) and highly high-quality (3), respectively.
For each experiment the quality judgment file has ".ks" suffix.

# Queries
We used 30 of ClueWeb09 queries which can be downloded here: http://trec.nist.gov/data/webmain.html. 

# Example documents
In the herding method experiment for each query and effect an exapmle document, manifesting the desired content effect, was manually promoted to 1'st place.
For each effect the example documents are located at "herding_<content-effect>_example_documents.trectext" file.
The format of document names is:
DOCNO Format: ROUND-00-<query_id>-EXAMPLEDOC


# Subtopic effect experiment
This content effect was tested both in terms of herding and biasing approaches. 
For each query 2 different subtopics were tested. The subtopics were taken from ClueWeb09 subtopics list.
The mapping between qid and the subtopic number which was promoted (and the actual information need manifested by the subtopic) is located at <herding/biasing>_subtopics_map.txt files (in each relevant directory separetly).

We include relevance judgemnts for each document (competing for a rankings w.r.t a query) w.r.t. to both subtopics promoted for the query. Please note that each document was tested w.r.t. a single subtopic (can be induced by the mapping file) during the experiment. The judgments are for both subtopics for analysis porpuses only.
Relevance judgments w.r.t. subtopics name is "<biasing/herding>_relevance_to_subptopic.rel".

The qrels format is: "\<qid\> \<subtopic-number\> \<docno\> \<rel-level\>".



# Directories
## Herding ##
###  Document_length_effect ###
The data contained in this directory is related to the documents created in the document length effect experiment (herding method).

### Non_relevance_effect ### 
The data contained in this directory is related to the documents created in the non-relevance effect experiment (herding method).

### Query_terms_effect ### 
The data contained in this directory is related to the documents created in the query terms effect experiment (herding method).

### Subtopic_effect ### 
The data contained in this directory is related to the documents created in the subtopic effect experiment (herding method).

## Biasing ##
### Subtopic_effect ###
The data contained in this directory is related to the documents created in the subtopic effect experiment (biasing method).


## Control ##
The data contained in this directory is related to the documents created in the control group. That is, no expore of any kind of manipulation for this group.

## Dummies ##
The data contained in this directory is related to the documents taken from Raifer et al '17 dataset. Dummies with docnos "DUMMY_{0,1}" where shared over all groups. 

Control group and biasing groups where filled with DUMMY_2 dummies (in the docno) as well.
