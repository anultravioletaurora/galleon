# Jellyfin

### Deployment
Deployment rolls out Jellyfin with Nvidia Support and Zap2It for handling live TV guides.

### Noteworthy Plugins
- [LastFM](https://jellyfin-repo.jesseward.com/manifest.json)
- [SSO](https://raw.githubusercontent.com/9p4/jellyfin-plugin-sso/manifest-release/manifest.json)
- [Intro Skipper](https://manifest.intro-skipper.org/manifest.json)

### Required Secrets
| Secret | Key | Description |
|------------------------|-----------------------|---------------------|
| ```jellyfin-secrets``` | ```zap2it-username``` | Username for Zap2It |
| ```jellyfin-secrets``` | ```zap2it-password``` | Password for Zap2It |
