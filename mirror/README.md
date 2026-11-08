How an update gets mirrored to a GitHub release (no Cloudflare involved):
1. Branch `mirror/<version>` from main, with `mirror/request.json` (version, build, sha256, notes) and the installer cut into `mirror/parts/part-aa`, `part-ab`, ... (90 MB pieces).
2. Pushing it runs `.github/workflows/mirror.yml`, which joins the pieces, checks the sha256, publishes the release (installer + `latest.json`) and deletes the branch.
The apps read `https://github.com/grigorsworks/persona/releases/latest/download/latest.json` as a backup update feed.
