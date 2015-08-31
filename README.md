# nubis-meta
Meta-repository for Nubis

# Upload a default SSL Certificate:

```bash
$> aws iam upload-server-certificate --server-certificate-name <cert-name> --certificate-body `cat cert.pem` --private-key `cat cert.key`
```

Deploy

```bash
$> aws cloudformation create-stack --capabilities CAPABILITY_IAM --stack-name nubis-meta --template-body "`cat deployment.json`"
$> aws cloudformation update-stack --capabilities CAPABILITY_IAM --stack-name nubis-meta --template-body "`cat deployment.json`"
```

Or better yet, use Ansible instead:

```bash
$> ansible-playbook -i localhost, ansible.yaml -e env=dev -e domain=allizom.org -e region=us-east-1 -e ssl_cert_arn="arn:aws:iam::<account-id>:server-certificate/<cert-name>"
```
