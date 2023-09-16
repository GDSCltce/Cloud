# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell

```cmd
export ZONE=
```
Copy the zone from task 1 step 7 instructions
```
export REGION=${ZONE::-2}
gcloud sql instances create myinstance \
--database-version=MYSQL_8_0 \
--tier=db-n1-standard-4 \
--region=$REGION
gcloud sql connect myinstance --user=root
```
Press Enter to continue when ask to enter password
```
CREATE DATABASE guestbook;
```
