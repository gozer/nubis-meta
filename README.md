$> aws cloudformation create-stack --capabilities CAPABILITY_IAM --debug --stack-name packer --template-body "`cat test.json`"

$> aws cloudformation update-stack --capabilities CAPABILITY_IAM --debug --stack-name packer --template-body "`cat test.json`"
