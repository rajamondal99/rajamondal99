# CI-CD USING GITLAB

**Steps to do**
1. Create a new repo on gitlab
2. Add a new file named ".gitlab-ci.yml"
3. Access your linux server and install gitlab-runner using binary file. (doc. "https://docs.gitlab.com/runner/install/linux-manually.html")
4. Create a runner on gitlab. (GitLab Runner is an application that works with GitLab CI/CD to run jobs in a pipeline.)
5. Register runner on your server.




  
**How to install gitlab runner?**
1. Simply download the binaries for your system:
   ```
   # Linux x86-64
   sudo curl -L --output /usr/local/bin/gitlab-runner "https://s3.dualstack.us-east-1.amazonaws.com/gitlab-runner-downloads/latest/binaries/gitlab-runner-linux-amd64"

   ```
2. Give it permissions to execute:
   ```
   sudo chmod +x /usr/local/bin/gitlab-runner
   ```
3. Create a GitLab CI user:
- *Note:-* Skip this step if you are trying to deploy odoo. Then do not create 'gitlab-runner' user, you need to use 'odoo' user to run the gitlab-runner.
   ```
   sudo useradd --comment 'GitLab Runner' --create-home gitlab-runner --shell /bin/bash
   ```
4. Install and run as service:
- For Odoo
  ```
   # Install
   sudo gitlab-runner install --user=odoo --working-directory=/home/odoo
   # Start
   sudo gitlab-runner start
   ```
- For Others
   ```
   # Install
   sudo gitlab-runner install --user=gitlab-runner --working-directory=/home/gitlab-runner
   # Start
   sudo gitlab-runner start
   ```



**How to create a runner on GitLab?**

To create a runner on GitLab, open your repo -> click on setting -> select ci-cd -> you can see the runner option, expand it -> click on new project runner.
After creating a runner you will get a token. This token needs to be registered on your server.


**How to register runner on your server?**
1. Run the register command:
   ```
   sudo gitlab-runner register
   ```
2. Enter your GitLab URL:
- For GitLab.com, the gitlab-ci coordinator URL is https://gitlab.com.
3. Enter the token you obtained to register the runner.
4. Enter a description for the runner.
5. Enter the job tags, separated by commas. In our case, we have to leave it blank.
6. Enter an optional maintenance note for the runner.
7. Enter the type of executor. In our case, we have to give 'shell'.




**.gitlab-ci.yml file code**
```
stages:
  - deploy

deploy:
  stage: deploy
  only:
    - main
  script:
    - whoami
    - pwd
    - echo "Start Work"
    - cd /odoo/custom/addons/test_cicd
    - git pull origin main
    - sudo service odoo-server restart
```
