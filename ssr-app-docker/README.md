# ssr-app-docker - AWS Elastic Beanstalk Docker platform

## Changes made

1. Switch from yarn to npm
2. Add a new script line in package.json
3. Create Docker files

## Deploy to AWS Elastic Beanstalk

### `eb init`

Initialize your AWS Elastic Beanstalk project with the following command:

```
eb init
```

Example:

```
$ eb init

Select a default region
1) us-east-1 : US East (N. Virginia)
2) us-west-1 : US West (N. California)
3) us-west-2 : US West (Oregon)
4) eu-west-1 : EU (Ireland)
5) eu-central-1 : EU (Frankfurt)
6) ap-south-1 : Asia Pacific (Mumbai)
7) ap-southeast-1 : Asia Pacific (Singapore)
8) ap-southeast-2 : Asia Pacific (Sydney)
9) ap-northeast-1 : Asia Pacific (Tokyo)
10) ap-northeast-2 : Asia Pacific (Seoul)
11) sa-east-1 : South America (Sao Paulo)
12) cn-north-1 : China (Beijing)
13) cn-northwest-1 : China (Ningxia)
14) us-east-2 : US East (Ohio)
15) ca-central-1 : Canada (Central)
16) eu-west-2 : EU (London)
17) eu-west-3 : EU (Paris)
18) eu-north-1 : EU (Stockholm)
19) ap-east-1 : Asia Pacific (Hong Kong)
20) me-south-1 : Middle East (Bahrain)
(default is 3): 1

Enter Application Name
(default is "ssr-app-docker"): ssr-app-docker
Application ssr-app-docker has been created.

It appears you are using Docker. Is this correct?
(Y/n): Y

Select a platform version.
1) Docker 18.09.9-ce
2) Docker
(default is 1): 2
Cannot setup CodeCommit because there is no Source Control setup, continuing with initialization
Do you want to set up SSH for your instances?
(Y/n): n
```

### `eb create --single`

Create your environment to deploy your React app:

```
eb create --single
```

Example:

```
$ eb create --single
Enter Environment Name
(default is ssr-app-docker-dev): ssr-app-docker-dev
Enter DNS CNAME prefix
(default is ssr-app-docker-dev): ssr-app-docker-dev
Creating application version archive "app-200412_104612".
Uploading: [##################################################] 100% Done...
Environment details for: ssr-app-docker-dev
  Application name: ssr-app-docker
  Region: us-east-1
  Deployed Version: app-200412_104612
  Environment ID: e-kp3p3ims3i
  Platform: arn:aws:elasticbeanstalk:us-east-1::platform/Docker running on 64bit Amazon Linux 2/3.0.0
  Tier: WebServer-Standard-1.0
  CNAME: ssr-app-docker-dev.us-east-1.elasticbeanstalk.com
  Updated: 2020-04-12 08:47:36.345000+00:00
Printing Status:
2020-04-12 08:47:34    INFO    createEnvironment is starting.
2020-04-12 08:47:36    INFO    Using elasticbeanstalk-us-east-1-717193739363 as Amazon S3 storage bucket for environment data.
2020-04-12 08:48:04    INFO    Created security group named: awseb-e-kp3p3ims3i-stack-AWSEBSecurityGroup-18HLISJDWFIIO
2020-04-12 08:48:19    INFO    Created EIP: 54.88.217.156
2020-04-12 08:53:16    INFO    Waiting for EC2 instances to launch. This may take a few minutes.
2020-04-12 08:55:48    INFO    Application available at ssr-app-docker-dev.us-east-1.elasticbeanstalk.com.
2020-04-12 08:55:48    INFO    Successfully launched environment: ssr-app-docker-dev
```

### `eb open`

Open you React app in your default browser with the following command:

```
eb open
```

### `eb terminate`

Don't forget to terminate the environment when you are done:

```
eb terminate
```

Example:

```
$ eb terminate
The environment "ssr-app-docker-dev" and all associated instances will be terminated.
To confirm, type the environment name: ssr-app-docker-dev
2020-04-12 08:58:29    INFO    terminateEnvironment is starting.
2020-04-12 08:58:47    INFO    Waiting for EC2 instances to terminate. This may take a few minutes.
2020-04-12 09:01:19    INFO    Deleted EIP: 54.88.217.156
2020-04-12 09:01:19    INFO    Deleted security group named: awseb-e-kp3p3ims3i-stack-AWSEBSecurityGroup-18HLISJDWFIIO
2020-04-12 09:01:21    INFO    Deleting SNS topic for environment ssr-app-docker-dev.
2020-04-12 09:01:22    INFO    terminateEnvironment completed successfully.
```
