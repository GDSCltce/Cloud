# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell
```cmd
export REGION=
```
copy the region from task 1 step 1 command
```cmd
gcloud config set dataproc/region $REGION
gcloud dataproc clusters create example-cluster --worker-boot-disk-size 500
gcloud dataproc jobs submit spark \
--cluster example-cluster \
--class org.apache.spark.examples.SparkPi \
--jars file:///usr/lib/spark/examples/jars/spark-examples.jar \
-- 1000
```
# check my progress you will get 100/100
## Hurray you are done with the lab
