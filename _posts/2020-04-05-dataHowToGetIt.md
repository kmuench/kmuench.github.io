---
layout: post
title: Data: Where is it, and how do I get it?
---
There is a single, inescapable truth that governs the life of every analyst: in order to do data science, you need data.

I notice that data import is rarely given more than a paragraph of thought in tutorials for beginners. That is perhaps unsurprising: no one’s entering the field for the non-stop thrill-ride of replacing blanks with NaNs, or the glorious mysteries of the [SRA format](https://www.ncbi.nlm.nih.gov/sra/docs/submitformats/).

Yet, easeful data acquisition is fundamental to the rest of the learning process. A new coder who gets frustrated with the data download process can quickly lose faith in their abilities, and quit the process before they’ve even begun. Also - this is very important - it turns out that you absorb the material much more deeply when you’re actually curious about the analysis you’re doing.

There are two challenges, then: how do you find data that you care about? And how can you get it into R or Python as quickly and as neatly as possible?

Here, I’ve assembled some public datasets and resources to help lower the first hurdle in your analysis projects. I’ve ordered them roughly from the cleanest and easiest datasets to procure, to the potentially more exciting (albeit much less curated) datasets. I’ll also devote a separate section to genomics data, since I've spent quite a bit of time searching around for those. 

Click the corresponding link if you’re looking for...

- <a href="#generalTabularData">General Tabular Data</a>
  - <a href = "#smallAmountEasyPracData">A small amount of easy-to-load of practice data</a>
  - <a href = "#biggerDataCivic">Bigger data for civic-minded people</a>
  - <a href = "#searchEngineNiche">Search engines for to suit your niche tastes</a>
- <a href="#genomicData">Genomic Data</a>
  - <a href = "#functionalGEO">Functional genomics data from GEO</a>
    - <a href = "#curatedBulk">Curated bulk RNA-Seq data</a>
    - <a href = "#curatedSC">Curated scRNA-Seq data</a>
  - <a href = "#scNotGEO">Single Cell RNA-Seq Data that isn’t from GEO</a>
  - <a href = "#variant">Genome variant data, and other sites of note</a>
  
  

Many of the methods below can be imported with ease into R or Python using existing packages. However, every now and again you’ll find a cool dataset that you’ll need to load yourself. In that case, check out the section on <a href="#extra tools">extra tools for importing data</a>.

I recommend making a note of when and where you download data, since some datasets can be updated (or change location) from year to year. If someone wants to repeat your analysis, they’ll have more faith in your results if they can replicate your output from the same starting point.

You don’t need the world’s biggest or fanciest dataset to do something interesting (a friend of mine once practiced R by analyzing the astrological sign of various serial killers). The important thing is that you find a practice dataset that sparks your curiosity, and teaches you the skills you'd like to learn.

Remember, if it seems overwhelming - break the problem down. The data is on a website - how can you put it on your computer? The data is on your computer - how do you import it into R? Some form of the data in in R - what does it need to look like to make a scatterplot with it? 

Obtaining and loading data can be a surprisingly tricky part of the process - feel good when you finally begin that journey of a thousand miles with this essential first step.



<a name="generalTabularData"></a>
# General Tabular Data
<a name="smallAmountEasyPracData"></a>
## A small amount of easy-to-load of practice data:

- For R users, [the R datasets package](https://stat.ethz.ch/R-manual/R-devel/library/datasets/html/00Index.html).

R automatically loads this built-in library of datasets when it starts, so you’ll barely have to list a finger to use them. You can see the full list of options by typing data() into command line. Plus, since they’re already cleaned, these truly present the lowest barrier to practice an R practitioner can find.
To load the dataset called “iris”, simply type:
data(iris)

Many have names that read like the titles of modern art pieces: “The World’s Telephones” (data(WorldPhones)), “Flow of the River Nile” (data(Nile)), “Occupational Status of Fathers and their Sons” (occupationalStatus). Easy doesn’t mean boring - there are tables to suit the tastes of a variety of nerds, from those in biotech (“Daily Closing Prices of Major European Stock Indices, 1991-1998”, data(esoph) ) to the history of finance (“Daily Closing Prices of Major European Stock Indices, 1991-1998” ( data(EuStockMarkets) ).

I personally have found that, without context, I have a hard time getting excited about, say, “Body Temperature Series of Two Beavers” ( data(beavers) ). Plus, the datasets tend to be on the smaller side.

Python users might have to do a little additional work, but have several options:
- [PyDataset](https://github.com/iamaziz/PyDataset) to access over 700 sample datasets
- [Seaborn](https://seaborn.pydata.org/generated/seaborn.load_dataset.html) and [Scikit-learn](https://scikit-learn.org/stable/datasets/index.html) both come with example datasets preloaded
- If you've just gotta have those R datasets, consider using the [rpy2](https://pypi.org/project/rpy2/) package. It allows you to use R within Python, including loading the datasets above - described (here)(https://stackoverflow.com/questions/16579407/are-there-any-example-data-sets-for-python)

<a name="biggerDataCivic"></a>
## Bigger data for civic-minded people
[Data.gov](https://www.data.gov/)
What in the United States do you care about? Health? Climate? Ecosystems? Education? You can find data related to all of the above here. You’ll have to do some digging to get to the actual data itself, but you should be able to find .csv files, for example, [beer statistics](https://www.ttb.gov/beer/statistics).

<a name="searchEngineNiche"></a>
## Search engines for to suit your niche tastes
These datasets might require a little extra elbow grease until you have nice, pretty, completely-filled-out, standardized-entry tables to explore. That said, you might have a better chance of discovering a question that sparks your imagination. 
[Everybody] [An excellent list of lists of free datasets] (https://r-dir.com/reference/datasets.html)
There are several interesting specialized databases in here, such as a [collection of social network data](http://snap.stanford.edu/data/), [global development data](https://data.worldbank.org/)
[Google’s Dataset search](https://datasetsearch.research.google.com/)
Like Google, but for datasets! Again, be aware that not all of these datasets are going to be nicely formatted, or high-quality
[Kaggle’s datasets](https://www.kaggle.com/datasets) 
You don’t need to be in a kaggle competition to download a cool dataset and play with it.
[Harvard Dataverse](https://dataverse.harvard.edu)
Another dataset search. This one has taken the time to make a section for COVID-19 data, for those quarantining data scientists in April 2020 (https://dataverse.harvard.edu/dataverse/harvard?q=covid-19). 
There are plenty of  palette cleansers derived from research groups as well - perhaps try “Survey Data on Memorable Experiences with Sad Music” (https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/GLSIXB)


<a name="genomicData"></a>
# Genomic DATA

Remember, any research supported with NIH funding [must make its sequencing data publically available by publication time](https://grants.nih.gov/grants/policy/data_sharing/data_sharing_guidance.htm#time). The authors usually indicate where the data repositories are located (or even provide the GEO database ID) in the Methods section or somewhere in Supplementary Files.


<a name="functionalGEO"></a>
## Functional genomics data from GEO
So many of the aforementioned NIH-supported researchers upload their data here that some papers will refer readers to accession numbers rather than URLs to the data. Its greatest flaw is how difficult the interface is to interpret. 

My suggestion: don’t worry about figuring out trying to download data directly from the GEO website, or figuring out what a MINIML file is. If you’d like to download the raw data, you can consider using wget (described below) to download data from the [GEO FTP site](https://ftp.ncbi.nlm.nih.gov/geo/) download the raw data. There are some handy tutorials on how to find the FTP site corresponding to your data of interest, including [this one](https://www.imm.ox.ac.uk/files/ccb/downloading_fastq_geo). You’ll also need to uncompress the data using the SRA Toolkit, tutorial [here](http://homer.ucsd.edu/homer/basicTutorial/retrieveFiles.html).

However, if you’re just looking for some count tables to play with and don’t need the .fastqs, check out [GEOquery](https://bioconductor.org/packages/release/bioc/html/GEOquery.html) for R (nice tutorial [here] (https://www.bioconductor.org/packages/release/bioc/vignettes/GEOquery/inst/doc/GEOquery.html) and [here](https://warwick.ac.uk/fac/sci/moac/people/students/peter_cock/r/geo/)), and GEOparse (https://pypi.org/project/GEOparse/) (tutorial [here](https://www.biostars.org/p/400047/) for Python.

Several groups have curated some choice lists of data, either to highlight great datasets or to standardize processing steps:
<a name="curatedBulk"></a>
### Curated bulk RNA-Seq data
[This website](http://www.cs.cmu.edu/~ckingsf/sharq/index.html) is a cleaned-up version of the GEO search interface for transcriptomic data through 2014, and can help you find GEO accession numbers.
[DEE2] (http://dee2.io/), [RECOUNT2](https://jhubiostatistics.shinyapps.io/recount/), and [ARCHS4](https://amp.pharm.mssm.edu/archs4/) has uniformly processed bulk RNA-Seq data from GEO
<a name="curatedSC"></a>
### Curated scRNA-Seq data
[The Hemberg lab](https://hemberg-lab.github.io/scRNA.seq.datasets/) has thoughtfully curated the accession numbers for many datasets they use profiling variosu tissues from human and mouse:
[This R package](http://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html) provides single cell RNA-Seq datasets that can be loaded like the data() packages before, with a focus on brain

<div class="message">
Note for R users: some individuals will upload their data as a [library](https://www.bioconductor.org/packages/release/data/experiment/) that can be installed and imported, like the data() packages discussed before. You can nab a copy of the [10x PBMC data](https://www.bioconductor.org/packages/release/data/experiment/html/TENxPBMCData.html) this way, although, of course, it’s always “safer” to get the data directly from the source in case the library creation accidentally introduced small discrepancies.
  </div>

<a name="scNotGEO"></a>
## Single Cell RNA-Seq Data that isn’t from GEO
- The [European Nucleotide Archive](https://www.ebi.ac.uk/ena) is another popular, well-maintained, heavy-hitting database of genomic data, with its own downloading methods described [here](https://www.ebi.ac.uk/ena/browse/read-download).
- [The Broad’s Single Cell Portal](https://github.com/broadinstitute/single_cell_portal) gives you both fastq() and [expression files](https://github.com/broadinstitute/single_cell_portal/wiki/Expression-File).
- [10x Genomics scRNA-Seq datasets](https://support.10xgenomics.com/single-cell-gene-expression/datasets) - used as benchmarking data for many scRNA-Seq tools today

<a name="variant"></a>
## Genome variant data, and other sites of note
- [GTEx](https://www.gtexportal.org/home/)
- [GDC Cancer Portal](https://portal.gdc.cancer.gov/): 2.5 petabytes of eQTL data related to cancer
- [dbGAP](https://www.ncbi.nlm.nih.gov/gap/): (databases looking at genotype-phenotype association)
- Anshul Kundaje maintains an impressive list of a [variety of genomic datasets](https://sites.google.com/site/anshulkundaje/idatasets)

<a name="extra tools"></a>
# Extra tools for Downloading Data Data

## Importing CSV files
Hopefully you’re lucky enough that your data is stored as a CSV (Comma Separated Value) file! That’s just a way of storing tabular data in a ASCII format, with some kind of delimiter (a comma, or sometimes a space, or a tab, or a slash) to indicate what different columns are. These are straightforward to import in [Python](https://realpython.com/python-csv/) or [R](http://www.r-tutor.com/r-introduction/data-frame/data-import).

By the way, you can [export Excel files as .CSV files](https://www.ablebits.com/office-addins-blog/2014/04/24/convert-excel-csv/) if you’d like to have a smooth way of importing your Excel projects into R and the .xlsx file type is giving you trouble.


## Data from an FTP Site
Data is often hosted on an FTP site. FTP means File Transfer Protocol, and you can think of it as the language that computers use to talk to one another and [pass files back and forth](https://www.wired.com/2010/02/ftp_for_beginners/). An FTP site is a computer that allows visitors to download data from it using the FTP protocol via the internet. You can usually see one [using your browser](https://ftp.ncbi.nlm.nih.gov/) (or even click to download files directly from it).

There are many ways to download data from an FTP site, but using wget has stood the test of time (truly - it was introduced in 1996).

Wget is a command line application - that means you use it by typing a command into command line instead of double-clicking an icon on your computer. If you use Linux, wget is already installed; Mac or PC users have to do a little extra to install it. Howtogeek has a nice description of how to use it [here](https://www.howtogeek.com/281663/how-to-use-wget-the-ultimate-command-line-downloading-tool/). 

For a Mac user, once wget is installed, the process is pretty easy. Open the Terminal application on your computer, and change your directory to your desktop by typing:

{% highlight bash %}
// Example can be run directly in your JavaScript console

// Create a function that takes two arguments and returns the sum of those arguments
var adder = new Function("a", "b", "return a + b");

{% endhighlight %}

<pre>
  <code class="bash">
    puts "Cd ~/Desktop"
  </code>
</pre>


“cd” means “change directory”; the part after that is the “path” to the folder on your computer where you want the data to be downloaded. I hate accidentally filling my desktop with random FTP files, so I usually make a folder and go into that directory by typing:

Mkdir my_ftp_download
Cd ~/Desktop/my_ftp_download

To download a single file:
Wget ftp://url/to/FTP/site/myFile.zip

To download a whole folder (directory) of files:
Wget -r ftp://url/to/FTP/site/


## Data in the JSON formet
Javascript Open Notation - another file format in which data can be stored. It shouldn’t be too hard with the correct package to load JSON into [Python](https://linuxconfig.org/how-to-parse-data-from-json-into-python) or into [R](https://stackoverflow.com/questions/2617600/importing-data-from-a-json-file-into-r).

## Extracting data from a PDF
Occasionally, you’ll discover that your data of interest is embedded into a PDF document (looking at you, [U.S. beer statistics](https://www.ttb.gov/beer/statistics)). Please, don’t type every number into an Excel sheet by hand - there is a better, more automated, faster way! You’ll want to investigate tools for scraping data from PDFs - Tabula (https://tabula.technology/) appears popular for this purpose.


