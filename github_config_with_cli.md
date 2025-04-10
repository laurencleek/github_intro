# Git: Command Line Usage

These steps outline how to install and use Git from a regular terminal or command line. Git is the underlying version-control tool for creating, tracking, and managing repositories. Here, we will walk through installing Git, configuring user details, and interacting with GitHub repositories using HTTPS.

---

## 1. Installing Git

Open Anaconda Prompt (or any terminal) and run:
```
conda install -c anaconda git
```
When asked to proceed, type “y” and press Enter. This will install Git on your system. If you need to update Git:
```
conda update git --channel conda-forge
```

---

## 2. Configuring Git

After installation, configure your username and email (these will appear on your commits):
```
git config --global user.name "YourName"
git config --global user.email "YourEmail@example.com"
```
You can check these settings any time:
```
git config --list
```

---

## 3. Cloning Repositories with HTTPS

On GitHub, open the repository you want to clone, click “Code,” and copy the HTTPS URL. In your terminal, go to the directory where you want the cloned folder:
```
cd C:\Users\YourName\Documents
```
Then clone the repo:
```
git clone https://github.com/YourOrg/YourRepo.git
```
This downloads the entire repository, including its history.

To update your local copy with new commits from GitHub, navigate inside the cloned folder and run:
```
git fetch
git merge
```
Or simply:
```
git pull
```
“pull” fetches and merges in one step.

---

## 4. Working on Assignments (or Any Repository)

1. Navigate to the folder where you want to store the repository.
2. (Optional) Create a new folder with:
    ```
    mkdir assignment-1
    cd assignment-1
    ```
3. Initialize a repository if starting from scratch:
    ```
    git init
    ```
4. If the remote repo already exists on GitHub, clone or pull it using the HTTPS URL.  
    Example for pulling a repo to an empty folder:
    ```
    git pull https://github.com/YourOrg/assignment-1-YourUserName.git
    ```

---

## 5. Submitting Changes

When you modify or add files, check their status:
```
git status
```
To stage all new or changed files:
```
git add .
```
Commit the changes with a message:
```
git commit -m "Explain what changed here"
```
Finally, push to GitHub:
```
git push
```
Ensure you specify the remote if it’s not tracked yet:
```
git push https://github.com/YourOrg/assignment-1-YourUserName.git
```
Check your GitHub repository in the browser to confirm that your changes are visible.

---

By using Git directly, you can manage, contribute to, and fetch updates from any GitHub repository without additional command-line tools.
