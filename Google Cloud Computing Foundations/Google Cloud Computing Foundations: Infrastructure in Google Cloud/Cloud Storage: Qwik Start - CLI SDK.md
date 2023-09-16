# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell

```cmd
gsutil mb gs://$DEVSHELL_PROJECT_ID
curl https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Ada_Lovelace_portrait.jpg/800px-Ada_Lovelace_portrait.jpg --output ada.jpg
gsutil cp ada.jpg gs://$DEVSHELL_PROJECT_ID
rm ada.jpg
gsutil cp -r gs://$DEVSHELL_PROJECT_ID/ada.jpg .
gsutil cp gs://$DEVSHELL_PROJECT_ID/ada.jpg gs://$DEVSHELL_PROJECT_ID/image-folder/
gsutil acl ch -u AllUsers:R gs://$DEVSHELL_PROJECT_ID/ada.jpg
```
# check my progress you will get 100/100
## Hurray you are done with the lab
