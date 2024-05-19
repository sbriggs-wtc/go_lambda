# GO, AWS Lambda

## Docker (Windows subsystem for linux)

docker build --platform linux/amd64 -t docker-image:test .

docker run -d -p 9000:8080 --entrypoint /usr/local/bin/aws-lambda-rie docker-image:test ./main

curl "http://localhost:9000/2015-03-31/functions/function/invocations" -d '{"payload":"hello world!"}'


## Zip

go build -tags lambda.norpc -o bootstrap main.go

"C:\Users\Shane Briggs\Go\bin\build-lambda-zip.exe" -o myFunction.zip bootstrap

curl -v -H "x-api-key: <API_KEY>" "<API_ENDPOINT>" -d '{"payload":"hello world!"}'



