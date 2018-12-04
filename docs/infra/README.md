# Objective

To create a basic Elastic Beanstalk Rails stack in CloudFormation that utilizes provides a "QA" and "Prod" environment. This setup allows code to be deployed first to "QA", tested and then the same code can be deployed to "Prod".

# Validate Stack
`aws cloudformation validate-template --template-body file://eb_rails_demo.yaml`

# Create a EBRailsApp Stack
`aws cloudformation create-stack --stack-name EBRailsApp --template-body file://eb_rails_demo.yaml`

# Update a EBRailsApp Stack
`aws cloudformation update-stack --stack-name EBRailsApp --template-body file://eb_rails_demo.yaml`

# Delete a EBRailsApp Stack
`aws cloudformation delete-stack --stack-name EBRailsApp`
