# Solution to having two separate repositories

## Overview

### Before

![before](./schema_solution_separate_repos_before.png)

### After
![after](./schema_solution_separate_repos_after.png)

## Solution

### Requirements

Having a Github-Pro account (available for university students freely) to
be able to create **private repositories** hosted on Github.

### Step-by-step solution

The solution stated here are with the `ssh` github urls, if you want the
`https` version, see the [README.md](./READM.md) file.

#### Student A

##### On Github
1. With your Github-Pro account, create a new **private** repository, preferably with the same name as
the assignment you want to do in pair, for example `1-html-css`. This
repository will have a clone url like the one below
   ```
   https://github.com/student-A/1-html-css.git
   ```
2. Add Student B as a collaborator on this repo, so that you can both access
   the newly created repo. To do so, go on the github page of the
   newly created repo, Settings->Manage Access->Invite a collaborator, and
   then insert the name of the github account Student B.

##### On your laptop

3. Clone the official Github-Classroom repo. See the line below as an example.
   ```
   git clone git@github.com:USI-Web-Atelier-2021/1-html-css-student-A.git
   ```
4. Change the url settings of the local git repo so that now it pulls from the
   newly created common private repository (you can do either with `https` or `ssh`).
   ```
   git remote set-url origin git@github.com:student-A/1-html-css.git
   ```
   To check if you have completed this step successfully try the command
   ```
   git remote -v
   ```
   and the output should something like
   ```
   origin git@github.com:student-A/1-html-css.git(fetch)
   origin git@github.com:student-A/1-html-css.git(push)
   ```
5. Add back the official Github-Classroom repository (be careful to add **your
   own** repo, and not the one of your teammate) as a push remote so that all
   the changes made are stored in the official repo.
   ```
   git remote set-url --add origin git@github.com:USI-Web-Atelier-2021/1-html-css-student-A.git
   ```
    To check if you have completed this step successfully try the command
    ```
    git remote -v
    ```
    and the output should something like
   ```
   origin git@github.com:student-A/1-html-css.git(fetch)
   origin git@github.com:student-A/1-html-css.git(push)
   origin git@github.com:USI-Web-Atelier-2021/1-html-css-student-A.git(push)
   ```
6. Push the local repo to the newly created one
   ```
   git push -u origin master
   ```
#### Student B

7. Accept the invitation of Student A to collaborate on the newly created
   private repo (the invitation should be located in your USI email inbox).
8. Clone the repo created by Student A
    ```
    git clone git@github.com:student-A/1-html-css.git
    ```
9. Add the official Github-Classroom repository (be careful to add **your
   own** repo, and not the one of your teammate) as a push remote so that all
   the changes made are stored in the official repo.
   ```
   git remote set-url --add origin git@github.com:USI-Web-Atelier-2021/1-html-css-student-A.git
   ```
   To check if you have completed this step successfully try the command
   ```
   git remote -v
   ```
    and the output should something like
   ```
   origin git@github.com:student-A/1-html-css.git(fetch)
   origin git@github.com:student-A/1-html-css.git(push)
   origin git@github.com:USI-Web-Atelier-2021/1-html-css-student-B.git(push)
   ```
10. Force a push so that your local repo is the same as the official repo
    ```
    git push -fu origin master
    ```
    (in some cases the default branch is called `main`, if the previous command
    failed, try to replace `master` with `main`).

### You're done!
Now every time you want to upload your commits, you can just perform 
```
git push
```
and all of them will be uploaded to both the Github-Classroom and the common
repository.


## Negative points
- The process has to be repeated at every assignment.
- The process of having a pro-github account to have access to private repos can
    be a bit involved.
- There might be some plagiarism issues if a student doesn't setup the private
    repository correctly.
