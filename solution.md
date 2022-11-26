## Git Webhook
This trigger builds based on git event(commits, push, branch creation etc).

1. Copy jenkins_url:8080 and add to webhook under your repository settings.

![](./img/1.png)

2. In jenkins Job Configuration, select `GitHub hook trigger for GITScm polling`, and save

![](./img/2.png)

3. Push changes to the git repo to trigger job

![](./img/3.png)

## Poll SCM
Jenkins tracks github commit according to schedules

1. In jenkins Job Configuration, select `Poll SCM`, write the cron job format, and save

![](./img/4.png)

Commit changes to the git repo

![](./img/5.png)

## Scheduled Jobs
Similar to Poll SCM, the difference is it doesn't check for commits, rather it runs the job at the scheduled time

In jenkins Job Configuration, select `Build Periodically`, write the scheduled time to run the job, and save

![](./img/6.png)

## Remote Triggers
This means job can be trigger from anywhere i.e from a script, jenkins server, laptop, as long as there is network access to the job.

1. Generate Job Url
Job Configure > Trigger builds remotely (e.g., from scripts) > Give a Token name > Generate URl and Save

![](./img/7.png)

2. Generate Token for User
username button > configure > API Token > Generate > copy token-name > save username:token-name in a file

![](./img/8.png)

3. Generate CRUMB
```
wget -q --auth-no-challenge --user username --password password --output-document - 'http://JENNKINS_IP:8080/crumbIssuer/api/xml?xpath=concat(//crumbRequestField,":",//crumb)'
```

![](./img/9.png)

4. Build Job from URL
```
curl -I -X POST 'http://username:APItoken@Jenkins_IP:8080/job/JOB_NAME/build?token=TOKENNAME' -H "Jenkins-Crumb:CRUMB"
```

![](./img/10.png)

![](./img/11.png)

## Post Job Trigger
This means triggering a job after the completion of another.

1. Create a new job, and select `Build after other projects are built`, in the job configuration. Chose the other project

![](./img/12.png)

2. Go to the other project, and build. After successful build, it will trigger the new job created.

![](./img/13.png)


![](./img/14.png)




