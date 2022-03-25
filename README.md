# Learning How to Merge Conflicts

While working on your capstone projects, you will likely try to merge two sets of code that git does not know how to process. These moments are referred to as merge conflicts. You will not be allowed to push/pull completely until you "resolve" the conflicts, so let's learn how to do that with this exercise. 

## Step 1: Setup a directory

- [ ] Set up a directory for the purpose of this exercise.

It does not matter what you name it or where you put it. That's up to you.

## Step 2: Connect it to git

- [ ] Open your terminal if you have not already and `cd` to your new directory.
- [ ] Tell `git` that you want your new directory to be a "git repository" by using the following command:

```bash
git init
```

If successful, you will see this:

```
Initialized empty Git repository in /<PATH-TO-YOUR-DIRECTORY>/.git/`
```

## Step 3: Make initial changes

Now that you have a git repository set up, you can make some changes to it. These changes are analogous to you working on your project. The exact changes themselves don't matter. 

Let's make a change by telling the computer we want to 
- make a new file called conflict.txt.
- add text to that file that says "'All his life, Klaus had believed that if you read enough books, you could solve any problem, but now he wasn't so sure.' -- Lemony Snicket."

- [ ] Use this command to do just that:

```bash
echo "All his life, Klaus had believed that if you read enough books, you could solve any problem, but now he wasn't so sure. -- Lemony Snicket." > conflict.txt
```

## Step 4: Stage and commit the initial changes

- [ ] Tell `git` you're ready to commit these changes by "staging" them. 

```bash
git add conflict.txt
```

- [ ] Tell `git` you're ready to save these changes within git by committing them.
```bash
git commit -m "Made an initial change"
```

## Step 5: Make a new branch

In order to intentionally create a conflict later, we will need two versions of the same repository. The way we do that is by making a branch. 

When working on your capstone projects later, you and your partners might each have their own branches. Or, you might might a branch that represents an individual feature that your team is building. 

- [ ] Make a new branch and automatically switch to that branch by using this command.

```bash
git checkout -b conflicting-branch
```

## Step 6: Make additional changes

We are going to edit the same spot in the same file. However, these edits will be different. This will later be part of the cause of the merge conflict we will need to resolve.

- [ ] Add a new quote to the end of the same file by using the following command:

```bash
echo "All my problems bow before my stubbornness. -- Amit Kalantri" >> conflict.txt
```

- [ ] Add and commit these changes at the same time by using this command:

```bash
git commit -am"Changes that we will later conflict with"
```

## Step 7: Cause conflict!
Now, we will switch back to our `master` branch. It does not have the second quote we just added. We will add different content into the same spot as where that quote is in the `conflicting-branch`.

- [ ] Add a new quote to the end of the `conflict.txt` file

```bash
echo "Nothing in life is to be feared, it is only to be understood. Now is the time to understand more, so that we may fear less. -- Marie Curie" >> conflict.txt
```

- [ ] Stage and commit these new changes. 

```bash
git commit -am"This will cause a conflict when we try to merge later on"
```

## Step 8: Attempt to merge conflicting branches

When working with partners, you'll eventually want to bring your work into one piece. That's where `merge` comes in. Let's try to merge the `conflicting-branch` with the `master` branch.

- [ ] Attempt and fail to merge.

```bash
git merge conflicting-branch
```

If you failed correctly, you should see this:

```
Auto-merging conflict.txt
CONFLICT (content): Merge conflict in conflict.txt
Automatic merge failed; fix conflicts and then commit the result.
```

## Step 9: Resolve the conflicts

Remember that errors often tell you how to fix them. In this case, we are told to `fix conflicts and then commit the result.`

This is the part most beginners get stuck on. 

- [ ] Open your directory in VSCode by using 

```bash
code . 
```

- [ ] Select either your `INCOMING CHANGES`, `CURRENT CHANGES,` or `BOTH CHANGES` to keep a particular version of the project. 

> Note: Make sure to check for the above labels, so you know which piece of code goes with each label. 

> Note: When accepting both changes, you can make additional edits to clean things up.

- [ ] Stage and commit your resolved conflict. 

> Do you remember what command(s) you can use to do this?

## You've done it!

You've officially merged a conflict. Congratulations!

The ones you face in the future will undoubtedly be trickier. To help manage that greater level of complexity, you'll want to make sure to discuss with your partners what code you do and do not want to keep. Different members will be more familiar with certain parts than others. When in doubt, talk it out.
