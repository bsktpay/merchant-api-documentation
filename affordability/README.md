
# AffordAbility

A brief description of what this project does and who it's for


## Getting Started

add button in html. Style it according to your requirement but dont remove the Id
```bash
 <button id="BSKTPAYBUTTON" onclick="openModal()">
      Affordability with bsktpay
    </button>

```

Change Variables in script tag according to requirement

```bash
  const variables = {
        appId: "c114eb01-eca5-4147-8bf8-032a0de1891d", // application Id for getting qr code
        baseUrlForBSKTPayApplication: "https://app.stage.bsktpay.co", // base url of iframe application
        apiBaseUrl: "https://stage-customer.api.bsktpay.co", // base url for affordability api
      };
```
    
### Adding Overlay

add a div before button
```bash
  <div id="overlay"></div>
```

Add a class in styles
 
```bash
#overlay {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.7);
        display: none;
        z-index: 9999;
      }
```

Add Three Function in script tag
```bash
 function showOverlay() {
        document.getElementById("overlay").style.display = "block";
      }

      // Function to hide the background overlay
      function hideOverlay() {
        document.getElementById("overlay").style.display = "none";
      }

      function checkPopupClosed() {
        if (newWindow && newWindow.closed) {
          hideOverlay();
        } else {
          setTimeout(checkPopupClosed, 100); // Check every 100 milliseconds
        }
      }
```

call the checkPopupClosed() function open modal
```bash
if (newWindow === null) {
    alert(
        "The pop-up was blocked by the browser. Please disable the pop-up blocker and try again."
    );
    hideOverlay();
} else {
    checkPopupClosed();
}
```

## User View 

Click on a button `Affordability with bsktpay`
## Login Step

User need to verify the identification. in this step User provide his number and click Next step Then user will receive an OTP on provided number

User will see 6 boxes in which user can add received OTP numbers. Then click on next Button 
## First Step

User will see the policy page if user has logged in 
otherwise he will be redirected to the login page.

if the user has downloaded the application and logged in, he will get the affordability and the popup will close emmediately 

After Login click on show QR Code 
## Second Step

In This Section user will see a qr code created by provided application id in variable section. 
After scanning he can get application 
After Getting the application click on next button
## Final Step

This final step shows the 100% progress of your proccesses. It close the popup after getting the affordability. User will get the affordability approximately in 10 seconds

after getting the affordability user will not able to open the popup