# ssr-app-nodejs - AWS Elastic Beanstalk Node.js platform

## Changes made

1. Switch from yarn to npm
2. Customize AWS Elastic Beanstalk environment
3. Add a new script line in `package.json`
4. Solve permission denied with `.npmrc`

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
(default is "ssr-app-nodejs"): ssr-app-nodejs
Application ssr-app-nodejs has been created.

It appears you are using Node.js. Is this correct?
(Y/n): Y

Select a platform version.
1) Node.js 12 (BETA)
2) Node.js 10 (BETA)
3) Node.js
(default is 1): 3
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
(default is ssr-app-nodejs-dev): ssr-app-nodejs-dev
Enter DNS CNAME prefix
(default is ssr-app-nodejs-dev): ssr-app-nodejs-dev
Creating application version archive "app-200412_100649".
Uploading: [##################################################] 100% Done...
Environment details for: ssr-app-nodejs-dev
  Application name: ssr-app-nodejs
  Region: us-east-1
  Deployed Version: app-200412_100649
  Environment ID: e-wyzcjqwm6v
  Platform: arn:aws:elasticbeanstalk:us-east-1::platform/Node.js running on 64bit Amazon Linux/4.14.1
  Tier: WebServer-Standard-1.0
  CNAME: ssr-app-nodejs-dev.us-east-1.elasticbeanstalk.com
  Updated: 2020-04-12 08:08:14.088000+00:00
Printing Status:
2020-04-12 08:08:13    INFO    createEnvironment is starting.
2020-04-12 08:08:14    INFO    Using elasticbeanstalk-us-east-1-717193739363 as Amazon S3 storage bucket for environment data.
2020-04-12 08:08:43    INFO    Created security group named: awseb-e-wyzcjqwm6v-stack-AWSEBSecurityGroup-1BAOESKYY2P2Q
2020-04-12 08:08:59    INFO    Created EIP: 18.214.57.52
2020-04-12 08:10:04    INFO    Waiting for EC2 instances to launch. This may take a few minutes.
2020-04-12 08:11:20    INFO    Application available at ssr-app-nodejs-dev.us-east-1.elasticbeanstalk.com.
2020-04-12 08:11:20    INFO    Successfully launched environment: ssr-app-nodejs-dev
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
The environment "ssr-app-nodejs-dev" and all associated instances will be terminated.
To confirm, type the environment name: ssr-app-nodejs-dev
2020-04-12 08:34:39    INFO    terminateEnvironment is starting.
2020-04-12 08:34:57    INFO    Waiting for EC2 instances to terminate. This may take a few minutes.
2020-04-12 08:36:43    INFO    Deleted EIP: 18.214.57.52
2020-04-12 08:36:43    INFO    Deleted security group named: awseb-e-wyzcjqwm6v-stack-AWSEBSecurityGroup-1BAOESKYY2P2Q
2020-04-12 08:36:45    INFO    Deleting SNS topic for environment ssr-app-nodejs-dev.
2020-04-12 08:36:46    INFO    terminateEnvironment completed successfully.
```
