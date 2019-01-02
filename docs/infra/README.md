# Objective

To create a basic Elastic Beanstalk Rails stack in CloudFormation that provides a "QA" and "Prod" environment. This setup allows code to be deployed first to "QA", tested and then the same code can be deployed to "Prod".

# Validate Stack
`aws cloudformation validate-template --template-body file://eb_rails_sample.yaml`

# Create a eb-rails-sample-app Stack
`aws cloudformation create-stack --stack-name eb-rails-sample-app --parameters --capabilities CAPABILITY_IAM --template-body file://eb_rails_sample.yaml`

# Update a eb-rails-sample-app Stack
`aws cloudformation update-stack --stack-name eb-rails-sample-app --parameters --capabilities CAPABILITY_IAM --template-body file://eb_rails_sample.yaml`

# Delete a eb-rails-sample-app Stack
`aws cloudformation delete-stack --stack-name eb-rails-sample-app`
