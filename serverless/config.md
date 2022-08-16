#1. Instale o AWS SDK
#Navegue até serverless/dependencies/nodejse execute 
npm install 
#para instalar o AWS SDK.


#2. Crie um bucket do S3
aws s3api create-bucket --bucket ccontipelab-s3-bucket-ivs-web-demo --region us-east-1


#3. Modelo de pacote com SAM
sam package --template-file template.yaml --s3-bucket ccontipelab-s3-bucket-ivs-web-demo --output-template-file output.yaml


#4. Implante o modelo empacotado
sam deploy --template-file ./output.yaml --stack-name ivs-demo-web --capabilities CAPABILITY_IAM --region us-east-1

Outputs
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Key                 ApiURL
Description         API endpoint URL for Prod environment
Value               https://yk2cdfp1t0.execute-api.us-east-1.amazonaws.com/Prod/
------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Successfully created/updated stack - ivs-demo-web in us-east-1