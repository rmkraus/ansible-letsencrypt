# ansible-letsencrypt
Ansible Lets Encrypt Client

## Usage

1. Copy secrets.yml.template to secrets.yml and fill out. Alternatively, you can
   use the secrets built into Tower.
2. Login to LetsEncrypt on the certificate managment node. This can be a remote
   Fedora/RHEL/CentOS machine or the localhost.
   ```bash
   ./login.yml -i INVENTORY -e @secrets.yml -l CERT_MANAGER
   ```
3. Generate certificates for hosts in your inventory.
   ```bash
   ./site.yml -i INVENTORY -e @secrets.yml -l HOSTS,NEEDING,CERTS
   ```

## Usage Notes

- Inventory hostnames should be the FQDN. It will be used as the Common Name 
  for the certs.
