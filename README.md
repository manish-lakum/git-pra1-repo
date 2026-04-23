# git-pra1-repo
use of practical exam in git program
1.Git Related Sample for Practical exam: 
Tracking Files Lifecycle
• Create a file (app.txt)
• Check repository status
• Stage file using git add
• Commit changes using git commit
• Modify file and view differences using git diff
• Commit updated changes
Create dev branch, Switch branches, Make changes
in dev, Switch back to main, Compare branches.
this pratical step by step commnad give me and all command is which work is explian

ans:
1. Initialize Repository
git init

👉 Creates a new Git repository in your folder.

🔹 2. Create a File
echo "Hello Git" > app.txt

👉 Creates a file named app.txt with content.

🔹 3. Check Repository Status
git status

👉 Shows:

Untracked files
Modified files
Staged files

📌 Now app.txt will be untracked

🔹 4. Stage File
git add app.txt

👉 Moves file to staging area (ready for commit)

🔹 5. Commit File
git commit -m "Added app.txt file"

👉 Saves snapshot in Git history
📌 Commit = permanent record of changes

🔹 6. Modify File
echo "This is updated content" >> app.txt

👉 Adds new content to file

🔹 7. View Changes (Difference)
git diff

👉 Shows difference between:

Last commit
Current changes
🔹 8. Stage Updated File
git add app.txt

👉 Adds modified file to staging

🔹 9. Commit Updated Changes
git commit -m "Updated app.txt content"

👉 Saves updated version in history

🔹 10. Create a New Branch (dev)
git branch dev

👉 Creates a new branch named dev

🔹 11. Switch to dev Branch
git checkout dev

👉 Moves you to dev branch

💡 (Shortcut command)

git checkout -b dev

👉 Creates + switches branch in one step

🔹 12. Make Changes in dev Branch
echo "Development changes" >> app.txt
git add app.txt
git commit -m "Changes in dev branch"

👉 These changes exist only in dev branch

🔹 13. Switch Back to main Branch
git checkout main

👉 Goes back to main branch

📌 You will NOT see dev changes here

🔹 14. Compare Branches
git diff main dev

👉 Shows difference between:

main branch
dev branch
🔹 15. View All Branches
git branch

👉 Shows all branches
👉 Current branch will have *

🔹 (Optional) Merge dev into main
git merge dev

=================================================
2.
Branching and Isolation
• Create a dev branch using git branch
• Switch branches using git checkout
• Make changes in dev branch
• Switch back to main branch
• Compare branchesOutcome: Student understands branch isolation and parallel development.
new practical

ans:
Practical: Branching and Isolation
✅ 1. Initialize Git Repository
git init

👉 Creates a new Git repository (starting point)

✅ 2. Create a File and Commit (main branch)
echo "Main branch content" > app.txt
git add app.txt
git commit -m "Initial commit on main"

👉 Creates and saves file in main branch

✅ 3. Create a dev Branch
git branch dev

👉 Creates a new branch named dev
📌 At this point, you are still in main

✅ 4. Switch to dev Branch
git checkout dev

👉 Moves from main → dev branch

💡 Shortcut:

git checkout -b dev

👉 Create + switch in one command

✅ 5. Make Changes in dev Branch
echo "This is dev branch change" >> app.txt
git add app.txt
git commit -m "Updated file in dev branch"

👉 Changes are saved only in dev branch

✅ 6. Verify dev Branch Content
cat app.txt

👉 Output will include:

Main branch content
This is dev branch change
✅ 7. Switch Back to main Branch
git checkout main

👉 Moves back to main

✅ 8. Check File in main Branch
cat app.txt

👉 Output:

Main branch content

📌 ❗ Notice:
👉 dev changes are NOT visible in main
👉 This proves branch isolation

✅ 9. Compare main and dev Branch
git diff main dev

👉 Shows differences between branches

✅ 10. Show All Branches
git branch

======================================
3.
Merging and Conflict Handling
• Merge dev branch into main using git merge
• Perform fast-forward merge
• Create conflicting changes in two branches
• Resolve merge conflicts manually
• Commit resolved changes
new practical

ans:
Practical: Merging and Conflict Handling
✅ 1. Initialize Repository
git init

👉 Creates a new Git repository

✅ 2. Create File and First Commit (main)
echo "Line 1: Hello" > app.txt
git add app.txt
git commit -m "Initial commit on main"

👉 Base file created in main branch

