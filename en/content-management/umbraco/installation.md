---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

Please follow the instructions to setup Umbraco CMS Software.

The **First Step** is to install the application in an IIS test environment using WebMatrix.

1. Launch WebMatrix
2. Once the WebMatrix home page appears, click **Site from Web Gallery**.
3. The Site from Web Gallery page appears, click **Umbraco CMS**, and then click **Next**.
4. Once the Accept EULA page appears, click **I Accept** to agree to the end-user license agreement.
5. Once the Application Parameters page appears, enter information appropriate to your environment, and click **Next** and click **OK** once Deployment Details dialog box appears.
6. Once the Publishing Settings page appears, add your hosting provider and domain-specific information, and click **Validate Connection**.
7. Click **Apply**, and then click **Publish** in case of successful connection and click **Continue**.
8. Here, Umbraco Configuration Wizard will appear and you can configure the Umbraco application.
 
The **Second Step** is to build the application package from the IIS site using IIS Manager:

1. Run the following command to backup an IIS 7.0 ` %windir%\system32\inetsrv\appcmd add backup "PreMsDeploy" `
2. Open the IIS Manager by clicking Start &gt; Run and typing inetmgr.
3. In IIS Manager, expand the Server node and the Sites node, then select the Default Web Site/MyApplication.
4. In the right-hand Actions pane under **Manage Packages**, click the **Export Application…** link to launch the wizard.
5. By default, the package will contain the site or application you have selected (in this case the Default Web Site/MyApplication) and its content folders. Click on the **Manage Components** button.
6. The first row is your iisapp provider entry, which is your application. In the second row, choose the **dbFullSql** provider from the **Provider Name** drop-down. If you hover over a provider, you will see a description and example path.
7. Enter the path to your database or script file in the **Path** column.  
  (Example: “Data Source=.\\SQLExpress;Database=MyApplicationDb;User id=MyAppUser;Password=SomePassWord;” without the quotes.)
8. You’ll notice that the database now shows up in the package contents tree view. Click **Next** to continue the wizard.
9. Next you will see parameters that are generated based on the two providers that you added in the previous step. We’re going to give them names and descriptions. Select the second parameter in the list, **Parameter 2**, and click on the **Add Parameter Entry** button.
10. Now create a parameter entry that points to the connection string inside the application’s Web.config file. You will notice that the parameter entry has 3 fields to fill out.
11. Choose the type of parameter you want. In this case, we’ll choose XmlFile because we want to point to the Web.config file.
12. Enter the scope for the parameter entry. The scope is a regular expression that tells us what file to locate in the package. In this case, we’ll choose the Web.config file but we’ll add \\ to indicate the start of the file and $ to indicate the end of the file name so that Web.config.bak wouldn’t also be updated.
13. Then we’ll add a match. For an XmlFile parameter entry, the match is an xpath query that indicates a particular element or attribute in the XML file. We’ll add an xpath pointing to the connection string attribute. Click **OK** to accept the entry.
14. You now have parameters that will allow a user installing this package to set the application path (site and app name where they want this app to be installed) and change the connection string (which will be updated in 2 places, first when running the SQL script and second inside the Web.config file). Click **Next** to continue.
15. Finally, choose a location to save your package. For this example, we chose `C:\MyApplication.zip`.
16. The wizard will now complete the packaging process and save the package to disk. When it is complete, you will see a **Summary** page that gives you an overview of what actions were performed.
 
The **Third Step** is to install the application on the target server using IIS Manager:

1. Run the following command to backup IIS 7.0 server `%windir%\system32\inetsrv\appcmd add backup "PreMsDeploy"`
2. Open the IIS Manager by clicking Start &gt; Run and typing inetmgr.
3. In IIS Manager, expand the Server node and the Sites node, then select the Default Web Site.
4. In the right-hand Actions pane, click the **Import Application…** link to launch the packaging wizard.
5. Select the package that you created in the previous quick guide, MyApplication.zip, or any other package.
6. In the **Install an Application Package** dialog, you will see the application and the database.
7. On the Parameters page, enter a new application name if desired and enter a SQL connection string and then click **Next** to install the package.
8. The **Summary** page will provide a high-level overview of some items that were installed from the package.
 