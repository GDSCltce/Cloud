# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell

```cmd
export ZONE=
```
copy the zone from task 1 step 3 table
```cmd
export REGION=${ZONE::-2}
gcloud dataproc clusters create example-cluster \
--region=$REGION \
--zone=$ZONE \
--master-machine-type=e2-standard-2 \
--master-boot-disk-size=50GB \
--num-workers=2 \
--worker-machine-type=e2-standard-2 \
--worker-boot-disk-size=50GB
gcloud dataproc jobs submit spark \
--region=$REGION \
--cluster=example-cluster \
--class=org.apache.spark.examples.SparkPi \
--jars=file:///usr/lib/spark/examples/jars/spark-examples.jar \
-- 1000
gcloud dataproc clusters update example-cluster \
--num-workers=4 \
--region=$REGION
```
# check my progress you will get 100/100
## Hurray you are done with the lab
