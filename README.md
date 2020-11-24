TLDR;
* Use GitHub for code, Google Drive (VU account) [*shared
  drive*](https://drive.google.com/drive/u/2/folders/0ABiXQV53pij4Uk9PVA) and Zenodo as much as
  possible.
* Working with sensitive data? Liaise with the data owner for solutions. Make sure that data can
  be stored for 10 year.

# About
This repository contains best practices, pointers and tips for data management within the QDA
group.

The goal of this document is to help making choices regarding data processing for a typical QDA
project. We identify different project artifacts, artifact phases and external requirements and
assess different storage solutions based on this.

# Project Artifacts
Most QDA project consist of two types of artifacts:
 1. Data.  
    This can be both `raw` data, i.e. in the form it was collected in, as processed data.
 2. Code.  
    For a particular project, code can be used to generate data (simulators, live applications),
    to process data (generate insights, train models, etc.) or independently from any data (e.g. a
    package).

# Artifact Phases
Typically, a research project transitions through various phases.
![artifact
phases](https://raw.githubusercontent.com/VU-QDA/data-management/main/artifacts/research-cycle/research-cycle.png?token=AAW5FRAUA47LQ4WKVKWHVHS7VFVJO)

The most simple way to think of phases is during and after the project. During the project we want
the artifact to be private, easily available and changeable. After the end of the project, we
typically want the artifacts to remain available.

In many cases, we will want to make artifacts publicly available. Although projects rarely last
long, artifacts may be repurposed and can cycle in and out of these phases.

For data management purposes, the most interesting phases are:
 * the active phase: the version is not final. We want easy access for processing and updating the
   artifact. 
 * the final phase: the artifact is 

Datasets or codebases are typically versioned. We think of different versions being in different
phases. For example, we may publish a study on risks of cyclists without a helmet with a
particular version of a dataset on biking accidents while collecting additional data for later
studies and data releases.


## Active Artifacts
Code and data can be hosted on GitHub. Data may be too large or change too quickly for storage on
GitHub. In this case
[SurfDrive](https://www.surf.nl/en/surfdrive-store-and-share-your-files-securely-in-the-cloud) can
be used.

## Final Artifacts
Research artifacts need to be stored for reproduction purposes. But publishing your research
artifacts may have direct benefits. For example, other authors may be more prone to include your
approach in a benchmark if you have published it. Storing data in the right way is part of good
scholarship and part of many guidelines on scientific integrity. VSNU recommends storing data for
at least [ten
years](https://www.vsnu.nl/files/documenten/Nederlandse%20gedragscode%20wetenschappelijke%20integriteit%202018.pdf).

You can publish your code and data using [Zenodo](https://zenodo.org/). Zenodo is an EU-backed
project aimed at making sharing, inspecting and repurposing research data more ease. Each Zenodo
release gets listed so that is easily findable. Additionally, it gets assigned a
[DOI](http://www.doi.org/) and other meta-data. This allows for you (and others) to cite the resource.
 
Code can also be published in a [GitHub
release](https://github.blog/2013-07-02-release-your-software/).

Data can be stored on Google Drive. All VU accounts have a storage of 1TB and we have a [shared
drive](https://drive.google.com/drive/u/2/folders/0ABiXQV53pij4Uk9PVA) with our group so that
others can access your data. Make sure to share your data with a tenured staff member such as Mark
so that is not deleted when you lose your VU account.

In case you are not allowed to publish your data (see `External Requirements'), you will still
need to store it to ensure reproducibility. You will need to work with the data owner to see how
this can be made possible. VU offers two privacy-sensitive storage solutions:
* [Research
  Drive](https://vunet.login.vu.nl/services/pages/practicalinformation.aspx?cid=tcm%3a165-413728-16)
  for GDPR-data and relatively collaboration
* DarkStor (€3.5 / GB / Year, see VUnet) for access-by-request only long-term storage.

# External Requirements
External requirements are demands from data owners. Typically, medical data comes with strict
controls on storage and processing. These requirements are in a sense `external'.

Since these requirements are not known and differ per project (partner), we only provide best
practices here.

In any case, make sure to make agreements on data retention (long-term storage). If data cannot
leave the data owners' premises, they should give guarantees on retention for ten years to ensure
reproducibility.

## Chinese Wall Best Practices
Many privacy-sensitive data may not leave the systems they are kept in, e.g. they should be kept
within a technical `chinese wall'. This setup requires logging into some environment managed by
the data owner (e.g. a hospital).

When working within a chinese wall, the following may help:
* store a backup of the code on GitHub if this is allowed and refresh it frequently, *at least*
  daily.
* avoid manual changes to data
* make sure to capture all data processing in scripts (end-to-end), so that  
  you can always reconstruct your data

# TODO
* Add template Msc. student agreement for working with sensitive data (if allowed by owner)
