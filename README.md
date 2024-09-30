## Build a Classifier for Hand-Written Digit Images

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
