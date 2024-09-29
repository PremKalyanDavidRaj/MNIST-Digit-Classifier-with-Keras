## Lab 1: Build a Classifier for Hand-Written Digit Images

### Purpose
This lab has three goals, to introduce you to:
- First set of key concepts in **neural AI**
- Basic usage of **conda** Python package and environment manager
- How to develop a neural AI system in **VS Code**

Through the practical experience of this lab you'll be introduced to key neural AI concepts:
- Deep neural networks
- Supervised learning
- Image classification 
- Machine learning frameworks and libraries
    - Google TensorFlow
    - TensorFlow Keras library

Another goal of the lab is an introduction to a very popular Python package and environment manager, **conda**. In this lab, you'll learn how to:
- create and configure a Pyton environment with conda
- install packages
- record package installations. 

Using VS Code you'll experience how to build a neural AI system with the help of 
of a professional machine learning framework, Google's TensorFlow, and its Keras library.

### Guidelines
#### Get the codebase
- Open a terminal utility: git-bash for Windows or terminal for MacOS/Linux
- Change directory to home directory
    - You should have a **comp841** or **comp741** folder for all the programming
    activities in this class. Otherwise, create one.
    - We'll call this directory "course root directory"
- Change directory to course root directory
- Clone lab1 from GitHub
    - `git clone <URL of lab1> lab1`
    - Note the 2nd argument of the `git clone` command
- Change directory to `lab1`

#### Get ready to configure the Python conda environment
- Open VS Code
    - From the top menu bar: File --> Open Folder ...
    - Select `lab1` folder
- Installl Copilot, Copilot Chat, and Jupyter extensions
- In VS Code, open the integrated terminal
    - From the top menu: View --> Terminal
- Switch the terminal's shell to **git-bash** (Windows) or **bash** (MacOS/Linux)
- MacOS/Linux developers ONLY:
    - Open Preferences: Open User Settings (JSON)
        - Cmd and Shift P to open the command palette
        - Type "Preferences: Open User Settings" and select it
        - Find Features -> Terminal
        - Scroll until you find the option "Intergrated InheritEnv"
            - Unselect it
        - This prevents VS Code to have its integrated terminal inherit from a previous 
        integrated terminal instead of inheriting from the MacOS/Linux OS user environment.  

#### Configure conda environment
The `conda` commands that will configure and manage the packages of lab1 environment 
are the following:
```
conda env list          # list Python environments created with conda
conda deactivate        # deactivate current conda environment, if any
conda create --name mnistenv python=3.11    # create an environment for lab1
conda env list          # new environment should be listed, along with base
conda activate mnistenv # activate the new environment
conda list              # list currently installed packages
conda install ipykernel
conda list
conda install tensorflow
conda list
conda install matplotlib
conda list
```
Get assistance from the classroom assistant or instructor to to resolve any issues 
you might have. 

#### Run the notebook, one cell at a time
- Read carefully all the notes in the Jupyter notebook `digit_classifier.ipynb`
- Examine carefully each code cell.
    - Try to understand the meaning of the code
    - If you need more explanations, ask Copilot.
- Run each code cell
- Pay attention to the quesitons and challenges. 
- Determine to what extent the output from running a cell clarifies your questions. 

### Requirements
The lab has two parts:
#### Understanding
- Create an `UNDERSTAND.md` file that has all the questions and challenges from the `digit_classifier.ipynb` notebook.
- Try to answer the questions
- Make sure that you give attribution to Copilot when used. 
    - What prompt did you use? 
    - What portion of the Copilot answer was relevant to your understanding?
    - Try to rephrase the answer in your OWN words. 
- If you use other sources, include the reference of the source. 
    - Again, try to rephrase the answer in your OWN words. 
- Challenges are required of graduate students only. 
    - Undergraduate students are very much welcome to give them a try. 

#### Experimentation
- Apply the approach used in building this digit classifier to build another classifier. 
- Use another dataset avaiable through Keras web site, such as CIFAR10 dataset. 
- Experiment with 2 hidden layers and 3 different batch sizes
- Record findings from your experiment in a new file, `EXPERIMENT.md`:
    - How many parameters were adjusted during training?
    - How long did the training take? 
    - What loss and accuracy did the model produced? 

#### Learning
- What other questions did you have while working on this lab?
- Think of those questions as building blocks to further improve your understanding of **lab1**. 
- Write the questions in a separate sections, at the end of the `UNDERSTAND.md` file, 
that has the heading `### More relevant questions`

### Submission
#### Canvas
- Convert the two Markdown files to PDF files that render the preview version of the
original Markdown file. 
- There are free online services that do the converstion. 
- My preference is to use `pandoc` tool
    - Install it on your machine
    - To convert a Markdown file, the command in a terminal utility is:
        - `pandoc Q&A.md -o Q&A.pdf`
- Uplodad both PDFs to the Canvas submission link

#### GitHub
- Use git version control commands ONLY for the Markdown files and the new notebook. 
- Before you push commit changes to the new notebook
    - Make sure you **Clear all outputs** from the notebook
    - Afte that, stage (`git add`) and `git commit -m ...`
    - Now, you are ready to `git push origin main`


