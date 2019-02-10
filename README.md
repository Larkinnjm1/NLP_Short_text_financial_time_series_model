# NLP_Short_text_financial_time_series_model
Principles of Data Science Natural Language Processing(NLP) project which performs topic modelling on news headlines and correlated these topics to stock price volatility. 

READ ME FILE  

The purpose of this document is to give an outline of each object that is present in the Jupyter note book file associated 
with this file. This file also provides the  outline of what is present in this zip file also:

# General folder directory

Main files:
INM430 Coureswork report.pdf
Final_Python_Notebook.ipynb
Final_Python_Notebook.html 

These files above are the main files with all code utilised for this project being present in both the python and html notebook. The initial Exploratory data analysis and explanation for the modelling workflow is described in these notebooks also. The initial analytical questions and final findings from this project are present in the report 'INM430 NiallLarkinCoureswork report.pdf'. 

Subfolder: Gensim models of LDA, NMF model folders, Results and Datasets

Datasets: Contains WIP and Raw data files used in model processing with LDA and NMP
Gensim models: Contains all models used during the LDA analyis stored as Gensim files
NMF model folders: Contains original python scripts from which the objected code was generated and used in the workbook
Results: Reference results folder outline below
 

#Folder Name: Result
Subfolders:

- LDA topic results - Excel spreadsheets containing the document distributions for each topic model generated by LDA for analysis
- NMF topic modelling tuning parameters - Excel spreadsheets containing the document distributions for each topic model generated by NMF for analysis during tuning stage contains the human qualitative assessment performed for each test also. 
- Plots of graphs  - Contains PNG plots for each graph used in the jupyter notebook 
- Final 200 topics list aggregated -Excel spreadsheets with each spreadsheet containing the final 200 topics for each text corpus analysed from 2009 to 2014 with the aggregated topic name assigned to each subtopic present in a seperate columns also. 



## Time Series Object Function set up 

Two objects where set up for time series data analysis:

- control_chart: The purpose of this object is to delineate between buy,sell and hold signals within the volatility trends for each index. Inputs incude the time series volatility data and the percent threshold for delineation between buy,sell and hold signals. 
- stat_significant: The purpose of this is to return a boolean to confirm whether or not a statistical result is significant or not. 

## OOP Objects for  text analysis:

### Text lemmatisation,tokenisation and stopword removal objects
-  def tokenize: Tokenize single string input and return as list of string tokens
-  def get_lemma: applied to a single string input in tokenized list of strings to lemmatize any string variables
-  def tokenizing: applies def tokenize object program to the entire dataframe
-  def lemmatize:applies def get_lemma program to entire dataframe
-  def prepare_text_for_LDA: applies function objects def tokenizing and def lemmatize to entire topic dataframe in series
-  def get_lda_topics: Generates dataframe out of LDAmodel.get_topic() function
- 

### Data aggregation objects
- def merge_text_rows: Merge rows of text data in time dataframes by date for data aggregation. 
- def assign_BSH_label_to_text assigns Buy, Sell and Hold labels of different days on index to each news headlines 

### NMF model objects and classes:

- def read_docs: Object used in NMF processing to read text files into a list variable while filtering blank outputs in the text file. 
- def read_vocab: Object used in NMF model training to read in the dictionary of unique variables as a list variable. 
- def calculate_PMI: Object used to calculated PMI score for each topic. 
- class SeaNMFL1(object): Class subject which produced the short text NMF model 
- class NMF(object): Class subject which produced regular NMF model 
- def NMF_Pre_process: Object used to perform data pre processing on original file which is read in as a txt file. Please note it does not perform any tokenisation, lemmatisation or stop word removal. this needs to be done prior to performing this activity. 
- def NMF_training_model: Object used to train NMF model which utilises NMF and SeaNMFL1 classes.
- def NMF_Printout_topics: Object used to store and print out topics and PMI score associated with topic from analysis.

# Chi Squared analysis and topic/stock volatility visualisations of data
- def chisq_of_df_cols input for this is the dataframe and specified columns of categorical variables within the dataframe that will be analysed for the Chi squared test using chi2_contigency program from the scipy.stats library 

- general_BSH_ratios: Purpose of this object is to return a dataframe of the different average ratio of buy sell and hold signals for each index for the time frame of the dataframe 

- generate_contigencyplot: Purpose of this object is to return multiple scatter quadrant plots of each indexes 



### Object oriented programs used in topic classification
- def contains_word(s, w): The purpose of this is to place space between strings and to ensure that they match in this fashion so as that only words in a sentence can be compared as opposed to portions of a word being compared to portions of another word i.e. kind being interpreted as matching kindergarden etc as kind can be found in the word kind
- def document_topic_classifier: Document classifier object using Topic list dataframe with PMI scores and headlines text dataframe to classify each document in the headlines dataframe to a specific document. 


