# CI-CD USING GITLAB

**Steps to do**
1. Create a new repo on gitlab
2. Add a new file named ".gitlab-ci.yml"
3. Access your linux server and install gitlab-runner. (doc. "")


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
