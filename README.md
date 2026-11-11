# Reeviz v0.3.3

Reeviz is an Autodesk Revit add-in for **model coordination, RVT link management, NWC export workflows, and working with Neevis/Navisworks clash data directly inside Revit**.

**Release source version:** v0.3.3

## Compatibility

- Autodesk Revit 2021
- Autodesk Revit 2022
- Autodesk Revit 2023
- Autodesk Revit 2024
- Autodesk Revit 2025
- Autodesk Revit 2026
- Windows x64

**Compatibility note:** Reeviz v0.3.3 retains the .NET 10 source-target correction required for the Revit 2026.5 managed API generation. Revit 2025.5 also moved to the .NET 10 API generation, but the Revit 2025 project remains on its .NET 8 target; dedicated Revit 2025.5 compatibility is therefore not claimed for this release.

## What's New in v0.3.3

- **NWCGo:** The Options window is 12% taller, improving room for the settings.
- **NWCGo:** The Assign Clash Code window includes a search field for finding family and type rows.
- **NWCGo:** More resilient handling of recoverable warnings and errors during grouped NWC exports, with an option to let users respond to native error dialogs.
- **NWCGo:** Improvements to retained-model handling after exports and unattended scheduled processing; consult Known Issues for remaining verification.
- **Portal (BETA):** Continued native Floor creation and geometry-boundary improvements for Permanent Mode. Complex model geometry may still require follow-up.
- **About Reeviz:** Added dedicated **Report Issue** and **Send Suggestion** actions.
- **Licensing and updates:** Improved compatibility with the current activation and official Public-release update workflow while preserving the existing Activation UI.
- **Revit versions:** Maintains separate Revit 2021–2026 package targets.

See `Release Notes/RELEASE_NOTES_v0.3.3.md` for details and current limitations.

## Reeviz Tools

### ProLink

**Use ProLink to add, organize, update, and manage RVT links in the current Revit project.**

Key capabilities include:

- Add RVT links from local files, supported Autodesk cloud sources, or Autodesk Desktop Connector.
- Choose link positioning, Overlay / Attachment behavior, and worksets.
- Review loaded, unloaded, changed, and pending links.
- Reload, unload, duplicate, remove, purge, or use **Reload From** to replace an existing source.
- Manage Shared Sites and persistent link groups.
- Export/import Reeviz link setup metadata.
- Use **Smart Find**, **Alert Me**, and **Check Updates** for supported replacement/update workflows.

### NWCGo

**Use NWCGo to prepare configured Revit views and export Navisworks NWC files from multiple Revit model sources in one batch.**

Key capabilities include:

- Local, Autodesk cloud, and Desktop Connector model sources.
- Persistent export profiles and per-row view/template/scope configuration.
- Multi-model batch processing with fault-tolerant logging and progress feedback.
- Per-row/bulk naming, copy/paste settings, sorting and group ordering.
- Excel round-trip editing for NWC rows.
- Scheduled Once/Repeated unattended exports with task history and logs.
- Optional reference-model workflows and lightweight preparation modes.

### Analyzer [BETA]

**Use Analyzer to review Neevis clash-coordination data directly inside Revit.**

Analyzer provides:

- Clash Summary, Clashes Table, Clashes Matrix, Priority Items, Clashes List and Workspace views.
- Filtering to the current Revit model or selected elements.
- Clash review/approval/comment/assignment workflows where supported by the loaded Workspace.
- Item A / Item B inspection, table-value copy, Excel export and coordination-view creation.
- Link Mode / Portal Mode behavior and configurable clash appearance.
- **Reset View** cleanup of Analyzer-applied visibility/filter/appearance changes.

### Portal [BETA]

**Use Portal to bring the relevant part of a Navisworks federation into the current Revit view for coordination reference.**

Typical workflow:

1. Open the coordinated Revit/Navisworks models.
2. Open Portal in Reeviz and establish the required Revit 3D Section Box.
3. Refresh the current coordination scope.
4. Review returned source models and visibility/color options.
5. Transfer/update the required coordination geometry.
6. Use **Clear Portal** when the temporary geometry is no longer required.

Portal includes source visibility/color controls, original-color support, transfer/update behavior, and managed cleanup before supported persistence operations.

## About Reeviz

Use **About Reeviz** to:

- Check the installed Reeviz version/build channel.
- Review validated license information, including edition, expiry/remaining days, Machine Code and enabled features where available.
- Manage Reeviz appearance/preferences.
- Review update options.
- Submit a bug report or suggestion.

## Licensing and Usage Data

Public Reeviz builds support **internet activation** and **manual activation** using the Machine Code shown in the Reeviz activation window. Reeviz also provides the established 7-day free trial and local deactivation workflow.

Licensed operation includes background authorization checks. A previously verified authorization may allow limited temporary offline use when the licensing service is unavailable. If the installed build becomes incompatible with current licensing requirements, Reeviz may require a compatible public update before licensed tools can continue; the existing Reeviz updater is used for that process.

Reeviz maintains aggregate product-usage statistics for product improvement and processes them automatically in the background. Data categories, retention and network behavior are described at a higher level in the installer **Terms, Licensing, Network Checks and Privacy Notice**. The About Reeviz UI does not provide a manual usage-statistics export control.

## Recommended Workflow

For a typical coordination project:

1. Use **ProLink** to prepare and maintain the Revit link setup.
2. Load the applicable Neevis Workspace and use **Analyzer** to review clashes affecting the Revit model.
3. Use **NWCGo** when coordinated NWC exports must be generated from multiple target Revit models/views.
4. Use **Portal** when Navisworks federation geometry is needed around a specific Revit scope.
5. Resolve the issue in Revit and update the coordination information through Analyzer/Neevis as required by the project workflow.

## Release Status

- **ProLink** — Released
- **NWCGo** — Released
- **Analyzer** — BETA
- **Portal** — BETA

Beta tools are intended for active testing. Keep normal project backups and report reproducible issues with the relevant Reeviz session information where possible.

## Links

- GitHub Releases: `https://github.com/mustafahafaec-spec/Reeviz-Releases`
- LinkedIn: `https://www.linkedin.com/in/mustafahaf/`

## Copyright

Copyright © 2026 Mustafa Hesham. All rights reserved.
