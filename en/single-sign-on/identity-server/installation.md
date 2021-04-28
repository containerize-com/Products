---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install directly from Nuget

You can install directly from nuget using following command:

 ```
Install-Package IdentityServer4 -Version 4.0.4
```

### Install IdentityServer4 Templates

dotnet new -i IdentityServer4.Templates

Add QuickUI files and ASP.NET Identity (optional)

 ```
dotnet new is4aspid --force<br></br><br></br><br></br>
```

 Update ConfigureServices() method in startup.cs as below: