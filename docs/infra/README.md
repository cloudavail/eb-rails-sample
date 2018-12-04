# Objective

To create a basic Elastic Beanstalk Rails stack in CloudFormation that utilizes provides a "QA" and "Prod" environment. This setup allows code to be deployed first to "QA", tested and then the same code can be deployed to "Prod".

# Validate Stack
`aws cloudformation validate-template --template-body file://eb_rails_demo.yaml`

# Set a Secret Key for Ruby on Rails App

`eb_rails_app_secret_key=$(openssl rand -base64 12)`

# Create a EBRailsApp Stack
`aws cloudformation create-stack --stack-name EBRailsApp --parameters ParameterKey=EBRailsAppSecretKeyBase,ParameterValue=$eb_rails_app_secret_key --template-body file://eb_rails_demo.yaml`

# Update a EBRailsApp Stack
`aws cloudformation update-stack --stack-name EBRailsApp --parameters ParameterKey=EBRailsAppSecretKeyBase,ParameterValue=$eb_rails_app_secret_key --template-body file://eb_rails_demo.yaml`

# Delete a EBRailsApp Stack
`aws cloudformation delete-stack --stack-name EBRailsApp`
