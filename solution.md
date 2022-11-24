## Git Webhook
This trigger builds based on git event(commits, push, branch creation etc).

1. Copy jenkins_url:8080 and add to webhook under your repository settings.

![]()

2. In jenkins Job Configuration, select `GitHub hook trigger for GITScm polling`, and save

![]()

3. Push changes to the git repo to trigger job