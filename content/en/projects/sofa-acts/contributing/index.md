---

title: "How to contribute"
aliases: "/sofa-acts/docs/Contributing"
---

## Prerequisites

Before contributing any code, you need to know how to use the Git tools and the GitHub website.

* For the use of Git tools, refer to the [official Pro Git book](http://git-scm.com/book/zh/v1) and get familiar with it by reading the first few chapters.
* For the Git collaboration process, refer to the article [Git Workflows.](http://www.ruanyifeng.com/blog/2015/12/git-workflow.html)

## GitHub Code Contribution Process

### Submit an issue

Regardless of whether you are fixing an ACTS bug or adding an ACTS feature, submit an issue on ACTS __GitHub__ to describe the bug you are going to fix or the feature you intend to add before you submit the code. There are several advantages of doing so:

* There will not be any conflict with other developers or their plans for this project to result in repetitive work.
* The ACTS maintenance personnel will discuss the issue or new feature you submitted to determine whether the modification is necessary, or if there is any room for improvement or a better solution.
* Start code development and submit the code after an agreement is reached. This reduces the cost of communication between both parties and the number of rejected pull requests.

### Get the source code

To modify or add a feature after submitting an issue, click the `fork` button in the upper left corner to copy the master branch code to your code repository.

### Pull a branch

All ACTS modifications are performed on branches. After the modification, submit a `pull request`. The modifications will then be merged into the master branch by the project maintenance personnel after the code review.
Therefore, after getting familiar with how to get the source code, you need to:

* Download the code locally. You may select the git/https mode in this step.

   ```
   Git clone https://github.com/your account name/acts.git
   ```
* Pull a branch to prepare for code modification.

   ```
   git branch add_xxx_feature
   ```

   After the preceding command is executed, your code repository will switch to the corresponding branch. To view the current branch, execute the following command:

   ```
   git branch -a
   ```

   If you want to switch back to the master branch, execute the following command:

   ```
   git checkout -b master
   ```

   If you want to switch back to the branch, execute the following command:

   ```
   git checkout -b "branchName"
   ```

### Modify the code and submit it locally

After a branch is pulled, you can modify the code.

* After modifying the code, execute the following command to submit all modifications to your local repository:

   ```
   git commit -am 'Add xx feature'
   ```

#### When modifying the code, note the following:

* Keep the code style consistent.
* ACTS uses the Maven plug-in to keep the code style consistent. Before submitting the code, be sure to execute the following command locally.

   ```
   mvn clean compile
   ```
* Supplement unit test code.
* New modifications should have passed existing unit tests.
* Provide a new unit test to prove that the previous code has bugs and the bugs have been fixed in the new code.
Execute the following command to run all tests:

   ```
   mvn clean test
   ```

   You can also use the IDE to help run a test.

#### Other do's and don'ts

* Retain the original style of the code you are editing, especially the spaces and line feeds in the code.
* Delete useless annotations.
* Annotate the places where the logic and functionality are not easy to understand.
* Update documents in a timely manner.

### Submit the code to a remote repository

After being submitted to the local repository, the code is synchronized to a remote repository.

* Execute the following command to submit the local modification to GitHub:

   ```
   git push origin "branchname"
   ```

If you clicked the 'fork' button to get the source code, the modified code is pushed to your code repository rather than the ACTS repository.

### Submit a request for merging the code into the master branch

After submitting the code to GitHub, you can send a request to merge your modified code into ACTS' master branch code. To do so, enter the corresponding repository on your GitHub and click the `Pull Request` button in the upper right corner. Select the target branch (usually `master`), and the system will notify the ACTS maintenance personnel, who will review your code.

#### Code review

After you submit the code, it will be assigned to maintenance personnel for review. You need to wait for the review result. If you have not received a reply after several days, leave a message under the PR, and put an at (@) sign before the name of the responsible person.

The person will leave a comment containing the code review suggestions on the corresponding PR or issue. If you find the suggestions reasonable, update your patch based on the comments.

#### Merge the code into the trunk

After your code passes the review, the ACTS maintenance personnel will merge it into the ACTS' master branch. You do not need to get involved in this step. After the code is merged, you will receive a message indicating a successful merge.

