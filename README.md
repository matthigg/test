# One Way To Quick Start

- Navigate to your Github Overview page
- Click the "Repositories" tab at the top next to the Overview tab
- Click the green "New" button in the upper-right 
- Create a Repository name, then click the green "Create repository" button at the bottom right
- Navigate to your new github repo via your browser (e.g. github.com/matthigg/test).
- Click the green "Code" button towards the middle right
- Click the HTTPS Tab, then click the copy icon to copy the url (e.g. https.//github.com/matthig/test.git)
- Open up your terminal (type pwd to get a sense of which folder you're in)
- Unless you want to navigate somewhere else to store your newly created repo, type:

  $ git clone CTRL + V

- Hit Enter, in a few seconds your new repo should be there. You can double check and then change your directory to the new repo:

  $ ls \n
  $ cd <name of your new repo>

- There's probably one branch named main, you can check with:

  > git branch

- The "origin" remote has probably been set up. To double check it:

  > git remote show origin

- This should display your newly created github repo's url twice -- once as the Fetch URL and once as the Push URL. This means that you'll push and pull/fetch updates from this location.

- From here make a new branch, type:

  > git checkout -b test-branch

- Check if there are any files in your new repo. Unless you chose to create a README.md file there might not be. Either way, create a new file & open it with 1 command:

  > code test-file.txt

- Write something in the file and save it (depending on your IDE settings the file may autosave, either way make sure it's saved).

- Now we'll commit the change to our new branch, test-branch. This commit will include both creating the file and editing it. First check out your git status. Type:

  > git status
  > git add .
  > git status

- You can see how the "status" of your git files changed. When you create new files and immediately type `git status` you'll see them show up in red (depending on your IDE, they show up as red in mine) as "Untracked files". When you modify existing files they'll show up in red as "Changes not staged for commit". Using `git add .` to add them all moves them from the "red" stage to the "green" stage, ie. staged. 

- If you make a mistake and want to unstage your changes type `git restore --staged .` to unstage everything, or `git restore --staged <filename>` for individual files.

- If you then want to undo changes not staged for commit, type `git restore .` for all or `git restore <filename>` for specific files. If you want to delete newly created untracked files type `git clean -fd`. 

- Anyways let's add everything to our commit. So back to this step:

  > git status
  > git add .
  > git status

- Now we'll commit these staged changes with:

  > git commit --message "enter any message here"

- Your changes should be commited, check the git log to see a) your new commit message and b) a commit hash that git generates for the commit to identify it. This can come in useful later.

  > git log
  > git log --oneline -5 (easier to read, enter any number of lines, I just chose 5)

- No we'll push your new branch with your new changes to the remote repo. Unless your repo is private these changes are visible to anyone.

  > git push -u origin test-branch

- View your repo in your web browser. You might see an info banner pop up that says "test-branch has recent pushes x seconds ago". In the same banner there's a green button that says "Compare & pull request". Click that.

- The "Open a pull request" page appears. Near the top you should see an arrow pointing from RIGHT to LEFT, where the test-branch on the right is our new feature branch, and the main branch on the left is the base branch. We want to push changes from our feature branch into the main branch, so we can leave this as-is.

- Add an optional title and description, then click the green "Create pull request" button.

- At this point you'd wait for other people to review your code but since it's just us, click the green "Merge pull request" button.

- Click the "Confirm merge" button.

- Now your remote feature branch has been merged into the remote main branch, and the remote feature branch (test-branch) was automatically deleted.

- Type:

  > git branch

- You'll see that your local test-branch is still there (and you're still on it) so we can see that the branches in the remote repo are probably out of sync with what we have locally. Change to the main branch:

  > git checkout main

- You'll probably see that your test file has been deleted. Check your directory to confirm:

  > ls

- Lets get the updated main branch. Type:

  > git pull

- Now your newly created test file should appear. At this point it was created in your local feature branch, pushed up to a repo, merged into the main branch, and you've pulled it from the remote repo.
