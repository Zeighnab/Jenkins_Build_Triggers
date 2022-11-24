## Git Webhook
This trigger builds based on git event(commits, push, branch creation etc).

1. Copy jenkins_url:8080 and add to webhook under your repository settings.

![]()

2. In jenkins Job Configuration, select `GitHub hook trigger for GITScm polling`, and save

![]()

3. Push changes to the git repo to trigger job

![]()

## Poll SCM
Jenkins tracks github commit according to schedules

1. In jenkins Job Configuration, select `Poll SCM`, write the scheduled time to run the job, and save

![]()

Commit changes to the git repo

