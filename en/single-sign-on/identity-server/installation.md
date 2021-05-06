---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install directly from Nuget

You can install directly from nuget using following command:

    Install-Package IdentityServer4 -Version 4.0.4

### Install IdentityServer4 Templates

    dotnet new -i IdentityServer4.Templates  
  

Add QuickUI files and ASP.NET Identity (optional)

    dotnet new is4aspid --force  
  
  

Update ConfigureServices() method in startup.cs as below:

    services.AddControllersWithViews();  
  

Also update Configure() method in startup.cs :

    app.UseRouting();  
       
     app.UseIdentityServer();  
     app.UseAuthorization();   
     app.UseEndpoints(endpoints =>  
     {  
     endpoints.MapControllerRoute(  
     name: "default",  
     pattern: "{controller=Home}/{action=Index}/{id?}");  
     });  
  

Build and run the project

  
Browse “/.well-known/openid-configuration” to make sure discovery endpoints is up and running.

### Running in Docker

1.  Create an empty ASP.NET Core Project (Check ‘Enable Docker Support”)
2.  Make sure the project file targets Linux OS <DockerDefaultTargetOS>Linux</DockerDefaultTargetOS>
3.  Modify the docker file as below:

  
        FROM microsoft/dotnet:2.2-runtime AS base  
        WORKDIR /app  
        EXPOSE 80  
        EXPOSE 443  
           
        FROM microsoft/dotnet:2.2-sdk AS build  
        WORKDIR /src  
        COPY \[“JrTech.Identity.Web/JrTech.Identity.Web.csproj“, “JrTech.Identity.Web/”\]  
        RUN dotnet restore “JrTech.Identity.Web/JrTech.Identity.Web.csproj“  
        COPY . .  
        WORKDIR “/src/JrTech.Identity.Web”  
        RUN dotnet build “JrTech.Identity.Web.csproj” -c Release -o /app  
           
        FROM build AS publish  
        RUN dotnet publish “JrTech.Identity.Web.csproj” -c Release -o /app  
           
        FROM base AS final  
        WORKDIR /app  
        COPY –from=publish /app .  
        ENTRYPOINT \[“dotnet”, “JrTech.Identity.Web.dll”\]  
      
      
      

*   Add IdentityServer 4  by running the following command:  
      
    dotnet add package IdentityServer4