🔸 PART A: Fast-Forward Merge
✅ 3. Create and Switch to dev Branch
git checkout -b dev

👉 Creates and switches to dev

✅ 4. Make Changes in dev
echo "Line 2: Added in dev" >> app.txt
git add app.txt
git commit -m "Added line in dev"
✅ 5. Switch to main
git checkout main
✅ 6. Merge dev into main (Fast-Forward)
git merge dev

👉 Since no new commits in main, Git performs fast-forward merge

📌 Meaning:

main simply moves forward to dev
No conflict, no extra commit
🔸 PART B: Conflict Handling
✅ 7. Create Conflict Scenario
Step 1: Create new branch
git checkout -b feature
Step 2: Modify same line in feature
echo "Line 1: Modified in feature branch" > app.txt
git add app.txt
git commit -m "Feature branch change"
✅ 8. Switch to main and Modify Same Line
git checkout main
echo "Line 1: Modified in main branch" > app.txt
git add app.txt
git commit -m "Main branch change"
✅ 9. Merge feature into main (Conflict occurs)
git merge feature

👉 Git will show:

CONFLICT (content): Merge conflict in app.txt
✅ 10. View Conflict in File

Open app.txt, you will see:

<<<<<<< HEAD
Line 1: Modified in main branch
=======
Line 1: Modified in feature branch
>>>>>>> feature

👉 This shows conflicting changes

✅ 11. Resolve Conflict Manually

Edit file like this:

Line 1: Final merged content

👉 Remove all conflict markers (<<<<<<<, =======, >>>>>>>)

✅ 12. Stage Resolved File
git add app.txt

👉 Marks conflict as resolved

✅ 13. Commit Merge
git commit -m "Resolved merge conflict"

=========================================
4.
Working with Remote Repositories
• Understand local vs remote repositories
• Configure remote using git remote add
• Clone repository using git clone
• Fetch updates using git fetch
• Pull changes using git pull
• Push changes using git push
Outcome: Student can synchronize local and remote repositories.
new practical

ans:
Practical: Working with Remote Repositories
🎯 Objective

👉 Learn how to connect local repository with remote repository and sync changes.

🔸 1. Understand Local vs Remote
Local Repository → Your computer (where you code)
Remote Repository → Online server like GitHub

📌 Work flow:
👉 Local ↔ Remote (sync using push/pull/fetch)

🔸 2. Initialize Local Repository
git init

👉 Creates a local Git repository

🔸 3. Add Remote Repository
git remote add origin https://github.com/username/repo.git

👉 Connects local repo to GitHub

📌 origin = default name for remote

🔍 Check Remote
git remote -v

👉 Shows linked remote URL

🔸 4. Clone Repository
git clone https://github.com/username/repo.git

👉 Downloads remote repo to local system

📌 Automatically:

Creates folder
Sets remote (origin)
🔸 5. Create File and Commit (Local Work)
echo "Hello Remote Git" > app.txt
git add app.txt
git commit -m "Initial commit"
🔸 6. Push Changes to Remote
git branch -M main
git push -u origin main

👉 Uploads local commits to GitHub

📌 -u sets upstream (no need to specify again)

🔸 7. Fetch Updates from Remote
git fetch

👉 Downloads changes from remote
👉 BUT does NOT merge into your branch

📌 Safe way to check updates

🔸 8. Pull Changes from Remote
git pull origin main

👉 Fetch + Merge in one step

📌 Updates your local repo with remote changes

🔸 9. Make New Changes and Push Again
echo "New line added" >> app.txt
git add app.txt
git commit -m "Updated file"
git push

👉 Sends updated changes to remote

🔸 10. View Branch Tracking
git branch -vv

=======================================
5.
GitHub Collaboration Workflow
• Create repository on GitHub
• Push local code to remote
• Clone repository to another directory
• Create a feature branch and push it
• Create pull request and review changes
• Merge pull request
new practical

ans:
Practical: GitHub Collaboration Workflow
🎯 Objective

👉 Learn how multiple developers collaborate using branches, push, pull request, and merge on GitHub

🔸 1. Create Repository on GitHub

👉 Steps (UI):

Go to GitHub
Click New Repository
Enter repo name (e.g., git-collab-demo)
Click Create Repository

📌 You will get a URL like:

