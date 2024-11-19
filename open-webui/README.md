## Ollama - B.Y.O.I. (Bring your own ingress)
Deploys Ollama for managing and interacting with A.I. models, as well as Open Web UI for web access to ollama. Open WebUI is configured to use Authentik as a SSO provider, so the secrets below are there to faciliate that rollout

### Required Secrets
| Secret | Key | Description |
|------------------------|-----------------------|---------------------|
| ```open-webui``` | ```openid_provider_url``` | Provider URL for OpenID |
| ```open-webui``` | ```oauth_client_id``` | The client ID for OAuth |
| ```open-webui``` | ```oauth_client_secret``` | The client secret for OAuth |
| ```open-webui``` | ```openid_redirect_uri``` | Redirect URL for OpenID |
