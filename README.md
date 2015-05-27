# nubis-meta
Meta-repository for Nubis

$> aws cloudformation create-stack --capabilities CAPABILITY_IAM --stack-name nubis-meta --template-body "`cat nubis.json`"
$> aws cloudformation update-stack --capabilities CAPABILITY_IAM --stack-name nubis-meta --template-body "`cat nubis.json`"

Or better yet, use Ansible instead:

$> ansible-playbook -i localhost, ansible.yaml -e env=dev -e domain=allizom.org -e template=deployment -e region=us-east-1

Note, there are 2 templates, deployment.json and meta.json.

deployment.json should be deployed in deployment environments
meta.json should be deployed only in the global environments
