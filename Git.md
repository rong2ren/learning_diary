# Using Git for Version Control

As part of my learning process, I practiced using Git for version control. Below are the steps I followed to create a new Git repository, add files, and push them to GitHub.

1. Creating a New Folder
```
cd G:
cd GitLearning
mkdir LearningPythonDiary
```

2. Initializing a Git Repository
Next, I initialized a Git repository in the folder:
```
git init
```

3. Adding a File to the Staging Area
I added a file to the Git staging area (from the working directory):
```
git add filename
```

3. Committing Changes
Once the file was added to the staging area, I committed the changes to the local repository with a commit message:
```
git commit -m "Initial code commit"
```

4. Pushing the Code to GitHub
To push my local changes to GitHub, I first needed to configure Git with my GitHub username and email and generate an SSH key. The following commands set up my global Git configuration:
```
git config --global user.name "Your Name Here"
git config --global user.email "your_email@example.com"
```
Then, I added my SSH public key to my GitHub account and set up the remote repository. For SSH access, I used:
```
git remote add origin git@github.com:username/LearningPythonDiary.git
```
Alternatively, I could use HTTPS, but that would require entering my username and password with each push:
```
git remote add origin https://github.com/username/LearningPythonDiary.git
```
Finally, I pushed the local code to the master branch on GitHub:
```
git push origin master
```

5. Pulling Changes from GitHub
If I wanted to update my local repository with changes from GitHub, I used:
```
git pull origin master
```

6. Cloning a Repository from GitHub
To clone an existing GitHub repository to my local machine, I used the following command:
```
git clone https://github.com/peterluo/LearningPythonDiary.git master
```
