---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Run this command to create Webiny project:

 ```
 npx create-webiny-project new-project
```

Set up the database now. Place the `.env.json` file in the root directory of your project and after changing the `MONGODB_SERVER` and `MONGODB_NAME` parameters your .env.json file should look like this:

 ```
{ <br></br>"default": {
"AWS_PROFILE": "default",
"AWS_REGION": "us-east-1",
"MONGODB_SERVER": "mongodb+srv://{YOUR_USERNAME}:{YOUR_PASSWORD}@someclustername.mongodb.net",
"MONGODB_NAME": "{YOUR_MONGODB_NAME}",
"DEBUG": true
}
}
```

Values of AWS parameters can be found from your AWS account.

Now, we need to set-up API environment locally and it may take 10 to 15 minutes.

 ```
 yarn webiny deploy api --env=local
```

Once it is completed, start the app using the following commands:

 ```
 cd apps/admin<br></br> yarn start
```

Admin app will run an installation wizard so complete every step before going next. Finally, the environment is set-up locally and you can see several ready-made apps including a **Form Builder.**

Likewise, follow the following commands to run any other app:

 ```
 cd apps/site <br></br> yarn start 
```

####  

