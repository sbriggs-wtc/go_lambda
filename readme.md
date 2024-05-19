# GO, AWS Lambda

## Docker

WSL:
docker build --platform linux/amd64 -t docker-image:test .
docker run -d -p 9000:8080 --entrypoint /usr/local/bin/aws-lambda-rie docker-image:test ./main
curl "http://localhost:9000/2015-03-31/functions/function/invocations" -d '{"payload":"hello world!"}'


## Zip

WSL:
apt install golang-go
sudo apt-get install zip unzip -y

go build -tags lambda.norpc -o bootstrap main.go
zip go1.zip bootstrap 
curl -v -H "x-api-key: <API_KEY>" "<API_ENDPOINT>" -d '{"payload":"hello world!"}'


CMD:
"C:\Users\Shane Briggs\Go\bin\build-lambda-zip.exe" -o go1.zip bootstrap




