# Reeviz

Reeviz is an Autodesk Revit add-in focused on **coordination, management, and auditing workflows**.

Version `0.1.0` is the first public release and currently supports **Autodesk Revit 2024**. Its first production tool is **ProLink**, a link-management workflow for adding and managing Revit links from local storage and Autodesk cloud projects.

## Compatibility

- Autodesk Revit 2024
- Windows x64
- .NET Framework 4.8

## Reeviz Ribbon

### Coordination

- **ProLink** — batch link and manage RVT models.

### Reeviz

- **About Reeviz** — version, licensing, appearance, update controls, GitHub Releases, and LinkedIn.

## ProLink

ProLink provides one interface for both adding new RVT links and managing links already present in the active Revit model.

### Logging

ProLink maintains an in-session log and writes operation logs under:

`%APPDATA%\Reeviz\Logs`

The log records link operations and relevant Autodesk cloud identity information to assist with coordination and troubleshooting.

## Appearance

Reeviz includes persistent **Light** and **Dark** themes.

The selected appearance is shared across Reeviz windows. Reeviz uses its own blue accent language in Dark mode rather than the green accent used by Neevis.


## Automatic Updates

Reeviz checks published releases from:

`https://github.com/mustafahafaec-spec/Reeviz-Releases`

Users can:

- Check for updates manually from About Reeviz.
- Enable automatic update checks.
- Download an available Reeviz ZIP package.
- Stage the update for installation after Revit closes.


## Links

- GitHub Releases: `https://github.com/mustafahafaec-spec/Reeviz-Releases`
- LinkedIn: `https://www.linkedin.com/in/mustafahaf/`

## Copyright

Copyright © 2026 Mustafa Hesham. All rights reserved.
