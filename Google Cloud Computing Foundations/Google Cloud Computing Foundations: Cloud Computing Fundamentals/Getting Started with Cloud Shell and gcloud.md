# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell

gcloud config set compute/region REGION 
// change REGION with the step 1 region provided like (us-central1,us-east1,us-west1)

gcloud config get-value compute/region

gcloud config set compute/zone ZONE
// change ZONE with the step 3 provided zone in the lab instructions

gcloud config get-value compute/zone
gcloud config get-value project
gcloud compute project-info describe --project $(gcloud config get-value project)
export PROJECT_ID=$(gcloud config get-value project)
export ZONE=$(gcloud config get-value compute/zone)
echo -e "PROJECT ID: $PROJECT_ID\nZONE: $ZONE"
gcloud compute instances create gcelab2 --machine-type e2-medium --zone $ZONE


## Hurray you are done with the lab
