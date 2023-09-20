
# AffordAbility

A brief description of what this project does and who it's for


## Getting Started

Change Variables in script tag according to requirement

```bash
  const variables = {
        appId: "c114eb01-eca5-4147-8bf8-032a0de1891d", // application Id for getting qr code
        baseUrlForBSKTPayApplication: "https://app.stage.bsktpay.co", // base url of iframe application
        apiBaseUrl: "https://stage-customer.api.bsktpay.co", // base url for affordability api
      };
```
    
## User View 

User will see a button `Affordability with bsktpay` click it.
## First Step

First step is to verify the identification. in this step User provide his number and click Next step Then user will receive an OTP on provided number
## Second Step

User will see 6 boxes in which user can add received OTP numbers. Then click on next Button 
## Third Step
Click on Show Qr After reading policies
## Fourth Step

In This Section user will see a qr code created by provided application id in variable section. 
After scanning he can get application 
After Getting the application click on next button
## Final Step

This final step shows the 100% progress of your proccesses. It close the popup after 30 seconds and you user will get the affordability 
