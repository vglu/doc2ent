---
title: "How to setup Postman for D365 FO"
date: 2021-02-14T22:11:00+02:00
draft: false

---

**Postman** is a popular tool for REST services. It is easy to use, to save and share environments and requests. and even to automate API requests testing.
[Here](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/third-party-service-test) you can find detailed information about steps required to setup and run requests using Postman and [here](https://www.gangsta.se/blog/entry/using-postman-for-odata-tests-in-local-d365fo-dev-machine) you can find specifics for local virtual machine setup.

It is important to note that there are 2 prerequisites.

1. **Register an application with Azure Active Directory**

Detailed information is available [here](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app) 

At minimum you should [register an application](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app#register-an-application) and [add a client secret](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).

**Note**: you have to record the `client_secret` value as it is shown only once. Alternatively you can always add a new client secret and use it instead.

2. **Register your application in D365**

`Client_id` created in previous step must be added into D365, detailed steps are described [here](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/services-home-page#register-your-external-application) 


You can download and import our environment template into Postman and replace values for the variables `tenant_id`, `client_id`, `client_secret` with your data. Please also check `resource` variable as url may deviate in your case:

![IMG](/usefull/how-to-setup-postman-for-d365-fo/PostmanSetup001ImportEnvironment.png)

After that you can download and import our collection of requests. Requests can be easily duplicated and extended. 

Login request must be executed first to obtain `access_token` and it has special code in **Tests** to save `access_token` to environment variable called `bearerToken`:
![IMG](/usefull/how-to-setup-postman-for-d365-fo/PostmanSetup002LoginRequestCode.png)

After that you can execute other requests and they will use `bearerToken` variable for authorization, for example:
![IMG](/usefull/how-to-setup-postman-for-d365-fo/PostmanSetup003UsingBearerToken.png)