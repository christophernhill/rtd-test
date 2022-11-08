# Contributing notes 

   * [Current draft outline](test.md#draft-outine)
   * [How to preview a PR](test.md#previewing-a-pr)
   * How to test build docs locally under OSX

## Draft outline

- ORCD Systems
    - For each have
        - Short description
        - Distinguishing factors
        - How to get an account
        - Link to pages/docs
    - What is the same? What is different?
- Filesystems and File Transfer
    - Filesystems
        - For each, how is the filesystem laid out? Anything to know about where to run, where to store, home directories, group directories, local disk, tmp/scratch space?
        - NESE
        - Best practices
    - How to transfer files
        - From desktop to each system
        - Between systems
- Basic software and package installation
    - Environment Modules
    - Installing packages/libraries in Python, Julia, R
    - Other software installs/requests
        - Self service- own installs, install from source, how to make a module, "module use"
        - Spack, easybuild
- Running Jobs
    - Again, what is the same? What is different?
    - How do we look up what partitions are available? What are they each for?
    - How do I run a...
        - Throughput job?
        - Distributed/Multinode job?
        - Multicore job?
        - GPU job?
        - Interactive job?
        - Jupyter job?
- Specific Software How-Tos: answers the question "How do I run/use X on Y?"
    - For each software:
        - How do I get set up?
        - How do I run it as a job?
        - What are the differences between systems?
    - Do we want to include "install from source" instructions?

## Previewing a PR

## Notes on setting up to build locally on OSX

#### One time install
```
mkdir sphinx-setup
cd sphinx-setup
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh 
chmod +x Miniconda3-latest-MacOSX-x86_64.sh
./Miniconda3-latest-MacOSX-x86_64.sh -b -p ./miniconda3
```

#### Repeat at start of shell session
```
cd sphinx-setup
. miniconda3/bin/activate
conda create -n orcd-sphinx python=3.10
conda activate orcd-sphinx
```

#### To add sphinx software (one time)
```
cd sphinx-setup
. miniconda3/bin/activate
conda activate orcd-sphinx
conda install -c conda-forge sphinx sphinx_rtd_theme sphinx-panels
```

#### To build docs
```
cd sphinx-setup
. miniconda3/bin/activate
conda activate orcd-sphinx
cd ../orcd-docs-edit-git
sphinx-build -E . _build
```

