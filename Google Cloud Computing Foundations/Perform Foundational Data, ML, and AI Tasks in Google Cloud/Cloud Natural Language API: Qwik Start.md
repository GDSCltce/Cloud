# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell

```cmd
export GOOGLE_CLOUD_PROJECT=$(gcloud config get-value core/project)
gcloud iam service-accounts create my-natlang-sa \
--display-name "my natural language service account"
gcloud iam service-accounts keys create ~/key.json \
--iam-account my-natlang-sa@${GOOGLE_CLOUD_PROJECT}.iam.gserviceaccount.com
gcloud compute ssh linux-instance
```
### Press `y` , `ENTER` > `ENTER` > `ENTER` > `n`, `ENTER`
```cmd
gcloud ml language analyze-entities \
--content="Michelangelo Caravaggio, Italian painter, is known for 'The Calling of Saint Matthew'." > result.json
```
# check my progress you will get 100/100
## Hurray you are done with the lab
