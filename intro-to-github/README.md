# How to use Git & Github

## Command lines

- Visit your parent folder/directory: `$ cd ..`
- Go into a directory: `$ cd folder_name/child_folder_name`
- Go back to your home directory: `cd ~`
- Find out where in the directory structure you are: `$ pwd`
- See what's inside a directory: `$ ls` or `$ ls directory_name`


## Getting started with Git

- Let's create a new project in Cloud 9
- Erase all the generated files in your directory
- Check to see if git is installed `$ git --version`
- Create a git repository: `$ git init`
- Create a file `$ touch hello.rb`
- Write your first line of Ruby in hello.rb `puts "hello world!"`
- Check out the status of your git repository: `$ git status`

### Staging and committing

When you check the status of your git repo, you will see in red all the changes that haven't been "staged for commit" and green what have been "staged for commit". Staging allows you to choose which changes you actually want to commit and which changes you either don't want to commit or commit later.
Committing means that you are actually making and saving your changes. Each commit has a name given by you (or your team members) so that you can track all the changes you made in a file.

- Stage all of the files in your folder to be included in your first commit: `$ git add .`
- Staging is useful because you control what will be locked into the commit
- To add individual files: `$ git add file_name`
- Make your first commit: `$ git commit -m “Some descriptive notes surrounded by quotation marks"`
- Use `$ git log` to look back at the history of this branch

### Branching

Branching is what you will use all the time. When you create a new branch, you make an **exact copy** of your repo. Each time you are making changes, it will affect this specific branch **without** affecting the master branch.
This is very useful when you have a new feature that you want to implement to a website. You will create a new branch for this specific feature, work on the code and commit changes. However the initial code from the master branch will remain unchanged. Therefore, all potential crashes are avoided.

- Make a new branch with `$ git checkout -b the-branch-will-be-named-whatever-you-type-here-no-spaces-use-hypens-plz`

- Switch branches using `$ git checkout master`. Look back at the history.

### Merging
Once you are done with all the changes you made in your branch, you are then ready to merge it with master branch.

- On your master branch, merge our other branch `$ git merge the-branch-you-named`
- on you master branch, delete our other branch `git branch ---delete the-branch-you-named`

### Resetting
Here is why Git is powerful. If your changes are not right and you need to go back to an older version of your code, it's possible. Here are the commands:

- Stash any uncommitted changes: `$ git stash`
- See a list of past commits: `$ git log`
- Revert to a past commit: `$ git reset --hard [#SHA-1 Hash ###]`

## Interacting with remote repos using Github:

### Linking your local Git repository with your Github repository
This is one of the most powerful thing Git and Github have to offer. Each time you make changes locally on your computer, you can send those changes to github through git and they will be automatically updated on your repo in the Github website.

- Visit your Github page and create a new repo with a name like `my-website`
- Copy the “HTTPS Clone URL”. Enter `$ git clone [git clone url]` in tour terminal on Cloud 9
- See your remote by typing `git remote -v`
- Push your first commit to github: `$ git push origin master`
- View your code on github

### Pull Requests: Screening your developments before releasing your code
When you are working in a team and you want people to review your code before pushing it to the master branch, you can create a pull request on github. When you create a pull request, you can ask team members to review your code, see all the changes you made and comment them.


- Let’s create a new branch where we’ll make some new changes that we’ll review before integrating into our master code base: `$ git checkout -b [your-branch-name]`
- Make some changes to your code
- Stage your changes for your commit
- Commit your changes
- Push your branch and new commit to github: `$ git push origin [your-branch-name]`
- Visit your github repo. You should see that your Github registered your pushing a new branch. Go ahead and click ‘Compare & pull request’ to submit a request to merge your code changes into your master code base. Don’t forget to include a message so that others know why they should include your changes.
- Once your pull request is open, go ahead and merge your code to the master code base.
- Problem, when we visit gh-pages, we still see the old version of your code. To update gh-pages, in the terminal, lets return to our master branch (`$ git checkout master`), pull the latest master version from github to our local repository (`$ git pull`), checkout out gh-pages branch (`$ git checkout gh-pages`), merge the updated master code-base into our gh-pages branch (`$ git merge master`), and, finally, push that updated gh-pages branch commit to github (`$ git push`)
- Visit your github gh-pages vanity url and you should see those newly made changes
