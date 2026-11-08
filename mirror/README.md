`request.json` names the update to mirror (version, build, url on wayzerr.com, sha256, notes).
Changing it runs `.github/workflows/mirror.yml`, which publishes a GitHub release with the installer and a `latest.json` feed.
