# Python class notes
Notes from  HarvardX: PH526x Using Python for Research 

## Sections

1. [Week 1: Basics](Wk1_basics.md)

2. [Week 2: Python libraries and concepts](Wk2_Py_librariesAndConcepts.md)

    - [Jupyter notebook with Matplotlib notes](Matplotlib.ipynb)
3. Week 3: Case studies Part 1
    - [Learn how to translate DNA](Learn_how_to_translate_DNA.md)
    - [Learn how to process texts](case_studies_I.ipynb)
    - [Learn how to classify items using the k-nearest neighbors method]

# Uncategorized notes

## Function code from environment

Often in DataCamp, once you answer is accepted as correct, you could be curious about how the instructors wrote the code. If their function is loaded in the environment, you can see the code as follows 

```
import inspect
inspect.getsourcelines(functionName)

```

## Conda for python

If conda is not already installed, follow instructions from link below

### [Installing conda](https://conda.io/docs/user-guide/install/index.html)

Make sure conda installed properly using `conda --version` (if you get `conda command not found` error, odds are adding the path to its bin to your .bash_profile file should do the trick)

Create a new environment for python3.6
`conda create -n py36 python=3.6 anaconda`

Activate this (or any other created) environment
`source activate py36`

To install packages in this environment
`conda install packagename`

To close and clean up
`source deactivate`
