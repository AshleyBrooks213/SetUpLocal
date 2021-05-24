# SetUpLocal
Setting up local environment on Mac.

Set up Virtualenv:
https://sourabhbajaj.com/mac-setup/Python/virtualenv.html

# Before You Begin

https://youtu.be/R5AfIRMnWSo

Make sure you’re running the latest version of the the MacOS (Catalina, 10.15 or later).

Make sure that your default shell in the terminal is z-shell.

# Common Commands

https://youtu.be/V2ZvfpSN-dg

You should be familiar with the following terminal commands:

pwd
cd
ls
mkdir
clear
nano

# Installation

https://youtu.be/h8ffN2D5P_M

**Install Xcode**
In order to work locally on your Mac, you need to install Python 3 and pip3 on your machine. Fortunately, both of these come as part of Apple’s Xcode. If you haven’t already installed Xcode, open the Terminal and enter the following command:

```xcode-select --install```

A popup window will appear. **Click Install**, and accept the user agreement.

To make sure that the latest version of pip3 has been installed, enter:

```pip3 install --upgrade pip --user```

**Install pipenv**
Once, pip3 is installed, you can use it to install pipenv:

```pip3 install pipenv --user```

During installation, you may get a warning that looks something like this:

**WARNING:** The script virtualenv-clone is installed in 'Users/<your_username>/Library/Python/3.7/bin' which is not on PATH

Note that the name of your path will a little look different: Your username will appear after User/, and you might have a different version number after Python/.

You will need to use this path later in the installation, so copy the Users/<your_username>/Library/Python/3.7/bin text and paste it somewhere where you can access it later.

Below the warning message, you should see a message saying that pipenv has been successfully installed.

**Add Directory to Your PATH**
Note: You only need to do this step if you got the warning above.

You now need to create a file named .zshrc that has this new path information. One way to do this is to use the program nano. In the terminal, enter:

```nano ~/.zshrc```

This will turn the terminal into a text editor. Go back to the path you copied during the last step and use it to write the following line:

```export PATH="/Users/<your_username>/Library/Python/3.7/bin:$PATH"```

Make sure to insert your path after the ```"``` character, and then add ```:$PATH"``` to the end. There should be no spaces in this text.

**Hit Ctrl+o then enter to save the file. Then Ctrl+x to quit.**

Finally, quit the terminal (be sure to quit the program, not just close the window).

**Confirm Installation**
Reopen the terminal and enter the command pipenv. If the command line gives a list of options, then the install was successful!

# Configure Git

https://youtu.be/M15B6BFhNOE

In order to work with the Lambda curriculum repos, you need to configure Git on your machine. Open up the Terminal, and type out the these commands, following each with ENTER.

You can use any username, but better to use the username that’s associated with your GitHub profile.

```git config --global user.name <your username>```

Be sure that this email is the same one associated with your GitHub account.

```git config --global user.email <your email address>```

If you’d like to continue using nano to write commit messages, use:

```git config --global core.editor "nano"```

Alternatively, you can use VS Code:

```git config --global core.editor "code --wait"```

# Build a Virtual Environment

*Build an environment on the fly:

https://youtu.be/htyumnje_iI

In the Terminal, use the cd command to navigate to the folder where you want to build your enviroment. For example,

```cd Documents/GitHub/testenv```

Once you’re in the correct directory, execute the command:

```pipenv shell```

You’ll know that your virtual enviroment is active if your command line starts with the name of the enviroment in parentheses.

```(testenv) <...> %```

Use pipenv install <packages> to install the packages that you’ll use for the project, separated by spaces. For example,

```pipenv install pandas sklearn matplotlib notebook```

You can also specify package versions using ==. For example, ```pipenv install numpy==1.17.*``` would install version 1.17 of numpy.

**Note that if you want to use Jupyter notebooks, you always need to install the notebook package.**

# Build environment from requirements.txt file
  
  https://youtu.be/_oGiIumVMsM

In the Terminal, use the cd command to navigate to the folder where the requirements.txt file is located. For example,

```cd Documents/GitHub/testenv```

Once you’re in the correct directory, execute the command:

```pipenv shell```

Once your virutal enviroment is activated, use the following command to install all the dependencies listed in the requirements.txt file:

```pipenv install -r requirements.txt```
