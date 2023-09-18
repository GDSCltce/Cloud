# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell
```cmd
export ZONE=
```
Copy zone from task 1 step 2 instruction
```cmd
gcloud compute instances create lamp-1-vm \
--zone=$ZONE \
--machine-type=e2-medium \
--image-project=debian-cloud \
--image-family=debian-11 \
--tags=http-server
gcloud compute firewall-rules create allow-http \
--action=ALLOW \
--direction=INGRESS \
--rules=tcp:80 \
--source-ranges=0.0.0.0/0 \
--target-tags=http-server
gcloud compute ssh lamp-1-vm --zone=$ZONE
```
# Type Y and press three times enter when the lab show do you want to continue
```cmd
sudo apt-get update
sudo apt-get install apache2 php7.0
sudo service apache2 restart
curl -sSO https://dl.google.com/cloudagents/add-google-cloud-ops-agent-repo.sh
sudo bash add-google-cloud-ops-agent-repo.sh --also-install
sudo apt-get update
```
## Now do 3 and 4 task manually
# check my progress you will get 100/100
## Hurray you are done with the lab
