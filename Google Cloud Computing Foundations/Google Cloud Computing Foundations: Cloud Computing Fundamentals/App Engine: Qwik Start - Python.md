# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell

```cmd
gcloud services enable appengine.googleapis.com
git clone https://github.com/GoogleCloudPlatform/python-docs-samples.git
cd python-docs-samples/appengine/standard_python3/hello_world
sed -i 's/Hello World!/Hello, Cruel World!/g' main.py
gcloud app deploy
```
# When it will ask for region then go to task 5 step 2 instructions and properly write that no in google console

```cmd
[1] asia-east1    (supports standard and flexible)
 [2] asia-northeast1 (supports standard and flexible and search_api)
 [3] asia-south1   (supports standard and flexible and search_api)
 [4] asia-southeast1 (supports standard and flexible)
 [5] australia-southeast1 (supports standard and flexible and search_api)
 [6] europe-central2 (supports standard and flexible)
 [7] europe-west   (supports standard and flexible and search_api)
 [8] europe-west2  (supports standard and flexible and search_api)
 [9] europe-west3  (supports standard and flexible and search_api)
 [10] us-central    (supports standard and flexible and search_api)
 [11] us-east1      (supports standard and flexible and search_api)
 [12] us-east4      (supports standard and flexible and search_api)
 [13] us-west1      (supports standard and flexible)
 [14] us-west2      (supports standard and flexible and search_api)
 [15] us-west3      (supports standard and flexible and search_api)
 [16] us-west4      (supports standard and flexible and search_api)
 [17] cancel
```

 # For eg if your region is us-east1 then type 11
