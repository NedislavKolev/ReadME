# GitLab hosted on Scaleway instance 

**1. Availability Zone**
- `PARIS - PAR 1`

**2. Type of Instance**
- Development
  - `DEV1-M`

**3. Choose an Image**
- InstantApps
  - `GitLab`

**4. Add volumes**
- GitLab does not need extra storage
  
**5. Name of Instance**
- For example
  - `scw-gitlab-manik`

**6. SSH Keys**
- Public SSH Key of the people who will have access to the instance

**7. Access GitLab**
- Type the public IP Address in your browser 
- Setup root account

<hr>
<hr>

# How to push project to GitLab

- Create project in GitLab

- On your host machine:

`$ cd to desired folder (root folder of project)`

`$ git init`

`$ git remote <add gitlab-origin <project url>`

`$ git add .`

`$ git status`

`$ git commit -m "Hello Commit"`

`$ git push -u gitlab-origin master`

<hr>
<hr>

# Ubuntu hosted on Scaleway instance
### Ubuntu is required for GitLab Runners

**1. Availability Zone**
- `PARIS - PAR 1`

**2. Type of Instance**
- Development
    - `DEV1-M`

**3. Choose an Image**
- OS Images
    - `Ubuntu 20.04 Focal Fossa`

**4. Add volumes**
- Ubuntu does not need extra storage

**5. Name of Instance**
- For example
    - `scw-ubuntu-manik`

**6. SSH Keys**
- Public SSH Key of the people who will have access to the instance

**7. Access GitLab**
- ssh root@[public IP Address]

<hr>
<hr>

#How to install and configure GitLab Runner for CI/CD

###Install using Linux Repository

**_[Before installing GitLab Runner install Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04)_**


$ `curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh" | sudo bash`

$ `sudo apt-get install gitlab-runner`

$ `sudo gitlab-runner register`

$ `sudo nano /etc/gitlab-runner/config.toml`

**Add these two lines to the configuration of the runner:**
<hr>
clone_url = ["public dns from scaleway"]
<hr>
extra_hosts = ["public dns from scaleway:IP addres of GitLab"]
<hr>