https://github.com/username/git-collab-demo.git
🔸 2. Push Local Code to Remote
Initialize + Commit
git init
echo "Initial project" > app.txt
git add .
git commit -m "Initial commit"
Connect to GitHub
git remote add origin https://github.com/username/git-collab-demo.git
git branch -M main
git push -u origin main

👉 Uploads your local project to GitHub

🔸 3. Clone Repository to Another Directory
git clone https://github.com/username/git-collab-demo.git collab-copy
cd collab-copy

👉 Simulates another developer’s environment

🔸 4. Create Feature Branch and Push
git checkout -b feature-1

👉 Create + switch to new branch

echo "Feature work" >> app.txt
git add app.txt
git commit -m "Added feature"
git push origin feature-1

👉 Push feature branch to GitHub

🔸 5. Create Pull Request (PR)

👉 Steps on GitHub:

Go to repository
Click Compare & pull request
Select:
base → main
compare → feature-1
Click Create Pull Request

👉 Add title & description

🔸 6. Review Changes

👉 GitHub shows:

File differences
Added/removed lines

📌 Reviewer can:

Comment
Approve
Request changes
🔸 7. Merge Pull Request

👉 Click:
Merge Pull Request → Confirm Merge

📌 This merges feature-1 into main

🔸 8. Update Local Main Branch
git checkout main
git pull origin main

===============================
6.
Undoing Changes & Recovery
• Undo unstaged changes using git checkout
• Unstage files using git reset
• Amend commits using git commit --amend
• Use git reset (soft, mixed, hard)
• Use git revert for safe undo
• Recover commits using git reflogOutcome: Student can safely undo and recover changes.
new practical

ans:
Practical: Undoing Changes & Recovery
🎯 Objective

👉 Learn how to undo mistakes and recover lost work safely in Git

🔸 1. Setup (Create File & Commit)
git init
echo "Version 1" > app.txt
git add app.txt
git commit -m "Initial commit"
echo "Version 2" >> app.txt
git add app.txt
git commit -m "Second commit"
🔸 2. Undo Unstaged Changes (Working Directory)
echo "Temporary change" >> app.txt
git checkout -- app.txt

👉 Removes changes NOT staged
👉 Restores file to last committed state

🔸 3. Unstage Files (Staging Area)
echo "New change" >> app.txt
git add app.txt
git reset app.txt

👉 Removes file from staging area
👉 File remains modified (not deleted)

🔸 4. Amend Last Commit
git commit --amend -m "Updated second commit message"

👉 Edits last commit message or adds changes
📌 Useful for fixing mistakes in last commit

🔸 5. Use git reset (Types)
🔹 Soft Reset
git reset --soft HEAD~1

👉 Removes last commit
👉 Keeps changes in staging

🔹 Mixed Reset (Default)
git reset HEAD~1

👉 Removes last commit
👉 Keeps changes in working directory (unstaged)

🔹 Hard Reset ⚠️
git reset --hard HEAD~1

👉 Deletes commit + all changes permanently

❗ Dangerous (data loss)

🔸 6. Use git revert (Safe Undo)
git revert HEAD

👉 Creates a new commit that undoes previous commit
👉 Safe for shared repositories

🔸 7. Recover Lost Commits (git reflog)
git reflog

👉 Shows history of all actions (even deleted commits)

Example:

abc123 HEAD@{1}: commit: Second commit
🔹 Recover Commit
git reset --hard abc123

=============================
7.
Git Hooks for Automation
• Understand client-side hooks
• Create pre-commit hook to run lint checks
• Create pre-push hook to run tests
• Automate validation before commits
• Explore post-merge hook usage
new practical

ans:
Practical: Git Hooks for Automation
🎯 Objective

👉 Automate tasks (lint, tests, validation) using Git Hooks

🔸 1. Understand Git Hooks

👉 Git Hooks = scripts that run automatically on Git events
👉 Located inside:

.git/hooks
🔹 Types:
Client-side hooks → run on your system (pre-commit, pre-push, etc.)
Server-side hooks → run on remote server

📌 In this practical, we use client-side hooks

🔸 2. Setup Repository
git init
echo "console.log('Hello');" > app.js
git add app.js
git commit -m "Initial commit"
🔸 3. Create Pre-Commit Hook (Lint Check)
Step 1: Go to hooks folder
cd .git/hooks
Step 2: Create file pre-commit

👉 (Linux/Mac / Git Bash)

touch pre-commit

👉 (Windows PowerShell)

New-Item pre-commit -ItemType File
Step 3: Add Script

