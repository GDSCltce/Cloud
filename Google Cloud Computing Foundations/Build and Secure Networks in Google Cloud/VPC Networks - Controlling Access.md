# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell
```cmd
export ZONE=
```
Copy the zone from task 1 step 3 table
```cmd
export PROJECT_ID=$(gcloud config get-value project)
gcloud compute instances create blue \
  --zone=$ZONE \
  --machine-type=e2-medium \
  --tags=web-server
gcloud compute instances create green \
  --zone=$ZONE \
  --machine-type=e2-medium 
gcloud compute firewall-rules create allow-http-web-server \
  --network=default \
  --action=ALLOW \
  --direction=INGRESS \
  --source-ranges=0.0.0.0/0 \
  --target-tags=web-server \
  --rules=tcp:80,icmp
gcloud compute instances create test-vm --machine-type=e2-micro --subnet=default --zone=$ZONE
```
### IAM & admin > Service Accounts > Create service account > Name= `Network-admin` > Role > Compute Engine > Compute Network Admin > Save
```cmd
gcloud iam service-accounts keys create key.json --iam-account=network-admin@$PROJECT_ID.iam.gserviceaccount.com
gcloud compute ssh blue --zone=$ZONE --quiet
```
```cmd
sudo apt-get install nginx-light -y
sudo sed -i 's#<h1>Welcome to nginx!</h1>#<h1>Welcome to the blue server!</h1>#' /var/www/html/index.nginx-debian.html
cat /var/www/html/index.nginx-debian.html
exit
```
```cmd
gcloud beta compute ssh green --zone=$ZONE --quiet
```
```cmd
sudo apt-get install nginx-light -y
sudo sed -i 's#<h1>Welcome to nginx!</h1>#<h1>Welcome to the Green server!</h1>#' /var/www/html/index.nginx-debian.html
cat /var/www/html/index.nginx-debian.html
```
# check my progress you will get 100/100
## Hurray you are done with the lab
