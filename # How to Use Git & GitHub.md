# How to Use Git & GitHub

This guide provides a concise overview of using Git and GitHub for version control, based on the essential steps and concepts introduced in the course materials .

---

## What is Version Control?
Version control systems (VCS) track changes in files over time, letting you:
- See who made which changes.
- Revert to earlier versions if needed.
- Collaborate seamlessly with others.

Git is a *distributed* VCS, meaning each collaborator’s machine has the full repository history. GitHub is a popular online service for hosting Git repositories and facilitating collaboration.

---

## Installing Git

1. **macOS**  
   - Open your Terminal and type `git`. macOS will typically prompt you to install developer tools if Git isn’t already installed.  
   - Alternatively, download from: [git-scm.com/download/mac](https://git-scm.com/download/mac)

2. **Windows**  
   - Download Git from: [git-scm.com/download/win](https://git-scm.com/download/win)  
   - Or install the [GitHub Desktop](https://desktop.github.com/) application, which includes Git automatically.

3. **Create a GitHub Account**  
   - Sign up at [https://github.com/](https://github.com/).  
   - (Optional) Request student benefits: [https://education.github.com/benefits?type=student](https://education.github.com/benefits?type=student)

---

## Creating Your First Repository

1. Log in to your GitHub account and click on your user icon in the top-right corner.  
2. Navigate to **Your repositories** → **New**.  
3. Choose a **name** (e.g., `firstrepo`).  
4. Select **Private** if you want it to be accessible only to you (and those you share access with).  
5. Choose **Add a README file** and select an appropriate `.gitignore` template (for example, “R” if you are storing R code).  
6. Click **Create repository**.

Your repository now exists on GitHub.

---

## Configuring Git Locally

Open a terminal (macOS) or Git Bash (Windows), then:

```bash
# Set your username (replace with your real name)
git config --global user.name "Your Name"

# Set your email address (use the one associated with your GitHub account)
git config --global user.email "your@email.com"
```
Then navigate to the folder where you would like to locate the
repository on your computer with cd (change directory)

## Cloning a repository

The next step is to copy (clone) the online repository to your computer:

1. On your repository page on GitHub:
   - Click on the green "Code" button
   - Copy the HTTPS URL

2. In the command line, enter:
   ```bash
   git clone <URL>
   ```
   (Replace `<URL>` with the copied repository URL)

3. Authentication:
   - You will be prompted for your GitHub username and password
   - Note: For password authentication, you'll need to create a personal access token
   - Some users may instead get a popup window for authentication - in this case you can skip creating an access token

   To create a personal access token:
   1. On GitHub, click on your profile icon in the upper right corner
   2. Go to Settings → Developer settings → Personal access tokens → Generate new token
   3. Configure the token:
      - Give it a descriptive name (e.g. "command line") 
      - Choose an expiration date
      - Select "repo" scope (allows access to private and public repositories)
      - Click "Generate token"
   4. Copy the generated token immediately (it will only be shown once)
   5. Return to the command line:
      - Enter your GitHub username
      - Use the token as your password when prompted
   
   Once authenticated, your Git and GitHub setup is complete and the repository will be cloned locally. You won't need to authenticate again until the token expires.


## Creating a file

1. We will now create a new file in the repository and log these changes

2. Create a new file:
   - Using RStudio or a text editor (e.g. VS Code - download at https://code.visualstudio.com/)
   - Add a file called `somecode.R` into the repository folder

3. Navigate to the repository:
   ```bash
   cd firstrepo
   ```

4. You are now ready to commit the changes made to the repository

## Committing changes

1. Check for changes:
   ```bash
   git status
   ```
   Make sure you are in the repository folder on your computer

2. Add changes to staging area:
   ```bash
   git add .
   ```
   - You can also add specific files instead of using the dot
   - WARNING: Be very careful using the dot to add files!

3. Commit the changes:
   ```bash
   git commit -m "added a code sample"
   ```

4. View commit history:
   ```bash
   git log
   ```

To practice these steps:
1. Add another line of code to your file
2. Repeat the above process (status → add → commit)
3. Check the commit history again with `git log`

## Pushing changes to the remote repository

1. Store changes in the remote repository:
   ```bash
   git push
   ```

2. Review changes in GitHub:
   - Go to repository page on GitHub
   - Click clock symbol next to 'commits' in upper right
   - Click on commit hash (e.g. '472cb9d') to see code changes

3. Get latest changes:
   ```bash
   git pull
   ```
   Run this if others have updated the remote repository


## Additional Git/GitHub Concepts

### Forking
- Creates your own copy of someone else's repository on GitHub
- Changes you push only affect your fork, not the original repository
- Useful for contributing to open source projects
- Different from cloning which creates a local copy

### Branches
- Parallel versions of code that branch off from main codebase
- Allow development of features without affecting main code
- Create a new branch:
  ```bash
  git branch feature-name
  git checkout feature-name
  ```
- Or create and checkout in one command:
  ```bash 
  git checkout -b feature-name
  ```

### Merging
- Combines changes from different branches
- Merge a branch into current branch:
  ```bash
  git merge branch-name
  ```
- May need to resolve conflicts if same files changed in both branches

### Pull Requests
- GitHub feature to propose changes from your fork/branch
- Steps to create:
  1. Push changes to your fork/branch
  2. Go to original repo on GitHub
  3. Click "New Pull Request"
  4. Select branches to compare
  5. Add description of changes
  6. Submit pull request
- Repository maintainers can review, comment, and merge

### Review of Key Commands

| Command | Description |
|---------|-------------|
| `git clone ...` | Download online repository to local computer |
| `git status` | See status of files in repository |
| `git add .` | Stage all changes made (alternatively add distinct file names to be staged) |
| `git commit -m "some message"` | Commit (i.e. record) staged changes |
| `git push` | Upload local changes to remote repository |
| `git pull` | If files changed online, update local repository first |