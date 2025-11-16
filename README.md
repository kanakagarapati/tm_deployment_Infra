# TravelMemory Deployment (generated)

## What I filled for you:
- aws_region: us-west-2
- key_name: kanakamanoj-gkm
- ami: ami-00f46ccd1cbfb363e
- db_user: tmkanaka
- db_pass: gkm@57006
- jwt_secret: OxTwvbJLWsN39VHCPM/q+5BH3S4dl7BKPTmilCqa61I=
- ansible_ssh_user: ubuntu
- ssh_private_key path (local): /Users/kanakamanojgarapati/Downloads/kanakamanoj-gkm.pem
- prometheus_on: web (Prometheus scrape target set to 16.144.31.60:5000)

## Next steps:
1. Run Terraform:
   cd terraform
   terraform init
   terraform apply -auto-approve

2. Copy the terraform outputs (web_public_ip, db_public_ip) and replace <DB_PUBLIC_IP> in ansible/inventory.ini and monitoring/prometheus/prometheus.yml

3. Set permissions on your PEM locally:
   chmod 400 /Users/kanakamanojgarapati/Downloads/kanakamanoj-gkm.pem

4. Run Ansible:
   ansible-playbook -i ansible/inventory.ini ansible/site.yml --private-key /Users/kanakamanojgarapati/Downloads/kanakamanoj-gkm.pem

## WARNING:
These files currently include real secrets (db_pass, jwt_secret). Do NOT push this repository public. Replace secrets with placeholders or use a secrets manager before committing.
