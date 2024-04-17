Topic 05: Dissecting DNA methylation heterogeneity in disease
============================================================

### *Project overview and guidelines*

-   [Introduction](#introduction)
-   [Objective](#objectives-and-work-plan)
-   [Description of datasets](#description-of-datasets)
-   [Literature review](#literature)
-   [How to structure your project](#how-to-structure-your-project)
    -   [Project proposal](#project-proposal)
    -   [Project](#project)

Supervisor
----------

- Supvervisor: Michael Scherer - michael.scherer@dkfz.de
- Tutor: Stefanie Mantz - s.mantz@stud.uni-heidelberg.de


Introduction
------------

DNA methylation is a cell-type specific epigenetic modification that is severly altered in multiple diseases, especially in cancers. By the addition or removal of a methyl-group to cytosines in the CpG context in DNA, the transcriptional activity of genes can be modulated. This can, for example, cause the aberrant activation of oncogenes or the supression of tumor supressor genes. DNA methylation has utilities as a biomarker, since it can be read in a high-throughput manner using next-generation sequencing approaches, but also with microarray technologies. Using these microarray technologies, one can readout a subset of 1-5% of all CpGs dinucleotides in the human genome at high-throughput. The microarrays will generate so-called beta-values limited to the [0, 1] interval representing the fraction of methylated CpGs in the bulk of cells that have been used as input to the array. We expect that most of the CpGs will have beta values close to either 0 or 1, respectively.


Objectives and work plan
------------------------

Within this project, you will analyze a DNA methylation dataset generated using the Illumina Methylation 450k bead array (microarray) technology. The goal is to thoroughly understand technical issues related to the array, to filter CpGs for their quality, and ultimately to perform a differential DNA methylation analysis between cancer and matched normal samples. In addition to an exploratory analysis, including low-dimensional representation plots of the data, you will also investigate the methylation state of individual CpGs.


Description of datasets
-----------------------

Your dataset comes in the form of a DNA methylation data matrix. Rows represent the different CpGs (usually between 400,000 and 800,000) and columns contain the samples that we want to analyze. You will have an additional data matrix comprising phenotypic information about the samples, i.e. this matrix will contain as many rows as columns in the data matrix. Each entry in your data matrix contains the beta values representing the average DNA methylation state of all cells analyzed in an individual sample. The data matrix has already been normalized to account for technical issues of the microarrays.

Data comes from the TCGA project and was already pre-processed to remove CpGs due to lower technical quality in a bigger cohort. However, you should still investigate whether some CpGs do not behave as expected. We have different tumor entities and would like each of the groups to investigate one of the tumor entities:

- Group 1: BRCA = Breast invasive carcinoma
- Group 2: LUSC = Lung squamous cell carcinoma
- Group 3: COAD = Colon adenocarcinoma
- Group 4: THCA = Thyroid carcinoma
- Group 5: KIRC = Kidney renal clear cell carcinoma

Data is available from: https://hub.dkfz.de/s/oeFnRppe6BpfNFa

Literature 
----------

- Pidsley, R., Zotenko, E., Peters, T. J., Lawrence, M. G., Risbridger, G. P., Molloy, P., Van Djik, S., Muhlhausler, B., Stirzaker, C., Clark, S. J., Jones, P., Baylin, S., Ko, Y., Mohtat, D., Suzuki, M., Park, A., Izquierdo, M., Han, S., Dayeh, T., … Kent, W. (2016). Critical evaluation of the Illumina MethylationEPIC BeadChip microarray for whole-genome DNA methylation profiling. Genome Biology, 17(1), 208. https://doi.org/10.1186/s13059-016-1066-1
- Bock, C. (2012). Analysing and interpreting DNA methylation data. Nature Reviews Genetics, 13(10), 705–719. https://doi.org/10.1038/nrg3273
- Müller, F., Scherer, M., Assenov, Y., Lutsik, P., Walter, J., Lengauer, T., & Bock, C. (2019). RnBeads 2.0: comprehensive analysis of DNA methylation data. Genome Biology, 20(1), 55. https://doi.org/10.1186/s13059-019-1664-9

How to structure your project
-----------------------------

### Project proposal

You first task will we to define a **project proposal**, which should
include

-   summary of literature
-   questions you want to address
-   approximate timetable

You will present this project proposal together with a literature review
on the subject 3 week after the beginning of the semester (10 minute
presentation + 5 minutes discussion).

### Project

Your project **MUST** contain the following elements:
- **descriptive statistics** about the datasets
- **graphical representations**
- **dimension reduction** analysis (PCA, clustering or k-means)
- **statistical tests** (t-test, proportion tests etc)
- **linear regression** analysis, either uni- or multivariate

#### Data cleanup

You will be analyzing multiple data sets together. It is
essential that you explore each dataset and clean it. Cleaning can refer
to many things:

-   Removing/Imputing missing values
-   Removing low variance columns/rows
-   Removing outlier samples (only if it is due to technical issues !!)
-   Making sure that data is in the correct format, for example, numbers
    should be encoded as numeric and not as characters. Categorical
    variables should be factors etc.
-   Re-ordering rows/columns in meaningful and useful ways

#### Data exploration

Now that you have cleaned data, explore your data to understand its
structure. Perform basic exploratory data analysis.

-   Look at the distribution of the overall data, specific samples or
    features.
-   Visualize the data distribution
-   Visualize the inter-dependencies (e.g. correlations) among specific samples/features of
    interest
-   Check some of your hypothesis like - is something high/low between
    two conditions etc

#### Data reduction

You have a high dimension matrix, that is, you have way more features
 than observations.

-   Try out methods to reduce the dimensionality of this data.
-   Cluster your samples to identify similar and dis-similar groups
-   Check how well the groups separate based on the features of your
    interest

#### Data modelling

Using data modeling with linear regression, we expect you to perform two tasks:

- Generate linear models to understand the relationship between CpG methylation states and phenotypic information. We want you to compare the *Primary solid Tumor* to the *Solid Tissue Normal* group
- Use linear models to understand relationships between different CpGs. Are there highly correlated or anti-correlated CpGs?
