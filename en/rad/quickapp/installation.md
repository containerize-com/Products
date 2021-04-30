---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

First clone the repo using the following command:

     git clone https://github.com/emonney/QuickApp.git

After a successful clone, run the following commands:

     dotnet restore // for ASP.NET project backend npm install // for Angular front end  

Now, go to “environment.ts” file in the ClientApp/Angular project and configure the front end url with the backend url and run the following command into the root directory to run the back end.

     dotnet run

After doing that, run the following commands to run the front end.

     cd ClientApp/ ng serve

Finally, you can access the URL [http://localhost:4200/](https://href.li/?http://localhost:4200/) into the browser.

Default admin log in:

*   Username: admin
*   Email: [admin@ebenmonney.com](mailto:admin@ebenmonney.com)
*   Password: [tempP@ss123](mailto:tempP@ss123)

Default standard log in:

*   Username: user
*   Email: [user@ebenmonney.com](mailto:user@ebenmonney.com)
*   Password: tempP@ss123
