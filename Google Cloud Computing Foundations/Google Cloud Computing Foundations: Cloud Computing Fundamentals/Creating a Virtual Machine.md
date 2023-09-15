# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell

```cmd
export ZONE=
```
This zone is provided in the table of task 1

```cmd
gcloud compute instances create gcelab \
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
gcloud compute instances create gcelab2 --machine-type e2-medium --zone=$ZONE
gcloud compute ssh gcelab --zone=$ZONE
```
Wait for this command to run it will take 2-3 mins type y and press double time enter 

```cmd
sudo apt-get update
sudo apt-get install -y nginx
ps auwx | grep nginx
exit
```


# check my progress you will get 100/100
## Hurray you are done with the lab
