## How To Spin Up Cloud Infrastructure and Test Locally

- Run ``` docker compose up -d ``` to build
- Run ``` docker compose logs -f ``` to see list of all supported services for local development
- Run ``` chmod u+x tf-ls.sh ```
- ``` aws configure --profile mylocalstack ```
temp
temp
us-east-1
none

- ``` export AWS_PROFILE=mylocalstack ```
- ``` ./tf-ls.sh init ```
- ``` ./tf-ls.sh plan -var-file tfvars/localstack.tfvars -out output.tfplan ```
- ``` ./tf-ls.sh apply output.tfplan ```

- ``` aws lambda invoke --endpoint-url http://localhost:4566 --function-name access-key-generator --region us-east-1 --payload "{\"user\": \"testuser\", \"region\": \"us-east-1\"}" result.log ```

- ``` aws iam list-access-keys --user-name testuser --endpoint-url http://localhost:4566  --region us-east-1 ```