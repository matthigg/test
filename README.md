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

  git clone CTRL + V

- Hit Enter, in a few seconds your new repo should be there. You can double check and then change your directory to the new repo:

  ls
  cd <name of your new repo>

- There's probably one branch named main, you can check with:

  git branch

- The "origin" remote has probably been set up. To double check it:

  git remote show origin

- This should display your newly created github repo's url twice -- once as the Fetch URL and once as the Push URL. This means that you'll push and pull/fetch updates from this location.

- From here make a new branch, type:

  git checkout -b test-branch

- Check if there are any files in your new repo. Unless you chose to create a README.md file there might not be. Either way, create a new file & open it with 1 command:

  code test-file.txt

- Write something in the file and save it (depending on your IDE settings the file may autosave, either way make sure it's saved).

- Now we'll commit the change to our new branch, test-branch. This commit will include both creating the file and editing it. First check out your git status. Type:

  git status
  git add .
  git status

- You can see how the "status" of your git files changed. When you create new files and immediately type `git status` you'll see them show up in red (depending on your IDE, they show up as red in mine) as "Untracked files". When you modify existing files they'll show up in red as "Changes not staged for commit". Using `git add .` to add them all moves them from the "red" stage to the "green" stage, ie. staged. 

- If you make a mistake and want to unstage your changes type `git restore --staged .` to unstage everything, or `git restore --staged <filename>` for individual files.

- If you then want to undo changes not staged for commit, type `git restore .` for all or `git restore <filename>` for specific files. If you want to delete newly created untracked files type `git clean -fd`. 
