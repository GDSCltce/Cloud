# Click on start lab
# Right click on google coud console and open it in incognito window
# Sign in the google cloud console with the credential provided in the lab
# Run this command by activating the cloud shell

```cmd
gcloud compute ssh linux-instance
```
### Press `y` , `ENTER` > `ENTER` > `ENTER` > `n`, `ENTER`
### Get API KEY from `Navigation menu` > `APIs & services` > `Credentials` > `Create credentials` > `API key`
```cmd
export API_KEY=
```
```cmd
cat > request.json <<EOF
{
  "config": {
      "encoding":"FLAC",
      "languageCode": "en-US"
  },
  "audio": {
      "uri":"gs://cloud-samples-tests/speech/brooklyn.flac"
  }
}
EOF
curl -s -X POST -H "Content-Type: application/json" --data-binary @request.json \
"https://speech.googleapis.com/v1/speech:recognize?key=${API_KEY}" > result.json
```
