# Nextcloud - BYOI (Bring your own Ingress)

### Deployment
Deployment rolls out a HA statefulset of the Nextcloud DB + Redis and a HA deployment of Nextcloud. Also deploys an external cronjob container for running nextcloud cronjobs

### Required Secrets
| Secret | Key | Description |
|------------------------|-----------------------|---------------------|
| ```nextcloud``` | ```admin-password``` | Admin password for Nextcloud |
| ```nextcloud``` | ```trusted_domains``` | Trusted domains for the Nextcloud web service |