Open pre-commit file and add:

#!/bin/sh
echo "Running lint check..."

# Example: check if file contains 'console.log'
if grep -r "console.log" .; then
  echo "❌ Lint Error: console.log found!"
  exit 1
fi

echo "✅ Lint Passed"
exit 0
Step 4: Make Executable (Linux/Mac)
chmod +x pre-commit
🔍 Result:

👉 If lint fails → commit blocked
👉 If passes → commit allowed

🔸 4. Test Pre-Commit Hook
echo "console.log('debug');" >> app.js
git add app.js
git commit -m "Test lint"

👉 ❌ Commit will fail (because console.log found)

🔸 5. Create Pre-Push Hook (Run Tests)
Step 1: Create file
cd .git/hooks
touch pre-push
Step 2: Add Script
#!/bin/sh
echo "Running tests before push..."

# Example test condition
if [ -f "fail.txt" ]; then
  echo "❌ Tests failed!"
  exit 1
fi

echo "✅ Tests passed"
exit 0
Step 3: Make Executable
chmod +x pre-push
🔍 Result:

👉 Push blocked if test fails
👉 Push allowed if passes

🔸 6. Automate Validation

👉 Hooks ensure:

Code quality (lint)
Testing before push
Prevent bad commits

📌 Fully automatic (no manual step)

🔸 7. Post-Merge Hook (After Merge Action)
Create file:
touch post-merge
Add Script:
#!/bin/sh
echo "Merge completed!"

# Example: install dependencies
echo "Installing dependencies..."

=====================
8.Quetion
Initialize and Track Files

Initialize a Git repo, Create a file, Check status, Stage file, Commit changes, Modify file, View difference, Commit again.

ans:
1. Initialize Git Repository
git init

👉 Creates a new Git repository in the current folder
👉 A hidden .git directory is created to store version history

🔸 2. Create a File
echo "Hello Git" > app.txt

👉 Creates a file app.txt with initial content

🔸 3. Check Repository Status
git status

👉 Shows current state of repository
👉 app.txt will appear as untracked file

🔸 4. Stage the File
git add app.txt

👉 Moves file to staging area
👉 Now file is ready to be committed

🔸 5. Commit Changes
git commit -m "Added app.txt file"

👉 Saves file in Git history
👉 First snapshot is created

🔸 6. Modify the File
echo "This is new content" >> app.txt

👉 Adds new line to existing file

🔸 7. View Difference
git diff

👉 Shows difference between:

Last committed version
Current modified version
🔸 8. Stage Modified File
git add app.txt

👉 Adds updated file to staging area

🔸 9. Commit Again
git commit -m "Updated app.txt content"

==================================
9.Question
Branching and Isolation
· Create dev branch, Switch branches, make changes in dev, Switch back to main, Compare branches
· Delete local branch, Delete remote branch, Remove merged branches, Clean unused branches, Verify branch list

ans:
PART A: Branch Creation & Isolation
✅ 1. Initialize Repository
git init
✅ 2. Create File and Commit (main)
echo "Main content" > app.txt
git add app.txt
git commit -m "Initial commit on main"

👉 Base project created in main

✅ 3. Create dev Branch
git branch dev

👉 Creates new branch dev

✅ 4. Switch to dev Branch
git checkout dev

👉 Moves from main → dev

✅ 5. Make Changes in dev
echo "Change in dev branch" >> app.txt
git add app.txt
git commit -m "Updated in dev"

👉 Changes exist only in dev

✅ 6. Switch Back to main
git checkout main

👉 Returns to main branch

📌 You won’t see dev changes here → proves isolation

✅ 7. Compare Branches
git diff main dev

👉 Shows difference between branches

🔸 PART B: Branch Deletion & Cleanup
✅ 8. Delete Local Branch
git branch -d dev

👉 Deletes branch safely (only if merged)

📌 Force delete:

git branch -D dev
✅ 9. Delete Remote Branch
git push origin --delete dev

👉 Removes branch from remote repository

✅ 10. Remove Merged Branches
git branch --merged

👉 Lists merged branches

git branch -d branch_name

👉 Delete merged branches

✅ 11. Clean Unused Branches (Remote)
git fetch --prune

👉 Removes deleted remote branches from local tracking

✅ 12. Verify Branch List
git branch

👉 Shows local branches

git branch -r

👉 Shows remote branches

git branch -a

👉 Shows all branches