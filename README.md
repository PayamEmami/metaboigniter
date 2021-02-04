# ![nf-core/metaboigniter](docs/images/nf-core-metaboigniter_logo.png)

**Get your metabolomics analysis up and running**.

[![GitHub Actions CI Status](https://github.com/nf-core/metaboigniter/workflows/nf-core%20CI/badge.svg)](https://github.com/nf-core/metaboigniter/actions)
[![GitHub Actions Linting Status](https://github.com/nf-core/metaboigniter/workflows/nf-core%20linting/badge.svg)](https://github.com/nf-core/metaboigniter/actions)
[![Nextflow](https://img.shields.io/badge/nextflow-%E2%89%A520.04.0-brightgreen.svg)](https://www.nextflow.io/)

[![install with bioconda](https://img.shields.io/badge/install%20with-bioconda-brightgreen.svg)](https://bioconda.github.io/)
[![Docker](https://img.shields.io/docker/automated/nfcore/metaboigniter.svg)](https://hub.docker.com/r/nfcore/metaboigniter)
[![Get help on Slack](http://img.shields.io/badge/slack-nf--core%20%23metaboigniter-4A154B?logo=slack)](https://nfcore.slack.com/channels/metaboigniter)

[![Gitter chat](https://badges.gitter.im/MetaboIGNITER/gitter.png)](https://gitter.im/MetaboIGNITER/community)

## Introduction

**nf-core/metaboigniter** is bioinformatics pipeline for pre-processing of mass spectrometry-based metabolomics data.
It can be used to perform quantification and identification based on MS1 and MS2 data.
The backbone of pipeline is based on XCMS, OpenMS, CAMERA, MSnbase, MetFrag, CSIFingerID, CFM-ID, and several other customized tools to noise filtering, quantification and identification both for library and in-silico identification. **Please go on to [this page](docs/metaboigniter_guide.md) to learn how to use the workflow**

The pipeline is built using [Nextflow](https://www.nextflow.io), a workflow tool to run tasks across multiple compute infrastructures in a very portable manner. It comes with docker containers making installation trivial and results highly reproducible.

## Quick Start

1. Install [`nextflow`](https://nf-co.re/usage/installation)

2. Install any of [`Docker`](https://docs.docker.com/engine/installation/), [`Singularity`](https://www.sylabs.io/guides/3.0/user-guide/) or [`Podman`](https://podman.io/) for full pipeline reproducibility _(please only use [`Conda`](https://conda.io/miniconda.html) as a last resort; see [docs](https://nf-co.re/usage/configuration#basic-configuration-profiles))_

3. Download the pipeline and test it on a minimal dataset with a single command:

    ```bash
    nextflow run nf-core/metaboigniter -profile test,<docker/singularity/podman/conda/institute>
    ```

    > Please check [nf-core/configs](https://github.com/nf-core/configs#documentation) to see if a custom config file to run nf-core pipelines already exists for your Institute. If so, you can simply use `-profile <institute>` in your command. This will enable either `docker` or `singularity` and set the appropriate execution settings for your local compute environment.




    **Please go on to [this page](docs/metaboigniter_guide.md) to learn how to use the workflow**
4. Start running your own analysis!

We highly recommend that you use the parameter file located in conf/parameters.config. Since the number of parameters is large, it's going to be a fairly complex bash command to run the workflow. Nevertheless, the parameters can always be passed to the workflow as argument using two dashes "--".

    <!-- TODO nf-core: Update the example "typical command" below used to run the pipeline -->

    ```bash
    nextflow run nf-core/metaboigniter -profile <docker/singularity/podman/conda/institute> --input '*_R{1,2}.fastq.gz' --genome GRCh37
    ```

See [usage docs](https://nf-co.re/metaboigniter/usage) for all of the available options when running the pipeline.

## Pipeline Summary

By default, the pipeline currently performs the following:

<!-- TODO nf-core: Fill in short bullet-pointed list of default steps of pipeline -->

* Sequencing quality control (`FastQC`)
* Overall pipeline run summaries (`MultiQC`)

## Documentation

The nf-core/metaboigniter pipeline comes with documentation about the pipeline: [usage](https://nf-co.re/metaboigniter/usage) and [output](https://nf-co.re/metaboigniter/output).

MetaboIGNITER is a comprehensive pipeline of several independent tools used to pre-process liquid chromatography-mass spectrometry (LCMS) data. We use Nextflow and nf-core to build and run the workflow but parts of this pipeline have also been implemented using Galaxy as part of [PhenoMeNal](https://github.com/phnmnl/) and [Pachyderm](https://github.com/pharmbio/LC-MS-Pachyderm).

## Credits

nf-core/metaboigniter was originally written by Payam Emami.

We thank the following people for their extensive assistance in the development
of this pipeline:

<!-- TODO nf-core: If applicable, make list of people who have also contributed -->

## Contributions and Support

If you would like to contribute to this pipeline, please see the [contributing guidelines](.github/CONTRIBUTING.md).

For further information or help, don't hesitate to get in touch on the [Slack `#metaboigniter` channel](https://nfcore.slack.com/channels/metaboigniter) (you can join with [this invite](https://nf-co.re/join/slack)).

## Citations

<!-- TODO nf-core: Add citation for pipeline after first release. Uncomment lines below and update Zenodo doi. -->
<!-- If you use  nf-core/metaboigniter for your analysis, please cite it using the following doi: [10.5281/zenodo.XXXXXX](https://doi.org/10.5281/zenodo.XXXXXX) -->

You can cite the `nf-core` publication as follows:

> **The nf-core framework for community-curated bioinformatics pipelines.**
>
> Philip Ewels, Alexander Peltzer, Sven Fillinger, Harshil Patel, Johannes Alneberg, Andreas Wilm, Maxime Ulysse Garcia, Paolo Di Tommaso & Sven Nahnsen.
>
> _Nat Biotechnol._ 2020 Feb 13. doi: [10.1038/s41587-020-0439-x](https://dx.doi.org/10.1038/s41587-020-0439-x).
> ReadCube: [Full Access Link](https://rdcu.be/b1GjZ)

In addition, references of tools and data used in this pipeline are as follows:

<!-- TODO nf-core: Add bibliography of tools and data used in your pipeline -->
