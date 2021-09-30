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

#### On Github
1. With your Github-Pro account, create a new **private** repository, preferably with the same name as
the assignment you want to do in pair, for example `1-html-css`. This
repository will have a clone url like the one below
<!-- - With `https`: -->
   ```
   https://github.com/student-A/1-html-css.git
   ```
<!-- - With `ssh`: -->
<!--    ``` -->
<!--    git@github.com:student-A/1-html-css.git -->
<!--    ``` -->
2. Student A now has to add their pair as a collaborator on this repo, so that
   they can both access the newly created repo. To do so, they must go on the
   github page of the newly created repo, Settings->Manage Access->Private
   Repository->Manage, and then insert the name of the github account of their
   pair.

#### On your laptop

3. Clone the official Github-Classroom repo. See the line below as an example.
    ```
    git clone https://github.com/USI-Web-Atelier-2021/1-html-css-student-A.git
    ```
4. Change the url settings of the local git repo so that now it pulls from the
   newly created common private repository (you can do either with `https` or `ssh`).
   <!-- - With `https`: -->
   ```
   git remote set-url origin https://github.com/student-A/1-html-css.git
   ```
   <!-- - With `ssh`: -->
   <!--     ``` -->
   <!--     git remote set-url origin git@github.com:student-A/1-html-css.git -->
   <!--     ``` -->
    To check if you have completed this step successfully try the command
    ```
    git remote -v
    ```
    and the output should something like

   <!-- - With `https`: -->
   ```
   origin https://github.com/student-A/1-html-css.git(fetch)
   origin https://github.com/student-A/1-html-css.git(push)
   ```
   <!-- - With `ssh`: -->
   <!--     ``` -->
   <!--     origin git@github.com:student-A/1-html-css.git(fetch) -->
   <!--     origin git@github.com:student-A/1-html-css.git(push) -->
   <!--     ``` -->
5. Add back the official Github-Classroom repository (be careful to add **your
   own** repo, and not the one of your teammate) as a push remote so that all
   the changes made are stored in the official repo.
   ```
   git remote set-url --add origin https://github.com/USI-Web-Atelier-2021/1-html-css-student-A.git
   ```
    To check if you have completed this step successfully try the command
    ```
    git remote -v
    ```
    and the output should something like

   <!-- - With `https`: -->
   ```
   origin https://github.com/student-A/1-html-css.git(fetch)
   origin https://github.com/student-A/1-html-css.git(push)
   origin https://github.com/USI-Web-Atelier-2021/1-html-css-student-A.git(push)
   ```
   <!-- - With `ssh`: -->
   <!--     ``` -->
   <!--     origin git@github.com:student-A/1-html-css.git(fetch) -->
   <!--     origin git@github.com:student-A/1-html-css.git(push) -->
   <!--     origin git@github.com:USI-Web-Atelier-2021/1-html-css-student-A.git(push) -->
   <!--     ``` -->
6. Student B now just has to follow steps 1 through 3, but using their own
   `USI-Web-Atelier` github repo


    ```
    git pull --allow-unrelated-histories
   ```
   https://github.com/USI-Web-Atelier-2021/1-html-css-student-B.git
   ```


## Negative points
- The process has to be repeated at every assignment.
- The process of having a pro-github account to have access to private repos can
    be a bit involved.
- There might be some plagiarism issues if a student doesn't setup the private
    repository correctly.
