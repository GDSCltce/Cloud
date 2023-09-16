# Click on start lab
# Right click on google coud console and open it in incognito window
# login with your username 1 credentials
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell

```cmd
export USERNAME2=
```
copy the username 2 provided in the lab
```
touch sample.txt
gsutil mb gs://$DEVSHELL_PROJECT_ID
gsutil cp sample.txt gs://$DEVSHELL_PROJECT_ID
gcloud projects remove-iam-policy-binding $DEVSHELL_PROJECT_ID --member="user:$USERNAME2" --role="roles/viewer"
gcloud projects add-iam-policy-binding $DEVSHELL_PROJECT_ID --member="user:$USERNAME2" --role="roles/storage.objectViewer"
```
# check my progress you will get 100/100
## Hurray you are done with the lab
