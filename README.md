# Detailed Git Collaboration Guide for Java Projects

## Objective

This guide demonstrates Git collaboration, including independent work on branches, collaborative branching, and resolving conflicts through GitHub.

## Prerequisites

- Java IDE and Git installed on both the instructor's and the student's machines.
- A shared GitHub repository.

## Session Outline

### Part 1: Project Initialization and Repository Setup

1. **Create and Push Java Project (Instructor)**:

   - **In the IDE**: Create a Java project with a basic class.
   - **In the Terminal**:
     - Initialize the repository: `git init`
     - Add files: `git add .`
     - Commit changes: `git commit -m "Initial commit"`
   - **On GitHub**: Create a new repository and push the local repository:
     - Link local to remote: `git remote add origin <repository URL>`
     - Push to remote: `git push -u origin master`

2. **Clone the Repository (Student)**:
   - **Student Action**: Clone the repository: `git clone <repository URL>`

### Part 2: Instructor Demonstrates Normal Workflow on a Branch

1. **Create and Work on a New Branch (Instructor)**:

   - **In the Terminal**:
     - Create a new branch: `git checkout -b feature-instructor`
     - Make changes in the IDE, then stage and commit: `git add .`, `git commit -m "Add feature"`
   - **Push and Merge**:
     - Push the branch: `git push origin feature-instructor`
     - **On GitHub**: Create and merge the pull request using "Squash and Merge"
     - Delete the branch on GitHub after merging.

2. **Update Master Branch Locally (Instructor)**:
   - **In the Terminal**:
     - Switch to master branch: `git checkout master`
     - Pull latest changes: `git pull origin master`
     - Delete local feature branch: `git branch -d feature-instructor`

### Part 3: Collaborative Work and Handling Non-Conflict Changes

1. **Both Create New Branches and Work Separately (Both)**:

   - **In the Terminal**:
     - Create new branches: `git checkout -b feature-yourname`
     - Make different changes, stage, and commit.

2. **Push, Create Pull Request, and Merge (Both)**:

   - **In the Terminal**:
     - Push the branch: `git push origin feature-yourname`
   - **On GitHub**:
     - Create and merge your own pull request using "Squash and Merge"
     - Delete the feature branch on GitHub after merging.

3. **Update Master Branch and Delete Local Branch (Both)**:
   - **In the Terminal**:
     - Switch to master: `git checkout master`
     - Pull changes: `git pull origin master`
     - Delete local branch: `git branch -d feature-yourname`

### Part 4: Handling Merge Conflicts on GitHub

1. **Create Conflicting Changes (Both)**:

   - **In the Terminal**:
     - Create new branches: `git checkout -b conflict-branch`
     - Make conflicting changes in the same part of the code, stage, and commit.

2. **Student Pushes Changes and Instructor Encounters a Conflict**:

   - **Student**: Push changes and create a pull request on GitHub.
   - **Instructor**: Merge the student's pull request.
   - **Instructor**: Pull latest master changes: `git pull origin master`, and face a conflict.

3. **Instructor Resolves Conflict on GitHub (Instructor)**:

   - **On GitHub**:
     - Attempt to merge your branch via pull request.
     - GitHub indicates a conflict. Resolve the conflict using GitHub's editor.
     - Complete the merge using "Squash and Merge."
     - Delete the feature branch on GitHub.

4. **Update Master Branch and Delete Local Branch (Instructor)**:
   - **In the Terminal**:
     - Switch to master branch: `git checkout master`
     - Pull latest changes: `git pull origin master`
     - Delete local conflict branch: `git branch -d conflict-branch`
