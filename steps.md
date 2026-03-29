🚀 Commands to Run

🔹 1. Validate template
aws cloudformation validate-template \
  --template-body file://webserver-ec2-cfn.yml

🔹 2. Create stack
aws cloudformation create-stack \
  --stack-name web-server-stack \
  --template-body file://webserver-ec2-cfn.yml \
  --parameters ParameterKey=KeyName,ParameterValue=ec2-tutorial

🔹 3. Check stack status
aws cloudformation describe-stacks \
  --stack-name web-server-stack \
  --query "Stacks[0].StackStatus"

🔹 4. Get website URL
aws cloudformation describe-stacks \
  --stack-name web-server-stack \
  --query "Stacks[0].Outputs"
  
🔹 5. Cleanup
aws cloudformation delete-stack \
  --stack-name web-server-stack
