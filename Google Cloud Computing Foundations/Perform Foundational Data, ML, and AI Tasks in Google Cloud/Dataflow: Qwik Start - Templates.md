# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell


```cmd
export REGION=
```
Copy the region from task 3 step 3 instructions
```cmd
gcloud services disable dataflow.googleapis.com
gcloud services enable dataflow.googleapis.com
```
```cmd
bq mk taxirides
bq mk \
--time_partitioning_field timestamp \
--schema ride_id:string,point_idx:integer,latitude:float,longitude:float,\
timestamp:timestamp,meter_reading:float,meter_increment:float,ride_status:string,\
passenger_count:integer -t taxirides.realtime
gsutil mb gs://$DEVSHELL_PROJECT_ID/
sleep 45
```
```cmd
gcloud dataflow jobs run iotflow \
--gcs-location gs://dataflow-templates/latest/PubSub_to_BigQuery \
--region $REGION \
--staging-location gs://$DEVSHELL_PROJECT_ID/temp \
--parameters inputTopic=projects/pubsub-public-data/topics/taxirides-realtime,outputTableSpec=$DEVSHELL_PROJECT_ID:taxirides.realtime
```


# check my progress you will get 100/100
## Hurray you are done with the lab
