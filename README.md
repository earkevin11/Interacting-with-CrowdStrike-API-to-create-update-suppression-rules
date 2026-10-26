# Interacting-with-CrowdStrike-API-to-create-update-suppression-rules

## 1. Retrieving an access token to authenticate to CrowdStrike's API
- The body will contain:
- 1. client_id
  2. client_secret
  3. grant_type
     
The client ID and client secret is from the API key we create within the Falcon CSPM portal. From there, the access key itself also needs its own permissions like Cloud Security Read or Write.
<img width="1152" height="774" alt="image" src="https://github.com/user-attachments/assets/76d9ca61-84ef-4789-bceb-f4a60839fe29" />


## 2. Use access/bearer token to GET a suppression rules
- 1. Copy and paste the access token and paste it into Authorization tab so we can use it to make a GET request
<img width="1124" height="910" alt="image" src="https://github.com/user-attachments/assets/681951a6-6931-4033-ad27-1aeee69f7bd2" />



- 2. Use CrowdStrike docs to identify what is url and parameters to retrieve our list of IDs for all of suppression rules.
  3. The URL we will use is https://api.crowdstrike.com/cloud-policies/queries/suppression-rules/v1 to retrieve all the rule IDs.
 
  <img width="777" height="897" alt="image" src="https://github.com/user-attachments/assets/3745d909-af0c-447a-b2fa-1025be639002" />

- 2. We want to know what is the suppression rule with ID = 4a353957-425a-4d4f-bfdf-fa6828185ae2
    https://api.crowdstrike.com/cloud-policies/entities/suppression-rules/v1?ids=4a353957-425a-4d4f-bfdf-fa6828185ae2

<img width="1100" height="938" alt="image" src="https://github.com/user-attachments/assets/0ae230d1-4b97-4b9a-a79c-bf5a20100fe2" />



## 3. PATCH request to add our assets to this suppression rule:
Name: Azure Virtual Machine does not have Trusted Launch enabled - Part 2
Rule ID: 4a353957-425a-4d4f-bfdf-fa6828185ae2

PATCH request to https://api.crowdstrike.com/cloud-policies/entities/suppression-rules/v1?ids=4a353957-425a-4d4f-bfdf-fa6828185ae2


<img width="1151" height="900" alt="image" src="https://github.com/user-attachments/assets/53b15854-0561-43ce-9a49-6838d801eb94" />
