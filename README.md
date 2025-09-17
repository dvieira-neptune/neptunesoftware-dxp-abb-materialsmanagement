# neptunesoftware-dxp-abb-materialsmanagement
Materials Management


# How to connect the app to SAP via Neptune DXP SAP Edition 

# Step 1. Copying & Pasting the ABAP code included in the app repository 
In this example you'll find 3 files, each containing ABAP code needed to create the custom Z interfaces and data provider class.
Start by copying the abap code for each of the “ZIF” interfaces to the transaction code SE24 in SAP. 

Then, copy the abap code of the “ZCL” data provider class to the transaction code SE24 in SAP. This is how the imported class should look like: 
<img width="1776" height="1316" alt="image" src="https://github.com/user-attachments/assets/115c945b-0768-45cc-acd2-94ffe5c31e2c" />


# Step 2. Access the Neptune cockpit & using the API Factory 

After successfully importing the abap interfaces and data provider class, access the Neptune cockpit via the transaction code “/n/NEPTUNE/COCKPIT”. 

Once inside the cockpit, access the “API Factory” tool and select the newly created abap class (the API name will be the same as the created abap class in SAP) 
<img width="1765" height="529" alt="image" src="https://github.com/user-attachments/assets/320d447f-6a27-4554-80ff-c9fa2caac275" />


Click on the “Policy” tab and set the “Unrestricted API Engine” to “Yes” (In case that you want to have a specific set of Users to use this API, you can simply just add your policy via the “Add” button and set the “Unrestricted API Engine” to “No”). 
<img width="1006" height="602" alt="image" src="https://github.com/user-attachments/assets/4ba16006-88d1-465b-ab43-414269e33afc" /> 

Now you can start testing your API before consuming it in Neptune DXP Open Edition via the “SWAGGER UI” tab. 
<img width="1815" height="1142" alt="image" src="https://github.com/user-attachments/assets/83297896-e82c-4cff-ad6e-51ff9a8fed5c" />

<img width="1754" height="1076" alt="image" src="https://github.com/user-attachments/assets/52915d91-f937-40fb-b567-b80bc9cfc847" />


 

# Step 3. Connecting the included API in Open Edition to the newly created API Factory API in SAP Edition 

In Neptune DXP Open Edition, you’ll see an API that’s already included when downloading the template from the marketplace. All the operations and definitions are also pre-configured as well. You just need to change the “https://Your_SAP_Edition_URL.neptune-software.com/neptune/api/dynamic/zcl_nad_mm_pr_create_tmp” to your own endpoint that’s available in the API Factory tool in SAP Edition. 
<img width="1779" height="1166" alt="image" src="https://github.com/user-attachments/assets/45e3f798-97fa-4afe-af0e-38a7c80f76cc" /> 

You can find the newly created API endpoint in SAP Edition via the API Factory tool in the SWAGGER UI tab. In the image below, you can use one of the 2 highlighted URLs to apply to your API endpoint in Neptune DXP Open Edition. 
<img width="1678" height="625" alt="image" src="https://github.com/user-attachments/assets/1e290261-3c69-43ca-bd3c-b22766e94907" /> 

And then in the API Designer tool of Neptune DXP Open Edition, apply the new endpoint and save the changes:
<img width="3671" height="666" alt="image" src="https://github.com/user-attachments/assets/a3239213-139f-452a-ba7d-78a8b2799c39" />

As a last step, the “Enable Proxy” and “Use in App Designer” checkboxes are already selected by default. You just need to add Proxy authentication (as you are accessing SAP externally).  

To add authentication to this API (The authentication will be based on an existing SAP User, you can create new types of authentications via the “Proxy Authentication” tool). 
<img width="1816" height="581" alt="image" src="https://github.com/user-attachments/assets/a3f948ac-6ef0-46af-921d-d3a226e73438" />

Now the API is ready to be consumed in Neptune DXP Open Edition, for example, in the “App Designer” tool. 
