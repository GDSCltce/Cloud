# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell

```cmd
export ZONE=
```
Copy the zone from task 1 step 2 command

```
export REGION=${ZONE::-2}
gcloud config set compute/region $REGION
gcloud config set compute/zone $ZONE
gcloud container clusters create lab-cluster --machine-type=e2-medium --zone=$ZONE
gcloud container clusters get-credentials lab-cluster
kubectl create deployment hello-server --image=gcr.io/google-samples/hello-app:1.0
kubectl expose deployment hello-server --type=LoadBalancer --port 8080
```
wait for this command to run it will take time

```cmd
gcloud container clusters delete lab-cluster
```
Type Y when it ask for do you want to continue and press enter

# check my progress you will get 100/100
## Hurray you are done with the lab
