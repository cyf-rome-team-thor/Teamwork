# Workflow
How to address common development scenarios. Not a strict set of rules but a collection of rec ipes that might be useful.

## Working on a task and you know what to do
1. Assign the task to yourself
2. Move the card into the `in progress` column
3. Start from latest code:
   ```bash
   git checkout master
   git pull origin master
   ```
4. Create a branch dedicated to this activity (you may choose a meaningful name, or the task-id, or both)
   ```bash
   git checkout -b task123--change-app-title
   ```
5. Work locally, commit changes to such branch
6. Preiodically, merge what has been merged to `master` meanwhile
   ```bash
   # while you are on task123--change-app-title branch
   git pull origin master 
   ```
6. When ready, push changes
   ```bash
   git push origin task123--change-app-title
   ```
7. Go to Github repo's page, and open a PR from `task123--change-app-title` toward `master`

## Working on a task and you DO NOT know what to do
Start by chat with people in the slack channel for quick help. In case you need longer explainations, you might:
1. Assign the task to yourself
2. Move the card into the `help needed` column
3. Expose your doubts in the related Github issue page

## Working on a task that depends on another with pending PR
Let's say you worked on `task123`, and submitted a PR. Now you want to work on `task456`, which depends on the previous task.
It's the same as _Working on a task and you know what to do_, except

3. Start from `task123--change-app-title`:
   ```bash
   git checkout task123--change-app-title
   git pull origin task123--change-app-title
   ```
4. Create a branch dedicated to this activity (you may choose a meaningful name, or the task-id, or both)
   ```bash
   git checkout -b task456--make-app-title-bigger
   ```
So now you can work on this as usual. Be careful that *this branch brings other branch's changes as well*, so if the previous changes you might change this as well.
Use this scenario wisely
