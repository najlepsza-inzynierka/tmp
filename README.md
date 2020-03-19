# Koronotyfikacja

## Workflow
Protocol of making changes is a must while developing a project in a bigger group. Scrum master has a better track what is current state of project - which features are still missing or what has been already done. Protocol also prevents from regression commits and pushing unreadable/uncertain code.

I suggest watching those videos first:

- GithHub workflow

  [![Alt text](https://img.youtube.com/vi/aJnFGMclhU8/0.jpg)](https://www.youtube.com/watch?v=aJnFGMclhU8)

- Automated kanban with approvers

  [![Alt text](https://img.youtube.com/vi/qRdht9CS_No/0.jpg)](https://www.youtube.com/watch?v=qRdht9CS_No)

Here is short example of how to solve isse - representation of task. Imagine that feature as a FB post, that tells us what should be implemented in our application.

### Pick issue
Every issue has unique ID. Its value is important and it will be used in next steps as {ISSUE_ID} that is equal to the number after #. If you pick issue, asign it to yourself - its a way to signalize that it is taken

![Image test](img/issue.png)

This issue has {ISSUE_ID} equal to 7. Lets implement this feature!

### Commit local changes

After Your few hours of work its time to persist your changes in repository:

```

#synchronize with remote master
git checkout master
git pull

#create issue/feature branch
git checkout -b fix/{ISSUE_ID}
git add .
git commit -m "Closed #{ISSUE_ID}
git push -u origin fix/{ISSUE_ID}
```

This commit message must follow this convenction, cause it is automated form of closing issue after merging PR into master branch. If You will not follow this naming convenction, you will have to close issue manualy. 

### Create Pull Request

![Image test](img/create-PR.png)

Pull Request is a form of notifing other colabolators that You request to make changes to master branch. Approvers will decide if changes are valid. In this case you will need only two approves. Also your changes must not contain conflicts with current master branch. If conflict occurs, pull master onto your fix/{ISSUE_ID} branch and manualy solve coflicts.

### Wait for review
Wait calm for approval of you code.

![Image test](img/add_approver.png)


As approver depending on commit content, choose right option:

![Image test](img/approve.png)

### Merge 
![Image test](img/merge.png)

Voila! Your code is now included in master branch

![Image test](img/final.png)

