# Assignment_1_Introduction

**This is the project for Assignment 1. Below you will find the overall instructions for the course's practicals, mirroring the instructions found in the ``course-environment``.**

---

# Computational Cognitive Modeling Practicals

Welcome to the Practical side of Computational Modeling of the Brain! Here you will find the 7 assignments - one per week - each in their own folder. 

## Setup

You've already created and logged into your Gitlab account - good job!

### Create Course Environment

The intended path structure of the course materials is along the lines of:

```
cmb/
├── course-environment/
│   └── environment.yml
│
├── group-1_assignment-1/
├── group-1_assignment-2/
└── group-1_assignment-3/
```

In general, you can deviate from this structure, as long as your final notebooks end up in the right place - in your Gitlab group!

The course environment is contained in its own yaml, and allows you to install it as a conda environment.

This assumes you have some version of conda installed. If you haven't, you can find information and the installation (Miniconda recommended) at: https://www.anaconda.com/download/success

Now, on whatever location is suitable for your computer:

```
mkdir cmb
cd cmb

git clone https://gitlab.com/rug-cs/courses/bsc-ai-cmb/2026-2027/student-resources/course-environment.git

conda env create -f course-environment/environment.yml
```

This installs a conda environment with the required packages called `compModBrain`.

Now we can go on downloading and installing the individual assignments.

### Working with the Assignments

Let's clone your repo's assignment into the main cmb folder

```
cd cmb #If you're not in it yet
git clone https://gitlab.com/<your-group>/<your-project>.git
```

Authenticate your GitLab credentials if required, likely in the browser.

```
cd <your-project>

git config --local user.name "Gitlab Name You Signed Up With"
git config --local user.email "user@gitlab.com"
```

Now you can work with the notebook in the designated environment

```
conda activate compModBrain
jupyter lab
```

Open the notebook in jupyter lab (or notebook), work in it, don't forget to save any changes you make!

Committing changes, pushing etc. works as you'd expect in git. The most basic way of committing and pushing changes is:

```
git add .
git commit -m "Finished Exercise 1a"
git push
```

Enjoy!

### Help, I've nuked my repo

In case you have somehow nuked your repo to a point where you cannot recover the original, untouched assignment anymore, you can revert back to a clean state with the following commands. **Be aware that this will replace and remove anything currently in your assignment's repo.**

```
# Download clean assignment
git fetch https://gitlab.com/rug-cs/courses/bsc-ai-cmb/2026-2027/student-resources/assignment_1_introduction.git main

# Replace local assignment
git reset --hard FETCH_HEAD

# Attach to repo history
git fetch origin
git reset --soft origin/main

# Save and upload the reset 
git commit -m "Restore clean assignment" 
git push
```