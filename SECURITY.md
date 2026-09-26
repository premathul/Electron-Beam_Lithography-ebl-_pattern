# Security and Data Handling

The application is intentionally static and local-first.

- No backend service is required.
- No pattern data is transmitted by the application.
- No cookies, analytics, telemetry, or third-party scripts are included.
- CSV export is generated locally in the browser.

For unpublished device designs, prefer local use or an access-controlled private deployment. Do not assume that a private source repository automatically makes every deployment target private; verify the host's access settings separately.

If future versions add authentication, cloud storage, collaboration, analytics, or APIs, this document should be revised before deployment.
