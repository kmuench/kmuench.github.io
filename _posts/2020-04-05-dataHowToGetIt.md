---
layout: post
title: Data - where is it, and how do I get it?
---
<p align="center">
  <img width="460" height="300" src="https://c.pxhere.com/images/84/b7/2d8b54b996763aa0aad1d553513f-1442539.jpg!d">
</p>

I'm afraid there's no way around it: in order to do data science, you're going to need data.

I notice that data import is rarely the focus of tutorials for beginners. That is perhaps unsurprising: no one’s entering the field for the non-stop thrill-ride of replacing blank cells with NaNs, or the glorious mysteries of the [SRA format](https://www.ncbi.nlm.nih.gov/sra/docs/submitformats/).

Yet, easeful data acquisition is fundamental to the rest of the learning process. Someone limited to studying only data that's easy to import, not the data they care about, will have a much harder time overcoming a lack of motivation in the eleventh hour of googling error messages. Plus, a new coder who gets frustrated with the data download process can quickly lose faith in their abilities, and quit the process before they’ve even begun.

There are two challenges, then: how do you find data that you care about? And how can you get that data into R or Python as quickly and as neatly as possible?

Here, I’ve assembled some public datasets and resources to help lower these hurdles in your first analysis projects. I’ll devote a separate section to acquiring genomics data, since that was a particular thorn in my side when I was getting started.

Click the corresponding link if you’re looking for...

- <a href="#generalTabularData">General Tabular Data</a>
  - <a href = "#smallAmountEasyPracData">A small amount of easy-to-load of practice data</a>
  - <a href = "#searchEngineNiche">Search engines for to suit your niche tastes</a>
- <a href="#genomicData">Genomic Data</a>
  - <a href = "#functionalGEO">Functional genomics data from GEO</a>
    - <a href = "#curatedBulk">Curated bulk RNA-Seq data</a>
    - <a href = "#curatedSC">Curated scRNA-Seq data</a>
  - <a href = "#scNotGEO">Single Cell RNA-Seq Data that isn’t from GEO</a>
  - <a href = "#variant">Genome variant data, and other sites of note</a>

Many of the methods below can be imported with ease into R or Python using existing packages. However, every now and again you’ll find a cool dataset that you’ll need to load yourself. In that case, check out the section on <a href="#extra tools">extra tools for downloading and importing data</a>.

I recommend <b>making a note of when and how you download data</b>, since some datasets can be updated (or change location) from year to year. That way, others who want to replicate your analysis can use the same starting point.

You don’t need the world’s biggest or fanciest dataset to do something interesting (a friend of mine once practiced R by analyzing the astrological signs of various serial killers). The important thing is that you find a practice dataset that sparks your curiosity, and lets you the practice the skill you'd like to learn.

Remember, if it seems overwhelming, try breaking the problem down. If the data is on a website - how can you get it on your computer? If the data is on your computer - how do you import it into Python? If some form of the data in in Python - what does it need to look like in order to make a scatterplot with it? 

Obtaining and loading data can be a surprisingly tricky part of the process, and it's natural to stumble on this step. Make sure you reward yourself when you get everything in place and can finally get to the good stuff!

---------

<a name="generalTabularData"></a>
# General Tabular Data
<a name="smallAmountEasyPracData"></a>
## A small amount of easy-to-load of practice data:

R users should consider [the R datasets package](https://stat.ethz.ch/R-manual/R-devel/library/datasets/html/00Index.html).

R automatically loads this built-in library of datasets when it starts, so you’ll barely have to list a finger to use them. You can see the full list of options by typing ```data()``` into command line. Plus, since they’re already cleaned, these data are truly the lowest barrier to entry an R user can find.
To load the dataset called “iris”, simply type:

{% highlight R %}
data(iris)
{% endhighlight %}

Many of these datasets have names that read like the titles of modern art pieces: “The World’s Telephones” (```data(WorldPhones)```), “Flow of the River Nile” (```data(Nile)```), “Occupational Status of Fathers and their Sons” (```data(occupationalStatus)```). 

Easy doesn’t have to mean boring - there are tables to suit the tastes of a variety of nerds, from those in biotech ("(O)esophageal cancer in Ille-et-Vilaine, France", ```data(esoph)``` ) to the history of finance (“Daily Closing Prices of Major European Stock Indices, 1991-1998” ( ```data(EuStockMarkets)``` ).

However, I personally have found that I usually need more context to get excited about studying, say, “Body Temperature Series of Two Beavers” ( ```data(beavers)``` ). Plus, the datasets tend to be on the smaller side. However, if you just need something easy to load so you can get coding as soon as possible, these datasets are a great choice!

Python users might have to do slightly more work, but they have several options:
- [PyDataset](https://github.com/iamaziz/PyDataset) to access over 700 sample datasets.
- [Seaborn](https://seaborn.pydata.org/generated/seaborn.load_dataset.html) and [scikit-learn](https://scikit-learn.org/stable/datasets/index.html) both come with example datasets preloaded.
- If you've just gotta have those R datasets, consider using the [rpy2](https://pypi.org/project/rpy2/) package. It allows you to use R within Python, including loading the datasets above, described [here](https://stackoverflow.com/questions/16579407/are-there-any-example-data-sets-for-python).

<a name="searchEngineNiche"></a>
## Search engines for to suit your niche tastes
These datasets might require a little extra elbow grease until you have nice, pretty, completely-filled-out, standardized-entry tables to explore. That said, your imagination will have much more room for exploration. 

- [Data.gov](https://www.data.gov/). What in the United States do you care about? Health? Climate? Ecosystems? Education? You can find data related to all of the above here. You’ll have to do some digging to get to the actual data itself, but you should find a variety of interesting reports, from [heart disease deaths in Oklahoma](https://catalog.data.gov/dataset/heart-disease-deaths-95993) to [beer statistics](https://www.ttb.gov/beer/statistics). They offer civic-minded data [challenges](https://www.data.gov/climate/climate-challenges), as well.
- An excellent list of lists of free datasets lives [on this website](https://r-dir.com/reference/datasets.html).
There are several enticing, specialized databases in here, such as a [collection of social network data](http://snap.stanford.edu/data/), or [global development data](https://data.worldbank.org/)
- [Google’s Dataset search](https://datasetsearch.research.google.com/). Like Google, but for datasets! Again, be aware that not all of these datasets are going to be nicely formatted, or high-quality
- [Kaggle’s datasets](https://www.kaggle.com/datasets). You don’t need to be in a kaggle competition to download a cool dataset and play with it.
- [Harvard Dataverse](https://dataverse.harvard.edu). Another dataset search. Quarantining scientists might check out their special section devoted to [COVID-19 data](https://dataverse.harvard.edu/dataverse/harvard?q=covid-19).  There are plenty of palette-cleansingly specific datasets derived from research groups as well - consider, for example, [“Survey Data on Memorable Experiences with Sad Music”](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/GLSIXB)


---------



<a name="genomicData"></a>
# Genomic Data

Remember, any research supported with NIH funding [must make its sequencing data publically available by publication time](https://grants.nih.gov/grants/policy/data_sharing/data_sharing_guidance.htm#time). The authors usually indicate where the data repositories are located (or even provide the GEO database ID) in the Methods section or somewhere in Supplementary Files.


<a name="functionalGEO"></a>
## Functional genomics data from GEO
Many, many of the aforementioned NIH-supported researchers upload their data here. Some papers will even provide an accession number (e.g., "GSE40548") rather than a URL for the data. 

GEO's greatest flaw, unfortunately, is its website design and misleading terminology. My suggestion: don’t worry about figuring out trying to download data directly from the GEO website, or figuring out what a MINiML file is.

If you’re just looking for some count tables to play with and don’t need the raw .fastqs, check out [GEOquery](https://bioconductor.org/packages/release/bioc/html/GEOquery.html) for R (nice tutorial [here](https://www.bioconductor.org/packages/release/bioc/vignettes/GEOquery/inst/doc/GEOquery.html) and [here](https://warwick.ac.uk/fac/sci/moac/people/students/peter_cock/r/geo/)), and [GEOparse](https://pypi.org/project/GEOparse/) (tutorial [here](https://www.biostars.org/p/400047/)) for Python.

Alternatively, if you’d like to download the raw data, you can consider using wget (described <a href="#extra tools">below</a>) to download data from the [GEO FTP site](https://ftp.ncbi.nlm.nih.gov/geo/) download the raw data. There are some handy tutorials on how to find the FTP site corresponding to your data of interest, including [this one](https://www.imm.ox.ac.uk/files/ccb/downloading_fastq_geo). You’ll also need to uncompress the data using the SRA Toolkit, tutorial [here](http://homer.ucsd.edu/homer/basicTutorial/retrieveFiles.html).

Several groups have curated some choice lists of datasets, either to highlight great datasets or to provide standard preprocessing to support meta-analysis:
<a name="curatedBulk"></a>
### Curated bulk RNA-Seq data
- [This website](http://www.cs.cmu.edu/~ckingsf/sharq/index.html) is a cleaned-up version of the GEO search interface for transcriptomic data through 2014, and can help you find GEO accession numbers.
- [DEE2](http://dee2.io/), [RECOUNT2](https://jhubiostatistics.shinyapps.io/recount/), and [ARCHS4](https://amp.pharm.mssm.edu/archs4/) has uniformly processed bulk RNA-Seq data from GEO
<a name="curatedSC"></a>.

### Curated scRNA-Seq data
- [The Hemberg lab](https://hemberg-lab.github.io/scRNA.seq.datasets/) has thoughtfully curated the accession numbers for many datasets they use profiling various tissues from human and mouse.
- [This R package](http://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html) provides single cell RNA-Seq datasets that can be loaded like the ```data()``` packages before, with a focus on brain tissue.

<a name="scNotGEO"></a>
## Single Cell RNA-Seq Data that isn’t from GEO
- The [European Nucleotide Archive](https://www.ebi.ac.uk/ena) is GEO's European sibling - another popular, well-maintained data repository, with its own downloading methods described [here](https://www.ebi.ac.uk/ena/browse/read-download).
- [The Broad’s Single Cell Portal](https://github.com/broadinstitute/single_cell_portal) is increasingly popular. It allows you to download both fastq and [expression files](https://github.com/broadinstitute/single_cell_portal/wiki/Expression-File).
- [10x Genomics scRNA-Seq datasets](https://support.10xgenomics.com/single-cell-gene-expression/datasets) are used as benchmarking data for many scRNA-Seq tools today.

<a name="variant"></a>
## Genome variant data, and other sites of note
- [GTEx](https://www.gtexportal.org/home/)
- [GDC Cancer Portal](https://portal.gdc.cancer.gov/) - 2.5 petabytes of eQTL data related to cancer!
- [dbGAP](https://www.ncbi.nlm.nih.gov/gap/)
- Anshul Kundaje maintains an impressive list of a [variety of genomic datasets](https://sites.google.com/site/anshulkundaje/idatasets).

A note for R users: some individuals will upload their data as a [library](https://www.bioconductor.org/packages/release/data/experiment/) that can be installed and imported, like the ```data()``` packages discussed before. You can nab a copy of the [10x PBMC data](https://www.bioconductor.org/packages/release/data/experiment/html/TENxPBMCData.html) this way, although, of course, it’s safer to download the data yourself directly from a repository in case small errors or discrepanices were introduced during library creation.


---------


<a name="extra tools"></a>
# Extra tools for downloading and importing data

## Importing CSV files
Hopefully you’re lucky enough that your data of interest is stored as a CSV (Comma Separated Value) file! That’s a regular plain text file that uses a convention for storing tabular data. In CSV files, some kind of delimiter (a comma, or sometimes a space, or a tab, or a slash) is used indicate what different columns are. CSV files are straightforward to import in [Python](https://realpython.com/python-csv/) and [R](http://www.r-tutor.com/r-introduction/data-frame/data-import).

By the way, you can [export Excel files as CSV files](https://www.ablebits.com/office-addins-blog/2014/04/24/convert-excel-csv/) if you’d like to have a smooth way of importing your Excel projects into R and the .xlsx file type is giving you trouble.


## Data from an FTP Site
Data is often hosted on an FTP site. FTP means File Transfer Protocol - you can think of it as the language that computers use to talk to one another and [pass files back and forth](https://www.wired.com/2010/02/ftp_for_beginners/). An FTP site is a computer that allows visitors to download data from it using the FTP protocol via the internet. You can usually see one [using your browser](https://ftp.ncbi.nlm.nih.gov/) (or even click links to download files directly from it).

There are many ways to download data from an FTP site, but using wget has stood the test of time (truly - it was introduced in 1996).

wget is a command line application - that means you use it by typing a command into command line instead of double-clicking an icon on your computer. If you use Linux, wget is already installed; Mac or PC users have to do a little extra to install it. Howtogeek has a nice description of how to use it [here](https://www.howtogeek.com/281663/how-to-use-wget-the-ultimate-command-line-downloading-tool/). 

For a Mac user, once wget is installed, the process is pretty easy. Open the Terminal application on your computer, and change your directory to your desktop by typing:

{% highlight bash %}
cd ~/Desktop
{% endhighlight %}

“cd” means “change directory”; the part after that is the “path” to the folder on your computer where you want the data to be downloaded. I hate accidentally filling my desktop with random FTP files, so I usually make a folder and go into that directory by typing:

{% highlight bash %}
mkdir my_ftp_download
cd ~/Desktop/my_ftp_download
{% endhighlight %}

To download a single file:
{% highlight bash %}
wget ftp://url/to/FTP/site/myFile.zip
{% endhighlight %}

To download a whole folder (directory) of files:
{% highlight bash %}
wget -r ftp://url/to/FTP/site/
{% endhighlight %}


## Data in the JSON formet
Javascript Open Notation - another file format in which data can be stored. It shouldn’t be too hard with the correct package to load JSON into [Python](https://linuxconfig.org/how-to-parse-data-from-json-into-python) or into [R](https://stackoverflow.com/questions/2617600/importing-data-from-a-json-file-into-r).

## Extracting data from a PDF
Occasionally, you’ll discover that your data of interest is embedded into a PDF document (looking at you, [U.S. beer statistics](https://www.ttb.gov/beer/statistics)). Please, don’t type every number into an Excel sheet by hand - there is a better, faster way! You’ll want to investigate tools for scraping data from PDFs - [Tabula](https://tabula.technology/) appears popular for this purpose.


