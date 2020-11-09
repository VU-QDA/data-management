# About
This repository contains best practices, pointers and tips for data management within the QDA
group.

The goal of this document is to help making choices regarding data processing for a typical QDA project.
We identify different project artifacts, artifact phases and external requirements and assess
different storage solutions based on this.

## Project Artifacts
Most QDA project consist of two types of artifacts:
 1. Data.  
    This can be both `raw` data, i.e. in the form it was collected in, as processed data.
 2. Code.  
    For a particular project, code can be used to generate data (simulators, live applications),
    to process data (generate insights, train models, etc.) or independently from any data (e.g. a
    package).

## Artifact Phases
Typically, a research project transitions through various phases.
![artifact
phases](https://raw.githubusercontent.com/VU-QDA/data-management/main/artifacts/research-cycle/research-cycle.png?token=AAW5FRAUA47LQ4WKVKWHVHS7VFVJO)

The most simple way to think of phases is during and after the project. During the project we want
the artifact to be private, easily available and changeable. After the end of the project, we
typically want the artifacts to remain available, yet not changeable. In many cases, we will want
to make artifacts publicly available. Although projects rarely last long, artifacts may be
repurposed and can cycle in and out of these phases.

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
Research artifacts need to be stored so that they can be investigated on suspicion of fraud. But
publishing your research artifacts may have direct benefits. For example, other authors may be more
prone to include your approach in a benchmark if you have published it.

You can publish your code and data using [Zenodo](https://zenodo.org/). Zenodo is an EU-backed
project aimed at making sharing, inspecting and repurposing research data more ease. Each Zenodo
release gets listed so that is easily findable. Additionally, it gets assigned a
[DOI](http://www.doi.org/) and other meta-data. This allows for you (and others) to cite the resource.
 
Code and data can also be published in a [GitHub
release](https://github.blog/2013-07-02-release-your-software/).

In case you are not allowed to publish your data (see `External Requirements'), you will still
need to store it for 10 (?) years. You will need to work with the data owner to see how this can
be made possible. VU offers a privacy-sensitive storage solution called DarkStor (€3.5 / GB /
Year, see VUnet).

## External Requirements
External requirements are demands from data owners. Typically, medical data comes with strict
controls on storage and processing. These requirements are in a sense `external'.

Since these requirements are not known and differ per project (partner), we only provide best
practices here.

### Chinese Wall Best Practices
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
* Group-specific storage data.ssh.vu?
  * Should contact cs administrator (Kees?)
  * Costs unknown
* Group-specific storage on DataVerseNL?
  * €3.5 / GB / Year
  * Contact VU library (Jolien Scholten)
* Check data retention requirements
* Include figure research phases

