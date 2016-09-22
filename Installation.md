# Workshop Set Up

## 1. Installing Python with Anaconda

One of the easiest ways to install and work with **Python** is through **Anaconda**, and this is the option we will be using for the workshop. Anaconda is an open source Python and R distribution which includes a hundred of the most popular Python, R and Scala packages for data science, as well as **conda**, a package dependency and environment manager that gives you access to over 720 ready-to-install packages. Anaconda is available for Windows, OS X and Linux.

>* If you are comfortable working with Python already and prefer using your own installation instead of using Anaconda, you are free to do it, but we will follow the class assuming you know how to create your own virtual environments and install libraries. Use Python 2.7 to create your environment and install the libraries specified in the paragraph 3.2.


>* If you already have Anaconda installed, you can jump to paragraph 2, but remember updating your conda distribution with the following commands:
```
conda update conda
conda update anaconda
```


To install Anaconda, you can choose between these two ways, depending on the available space in your computer and the WiFi conditions:

### 1.1 Option I: Anaconda
This installs the whole distribution with the most popular data science packages included. Requires 3 GB of available disk space.

Use the following link to download the package according to your operative system and architecture (in any case select the **Python 2.7 version**): http://continuum.io/downloads

Follow the default installation. If you are installing through your command line and you are asked the following question, we recommend you to answer **yes**:

```
Do you wish the installer to prepend the Miniconda2 install location
to PATH in your /home/malonfe/.bashrc|.bash_profile ? [yes|no]
```

### 1.2 Option II:  Miniconda
It is a lighter alternative to Anaconda. Miniconda comes just with Python and **conda** manager. It is an ideal option for users who want to start with a minimal installation and install the packages as they are necessary. Requires 400 MB of available disk space.

Use the following link to download the package according to your operative system and architecture (in any case select the **Python 2.7**):
http://conda.pydata.org/miniconda.html

Follow the default installation for your operative system [here](http://conda.pydata.org/docs/install/quick.html). If you are installing through your command line and you are asked the following question, we recommend you to answer **yes**:

```
Do you wish the installer to prepend the Miniconda2 install location
to PATH in your /home/malonfe/.bashrc|.bash_profile ? [yes|no]
```
## 2. Useful conda documentation
[Conda cheat sheet](http://conda.pydata.org/docs/_downloads/conda-cheatsheet.pdf)

[Conda Docs](http://conda.pydata.org/docs/using/index.html)

## 3. Creating a Python virtual environment to work with
Using **virtual environments** when working with Python is a good practice as it means working like in a separate "box" where you can install the libraries you need for a project, not interfering with other environments or projects.

### 3.1 Be sure that you have **conda** added to your path
In your terminal write just the command:

```
conda
```

If you received a message like this:

```
-bash: conda: command not found
```
then keep reading how to add conda to your path. If otherwise the command responses with a lot of options, go to step 3.2.




#### In OS X
You need to add the following lines to your `/Users/<my-user>/.bash_profile` file (changing `<my-user>` for your user name and `<anaconda-folder>` for either miniconda2 or anaconda2):

```
# added by Miniconda2 4.1.11 installer
export PATH="/Users/<my-user>/<anaconda-folder>/bin:$PATH"
```

Then write the following command for the chages to take effect:
```
source .bash_profile
```
If the **`conda`** command keeps returning the same error close the terminal and open it again.

#### In Linux
You need to add the following lines to your `/Users/<my-user>/.bashrc` file (changing `<my-user>` for your user name and `<anaconda-folder>` for either miniconda2 or anaconda2):


```
# added by Miniconda2 4.1.11 installer
export PATH="/home/<my-user>/<anaconda-folder>/bin:$PATH"
```

Then write the following command for the changes to take effect:
```
source .bashrc
```
If the **`conda`** command keeps returning the same error close the terminal and open it again.

#### In Windows
You need to add the route to your anaconda or miniconda *bin* folder to your PATH in the environment variables. Check this [link](http://www.computerhope.com/issues/ch000549.htm) on how to manage your environment variables in different Windows versions.

### 3.2 Create a virtual environment with the necessary libraries
To create your virtual environment with conda, run the following command in your working folder:

```
conda create --name myvenv pandas jupyter matplotlib seaborn
```
The name of your new virtual environment will be **`myvenv`** and you will be adding to it the following libraries: **`pandas, jupyter, matplotlib and seaborn`**. This process will take longer with Miniconda as it needs to download the libraries before adding them to the environment.

> In case you are using your own Python installation, the libraries you should install in your virtual environment are the same. Some of them depend on others, so installing **`seaborn`** will probably install **`pandas`** and **`matplotlib`** already for you. Remember using `pip freeze` to check what libraries you have installed.

### 3.3 Activate your virtual environment
Now you need to activate the virtual environment you just created. The command that will do that for you is:
```
source activate myvenv
```
If the virtual environment was successfully activated you should see that the prompt in your terminal has changed to something like this:
```
(myvenv)<your-computer-name-and-user>$
```
Now you are inside your virtual environment and you are ready to start working on it.

>If you use your own python remember to activate your environment with `source myvenv/bin/activate`

## 5. Download all the required files
All the files that you need are in PyLadiesDC GitHub online repository and can be donwloaded easily:  
  * Go to the workshop repo https://github.com/PyLadiesDC/python-for-journalists
  * In the 'Clone or Download it' button select your choice:
      * If you don't use git regularly just use the option 'Download Zip' and unzip the files in your computer 
      * If you are familiar with git, just clone the repo if you want

## 6. Run Jupyter notebook
The Jupyter Notebook is a web application that allows you to create and share documents that contain live code, equations, visualizations and explanatory text. We will use it to run our Python scripts and check the output of our code. We'll provide you the script you'll need in order to follow the workshop.

With your virtual environment activated, go to the folder you just downloaded and run the following command:

```
jupyter notebook
```
A server will be launched and a new tab will be open in your default browser (by default in http://localhost:8888/) allowing you to navigate your scripts, open them, work with them, and save all your changes.

The server takes the control of your terminal, so if you need to run any command on it, either you stop the server with CTRL+C, or you send the process to the background (checkout this [link](http://www.thegeekstuff.com/2010/05/unix-background-job)). If you are not really familiarized with unix commands we recommend you to stop and relaunch the server any time you need it, or open two terminals. In the latter case do not forget to activate your virtual environment in both of them.

## 7. Shutting down
### 7.1 Deactivating environment
Check again the conda cheat sheet we provided to learn how to manage the environments. In order to deactivate your virtual environment (you can always simply close the terminal) you should run the following command:

```
source deactivate
```

> For standard python environments with the `deactivate` command is enough.

### 7.2 Returning your Path to the original value
If you ever need to use your system's Python, instead of the Anaconda's Python we have been using today. Remember that we updated your PATH, so anytime you run the `python` command you'll be using the Anaconda one. In order to avoid that, you can comment the lines of code we have added to either your `.bashrc` or your `.bash_profile` file. Or, for Windows systems, delete the route you just added to your path.

If you want to run condas without having the path updated you may:
* either use the absolute path to the command, see the example:
```
<miniconda2|anaconda2>/bin/conda create --name newenv pandas
```

* update the path temporarily (for your console session) in the console you are using writing the same line you had in your bash file:
```
export PATH="/Users/<my-user>/<anaconda-folder>/bin:$PATH"
```

An useful command to know which Python you are running at any time is the following one, that tells you the path to the executable Python you are calling.

```
which Python
```
When using Anaconda the result would be something like this:
```
/Users/<my-user>/<miniconda2|anaconda2>/envs/myvenv/bin/python
```




