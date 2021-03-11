# How to install C/C++ Compile on windows vscode


* **First install vscode**
* **Download c/c++ intelligence extention from vscode extention installer**
* **Go the link and istall MinGW-64 (it's c/c++ compiler) <br>**
[Download Link MinGW-64 compiler](https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/installer/mingw-w64-install.exe/download)

* **After installing compiler go to "C drive" then, mingw/bin directory. Copy the full directory path for set enviroment variable**
* **Open the enviroment variable settings for your account**
* **Go the path setting, "new option" and paste the directory address**

<mark>You are good to go! Everything had done.</mark><br>

* **Open your CMD and run folloing code below:**<br>

````
g++ --version

gdb --version
````

### [For more information, Visit this site](https://code.visualstudio.com/docs/languages/cpp)