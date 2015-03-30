# nubis-meta
Meta-repository for Nubis

$> aws cloudformation create-stack --capabilities CAPABILITY_IAM --stack-name packer --template-body "`cat nubis.json`"
$> aws cloudformation update-stack --capabilities CAPABILITY_IAM --stack-name packer --template-body "`cat nubis.json`"

Or better yet, use Ansible instead:

$> ansible-playbook -i localhost, ansible.yaml

