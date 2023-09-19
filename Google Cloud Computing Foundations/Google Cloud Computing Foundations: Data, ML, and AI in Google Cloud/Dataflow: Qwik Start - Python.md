# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell
```cmd
export REGION=
```
Copy the region from the instructions given in the set up and requirements
```cmd
gcloud config set compute/region $REGION
gsutil mb gs://$DEVSHELL_PROJECT_ID-bucket/
gcloud services disable dataflow.googleapis.com
gcloud services enable dataflow.googleapis.com
docker run -it -e DEVSHELL_PROJECT_ID=$DEVSHELL_PROJECT_ID -e REGION=$REGION python:3.9 /bin/bash -c '
pip install "apache-beam[gcp]"==2.42.0 && \
python -m apache_beam.examples.wordcount --output OUTPUT_FILE && \
HUSTLER=gs://$DEVSHELL_PROJECT_ID-bucket && \
python -m apache_beam.examples.wordcount --project $DEVSHELL_PROJECT_ID \
  --runner DataflowRunner \
  --staging_location $HUSTLER/staging \
  --temp_location $HUSTLER/temp \
  --output $HUSTLER/results/output \
  --region $REGION
'
```
# check my progress you will get 100/100
## Hurray you are done with the lab
