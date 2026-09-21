   # Project Reflection: Version Control Simulation

   ## Creating and Managing Branches

   I started by creating the GitHub repository `version-control-simulation-adrian` and cloning it locally. My first challenge was running Git commands from the parent folder, which gave "not a git repository" errors. Opening the repository folder itself in VS Code fixed this. I also noticed my repository name didn't match the required convention, so I renamed it on GitHub and updated the remote with `git remote set-url`. Since an empty repository has no `main` branch, I committed and pushed a README first.

   I then created `feature/header` and committed a basic `index.html` with a header. Because `index.html` didn't exist on `main`, I created `feature/footer` from `feature/header` and added a footer there. I caught a typo in one commit message and fixed it with `git commit --amend` before pushing. Running `git log --oneline --all --graph` helped me see how the branches diverged.

   ## Handling the Merge Conflict

   To simulate a conflict, I added a different footer on `feature/header` in the same spot. Merging `feature/footer` into `main` fast-forwarded, but merging `feature/header` stopped with a conflict in `index.html`. I read the markers (`<<<<<<< HEAD`, `=======`, `>>>>>>>`), combined both lines into a single footer, removed the markers, and committed the merge. When I reviewed the file afterward, I found I had left two footer blocks, so I fixed that in a separate commit. My takeaway is that a conflict isn't an error. It's Git asking for a decision, and I should always review the file after resolving it.

   ## Pull Requests and Collaboration

   A pull request compares two branches, so I created `review/main` from the README-only commit before pushing my work. That way the pull request from `main` showed all my changes instead of being empty. I wrote a description summarizing what changed and what to check, and I commented on my own code to explain my decisions.

   Reviewing a peer's pull request meant reading code the way a reviewer would: checking commit messages, looking for leftover conflict markers, and spotting duplicate elements. Pull requests improve code quality by catching mistakes, like my duplicate footer, before they spread. They also improve collaboration because comments record why decisions were made.