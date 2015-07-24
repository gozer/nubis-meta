# nubis-meta
Meta-repository for Nubis

# Upload a default SSL Certificate:

```bash
$> aws iam upload-server-certificate --server-certificate-name <cert-name> --certificate-body `cat cert.pem` --private-key `cat cert.key`
```

Deploy

```bash
$> aws cloudformation create-stack --capabilities CAPABILITY_IAM --stack-name nubis-meta --template-body "`cat nubis.json`"
$> aws cloudformation update-stack --capabilities CAPABILITY_IAM --stack-name nubis-meta --template-body "`cat nubis.json`"
```

Or better yet, use Ansible instead:

```bash
$> ansible-playbook -i localhost, ansible.yaml -e env=dev -e domain=allizom.org -e template=deployment -e region=us-east-1 -e ssl_cert_arn="arn:aws:iam::<account-id>:server-certificate/<cert-name>"
```

Note, there are 2 templates, deployment.json and meta.json.

* deployment.json should be deployed in deployment environments
* meta.json should be deployed only in the global environments
