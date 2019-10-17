# PubMed-API-Script
API script with flexible query and simple EDA and analysis

## What's this?
- This is the python script use for get huge PubMed data from NCBI API.  
Document is here. https://www.ncbi.nlm.nih.gov/books/NBK25501/
- You have to read below term before use this script.  
https://www.nlm.nih.gov/databases/download/terms_and_conditions.html

## All code
You can see all code and viz at below link.  
https://nbviewer.jupyter.org/github/tatsuya-takahashi/PubMed-API-Script/blob/master/PubMed.ipynb

## How to use
- You can set your own parameter to fetch PubMed data.
- You can analyze data as you like. This sample indicates simple EDA.

```
# const
BASEURL_INFO = 'https://eutils.ncbi.nlm.nih.gov/entrez/eutils/einfo.fcgi'
BASEURL_SRCH = 'https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esearch.fcgi'
BASEURL_FTCH = 'https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi'

# parameters
SOURCE_DB    = 'pubmed'     #pubmed, nuccore, nucest, nucgss, popset, protein
TERM         = 'cancer'     # Entrez text query. 
DATE_TYPE    = 'pdat'       # Type of date used to limit a search. The allowed values vary between Entrez databases, but common values are 'mdat' (modification date), 'pdat' (publication date) and 'edat' (Entrez date). Generally an Entrez database will have only two allowed values for datetype.
MIN_DATE     = '2018/01/01' # yyyy/mm/dd
MAX_DATE     = '2019/12/31' # yyyy/mm/dd
SEP          = '|'
BATCH_NUM    = 1000

# seed
RANDOM_STATE = 42
np.random.seed(RANDOM_STATE)
```

## What's output?
### pubmed_article.csv
PMID  
JournalTitle  
Title  
doi  
Abstract  
Language  
Year_A  
Month_A  
Day_A  
Year_PM  
Month_PM  
Day_PM  
Status  
MeSH  
MeSH_UI
KeywordI  
Keyword


### pubmed_author.csv
authorId  
PMID  
name  
identifier  
identifierSource

### pubmed_affiliation.csv
authorId  
affiliation


