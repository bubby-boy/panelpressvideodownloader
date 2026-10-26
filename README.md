# PanelPress Anime Library

A Flask-based anime URL catalog with search/filter controls, browser playback, and individual or batch downloads. The UI and catalog are embedded in `app.py`; `anime_urls.txt` is the source URL list.

## Deploy on blitz.cloud

This project is packaged as a Docker app. The `Dockerfile` installs Python dependencies and runs the Flask app with Gunicorn on `0.0.0.0:$PORT` (default 8080), as expected by container hosting.

1. Push the contents of this folder to a GitHub repository.
2. In blitz.cloud, create/deploy an app from that repository if the GitHub deployment option is available for your account. If the dashboard asks for a Docker image instead, build this Dockerfile and publish the image to a public container registry, then deploy that image.
3. Set the app's port to `8080` if the platform asks for one.
4. Open the generated HTTPS address.

## Run locally on Windows

Double-click `run.bat`, wait for dependencies to install, then open `http://127.0.0.1:5000`.

## Notes

- `downloads/` is where fetched files are saved while the app container is running. Container filesystems may be temporary, so downloaded files can disappear after a redeploy/restart unless persistent storage is configured.
- The queue/status data is held in memory and resets when the app restarts.
- The catalog contains URLs supplied by the project owner; availability, playback compatibility, and permissions to redistribute or download each item are not verified. Only use sources and content you have permission to access and download.
- This is a starter deployment setup, not a claim that the app has been runtime-tested on blitz.cloud.
