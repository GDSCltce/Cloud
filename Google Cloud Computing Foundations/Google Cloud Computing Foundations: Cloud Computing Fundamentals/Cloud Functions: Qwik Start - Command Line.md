# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell

```cmd
export REGION=
```
Just copy the region from the task 1 step 1 command

```cmd
gcloud config set compute/region $REGION
mkdir gcf_hello_world
cd gcf_hello_world
cat > index.js << EOF
exports.helloWorld = (data, context) => {
const pubSubMessage = data;
const name = pubSubMessage.data
    ? Buffer.from(pubSubMessage.data, 'base64').toString() : "Hello World";
console.log("My Cloud Function: "+name);
};
EOF
gsutil mb -p $DEVSHELL_PROJECT_ID gs://$DEVSHELL_PROJECT_ID
gcloud functions deploy helloWorld \
--stage-bucket $DEVSHELL_PROJECT_ID \
--trigger-topic hello_world \
--runtime nodejs20
```

# check my progress you will get 100/100
## Hurray you are done with the lab
