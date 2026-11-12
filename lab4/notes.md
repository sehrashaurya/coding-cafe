# Lab 4 Notes

## Question 1 - What does --global mean?
`--global` saves the setting in my user-wide Git config (C:\Users\ashus\.gitconfig), so it applies to every repository on this laptop. Without it, Git uses `--local` and saves the setting only in the current repository's `.git/config`; outside a repository it would give an error.

## Question 2 - What appeared in ls -a but not ls?
A hidden folder called `.git` appeared. It is Git's database for the project: it stores every commit and saved file version, the branch pointers, HEAD, and the repository's config.

## Question 3 - How many files is Git offering to track?
Only two entries: `README.md` and `week02/`. Nothing unfamiliar showed up. `.venv` was hidden because Python puts its own `.gitignore` inside it, and `week01` did not show because it is empty and Git does not track empty folders.

## Question 4 - What disappeared after adding .gitignore?
Nothing disappeared in my case; `.gitignore` itself was the only new entry. The lab expected `.venv/` to vanish, but it was already hidden by the `.gitignore` inside `.venv`.

## Question 5 - Should .gitignore be committed?
It should be committed. It is part of the project's setup, so anyone who clones the repository (or I on another computer) gets the same ignore rules automatically.

## Question 6 - Where did README.md move in git status?
It moved from "Untracked files" to "Changes to be committed". In the three-places model it went from the working directory into the staging area: it is ready for the next commit but not yet saved in the repository.

## Question 7 - What did git commit print?
It printed `[main (root-commit) 7e944c1] Lab work so far` and `4 files changed, 4 insertions(+)`, followed by a `create mode` line for each of the 4 new files. "root-commit" means it was the first commit.

## Question 8 - What are the first seven characters of a commit?
They are the short form of the commit's hash (e.g. `7e944c1`), a unique ID calculated from the commit's contents. It is used to refer to a specific commit, for example `git show 7e944c1`.

## Question 9 - The four steps of the loop
Edit a file, check with `git status`, stage with `git add`, and save a snapshot with `git commit`.

## Question 10 - Why is README special?
README is a standard name that GitHub looks for: if it is in the top folder, GitHub automatically shows it on the repository's front page. It is the first thing a visitor reads, so it describes the whole project.

## Question 11 - What did gh auth login do?
After I approved it in the browser, GitHub gave `gh` a login token, which it stored on my laptop. Because I chose to authenticate Git with my GitHub credentials, `git push` now uses that token automatically instead of asking for a password.

## Question 12 - What shows on the GitHub front page, and why?
The file list, and below it my README shown as a formatted page with the "Coding Cafe" heading. GitHub automatically displays `README.md` from the top folder.

## Question 13 - Did pushing change local history?
No. `git log --oneline` shows the same commits with the same hashes; pushing only copied them to GitHub. The only difference is a new `origin/main` label showing where GitHub's copy is.

## Question 14 - Private repo vs no repo
A private repository really exists on GitHub and holds a backup of my history, but only I and the people I invite (my TAs) can see it; to everyone else it shows a 404 page, as if it did not exist. If the repository did not exist at all, there would be no online copy and nobody, including the TAs, could see it.
