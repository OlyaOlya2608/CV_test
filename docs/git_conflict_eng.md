# How to Resolve a Conflict When a File Is Changed in Both Local and Remote Repositories

A conflict in Git occurs when you try to push changes from your local repository to the remote, but the same file has also been modified remotely. </br>
To resolve the conflict:

1. [Identify the conflicting file](#identify-the-conflicting-file)
2. [Fix the conflicting file](#fix-the-conflicting-file)
3. [Push the changes to the repository](#push-the-changes-to-the-repository)

## Identify the Conflicting File

Open the terminal and run: `git status`. Git will display the branch name and the file that caused the conflict.

Example output:
```
On branch <branch_name>
You have unmerged paths.
    (fix conflicts and run "git commit")

Unmerged paths:
    (use "git add <file>..." to mark resolution)
    both modified:   <branch_name>
```
## Fix the Conflicting File

1. Open the conflicting file in a code editor or terminal. Each conflicting section will be marked with special markers:
    ```
    <<<<<< HEAD
    Your local changes
    =======
    Changes from the remote repository
    >>>>>>
    ```
2. For each conflict, decide which changes to keep:
    - **Keep local changes** — remove the markers and the remote changes.  
    - **Keep remote changes** — remove the markers and your local changes.  
    - **Keep both** — remove only the markers.  

3. Save the file.

## Push the Changes to the Repository

In the terminal:

1. Stage the resolved file: `git add <file_name>`.
2. Create a commit: `git commit -m "<short description of changes>"`.
3. Push the changes to the remote repository: `git push`.