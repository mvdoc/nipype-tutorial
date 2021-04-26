# A minimal tutorial on Nipype by Matteo Visconti dOC

This repository contains a very, very short tutorial on
[Nipype](https://nipype.readthedocs.io/en/latest/). It is far from being a
complete tutorial of all features of Nipype. It shows how I would go about creating
a simple workflow for QA, which generates a temporal SNR volume and framewise displacement 
parameters. In the process, it highlights some useful features and practices to iterate
workflows over multiple files (largely inspired by [fMRIPrep](https://fmriprep.org/en/stable/)).

This tutorial was written rather quickly, and the narrative needs to be improved.
That said, I think it accomplishes the goal of showcasing the benefits of using Nipype. 
The audience is assumed to be researchers who already know a great deal about
neuroimaging, and who are trying to switch to a better way of writing pipelines.

More exhaustive tutorials are available elsewhere. To learn more about Nipype, I
highly recommend checking the following links:

- [Nipype example's page](https://nipype.readthedocs.io/en/latest/examples.html)
- [Michael Notter's Nipype tutorials](https://miykael.github.io/nipype_tutorial/)

If you need help, do the following

1. Search through [Nipype's issues](https://github.com/nipy/nipype/issues).
2. Search on [Neurostars](https://neurostars.org/).
3. If 1. and 2. do not answer your question, post on Neurostars.

More advanced users might want to check the following packages containing tested workflows. 
If you can use them without reinventing the wheel, that's fantastic. Otherwise they are
great for inspiration.

- [nipreps/niworkflows](https://github.com/nipreps/niworkflows) for common MRI workflows
- [nipreps/sdcflows](https://github.com/nipreps/sdcflows) for distortion-correction workflows.


## Installation

Python packages required by this tutorial are listed under `requirements.txt`. Install them with

```bash
pip install -r requirements.txt
```

in your favorite conda/non-conda environment. Feel free to open an issue or a
PR if I forgot some packages.

You also need a working version of FSL and AFNI to run some steps of the
example workflows. The tutorial uses [DataLad](https://datalad.org) to download
a dataset from [OpenNeuro](https://openneuro.org). You might need to install
[git-annex](https://git-annex.branchable.com/).

## Content

- [01-example-interface](01-example-interface.ipynb) describes
  what an `Interface` object is, one of the building blocks of Nipype workflows.
- [02-example-simple-workflow](02-example-simple-workflow.ipynb) creates a
  simple quality-assurance workflow that performs motion correction, computes
  tSNR on the motion corrected volumes, and computes framewise displacement. In
  the process, it explains some core concepts of writing Nipype workflows.
- [03-extending-our-first-workflow](03-extending-our-first-workflow.ipynb)
  extends the workflow so that it can be run over multiple files. It showcases
  the `Function` interface, some advanced features of Nipype to rename
  filenames, one way to create subworkflows for each input file, and how to use
  a `DataSink` node.
