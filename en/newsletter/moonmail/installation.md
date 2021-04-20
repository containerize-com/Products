---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installing using yarn

First make sure you have installed yarn ([Install instructions](https://yarnpkg.com/en/docs/install))

Install serverless 0.5 globally:

 ```
yarn global add serverless@0.5.6
```

Install the root project dependencies:

 ```
yarn install
```

Install the API dependencies:

 ```
cd api && yarn install
```

Install the event processors' dependencies:

 ```
cd events && yarn install
```

Installing the dependencies for the rest of the services follow the same convention. You just need to cd into it and install its dependencies.

Initialize and configure the Serverless 0.5 project

 ```
sls project init -c -n your-lower-case-project-name
```

Deploy Serverless resources

Create all the needed resources in your AWS account:

 ```
sls resources deploy
```

Deploy all the Lambda functions:

 ```
sls function deploy
```

Deploy MoonMail events:

 ```
sls event deploy
```

Create the API Gateway endpoints:

 ```
sls endpoint deploy
```

#### **Explore**

You may find the following links relevant:

- [Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)
 