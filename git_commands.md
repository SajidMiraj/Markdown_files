# Git Configuration Commands

## 1. GIT SETUP

```
git config --global user.name <given username>

git config --global user.email <given vaild-email>

git config --global color.ui auto
```

## 2. Checking Your Validation 

* Run following commands : 

```
git config --global user.name

git config --global user.email

```

* If output and your providing username & email is same, you are good to go!

## 3. GIT INITIALIZE 

* Initialize an existing directory as a Git repository
````
git init
````

## 4. GIT ESSENTIAL COMMANDS 


```
git status --> show modified files in working directory.

git status -s --> show extra some features on working directory.

git diff <file-name> --> see all changed in specific file before move stage area.

git diff --> see all changed for files before move stage area.

git add <file name> --> to move modified file in staging area.

git add -A --> move all modified files in staging area.

git diff --staged --> see all changes in stage area before commit.

git reset <file name> --> unstage a file which is staging area. 

git commit -m “commit message” --> commit your all files on staged .

git checkout <file name> --> delete all current changes code in specific file and push privious commit code.

git checkout -f --> delete all current changes code in all files and push privious commit code.

git log --> show all commits history.

git log -p -3 --> you can see first 3-commit messange among total

git rm -cached --> remove files just from git not permanently hard-disk.

git rm <file name> --> delete file permanently.

```

## 5. Branch Creating

```
git branch --> lists all branches

git branch <branch-name> --> create a branch.

git checkout <branch-name> --> jump one from other branch. 

git merge <sub-branch-name> master --> add all code sub-branch to master.
```

## 6. SSH key for GITHUB
* **Open your gitbash terminal and run following codes:**
```
    ssh-keygen -t ed25519 -C "<your_email@example.com>"

    eval `ssh-agent -s`

    ssh-add ~/.ssh/id_ed25519

    clip < ~/.ssh/id_ed25519.pub

```
* **Then, go to your account settings**
* **Find "SSH and GPG keys" from Navbar**
* **Open it and click "New SSH key" option**
* **Define an "unique title" and click paste option in "Key field"**
* **click "add SSH key" option YOU ARE GOOD TO GO !**
* **[Visit here for more information](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)**


## 7. 

### **[GIT PDF](https://education.github.com/git-cheat-sheet-education.pdf)**