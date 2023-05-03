# task #1: automated script for creating linux users and configuring their SSH login

## pre-implementation task

- create an 5-10 length subtask list and time estimate for the following task
- if a subtask time estimate is more than 10 hours, break it down into smaller subtasks, if a subtask is less than 1 hour, merge it with another subtask.
- delegate all subtasks to team members

## specification

- automate the steps below with a bash shell script which takes the username as an argument, and asks for the password for the new user interactively
- create user on a Linux system (Ubuntu 22.04 LTS Server),
- create a private/public key pair for the user
- configure SSH to allow login with a private key only, and disable login with a password.
- make the user has their own directory for storing their authorized keys.

## notes

- configure MobaXterm to use the private key for SSH login
- document the steps in a markdown file
- test the script on a clean Ubuntu 22.04 LTS Server. recommended to use vagrant to create the test environment, so the test environment can be easily recreated, but it is not mandatory. you can use any kind of Ubuntu 20.04, including cloud, WSL, or manually installed VirtualBox instance, however the test environment should be a clean Ubuntu 22.04 LTS Server, and tests should be repeatable.
- place the automation script and all files belong to it a separate folder in the repository:

  ```
  /tools/create-users
  ```
