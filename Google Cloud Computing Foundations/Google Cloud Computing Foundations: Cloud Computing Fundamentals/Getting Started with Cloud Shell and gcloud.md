# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell

```cmd
export ZONE=
```
Paste the zone that is provided in step 3 of task 1
```cmd
gcloud compute instances create gcelab2 --machine-type e2-medium --zone $ZONE
```

## Hurray you are done with the lab
