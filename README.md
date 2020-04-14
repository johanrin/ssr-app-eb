# ssr-app-eb - I deployed a server-side React app with AWS Elastic Beanstalk. Here’s what I learned.

I’m doing the #AWSCertified challenge and I decided to write about my journey. The purpose is to share what I learn and also the pain points I encounter during the process.

During this Easter weekend, I decided to explore AWS Elastic Beanstalk.

My objective was to deploy a basic React app using Elastic Beanstalk command line interface (EB CLI). The experience had to be simple as possible.

I decided to use [Razzle](https://github.com/jaredpalmer/razzle), a server-rendering framework, for this experiment because I think it's more flexible than Next.js. But we can easily adapt the commands explained below for other frameworks.

The repository is divided in two parts:

1. `ssr-app-docker` explaining how to deploy your React app with AWS Elastic Beanstalk Docker platform
2. `ssr-app-nodejs` explaining how to deploy your React app with AWS Elastic Beanstalk Node.js platform
