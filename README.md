# Reeviz

Reeviz is an Autodesk Revit add-in focused on **coordination, management, and auditing workflows**.

**Current public release:** v0.1.3

## Compatibility

- Autodesk Revit 2023
- Autodesk Revit 2024
- Autodesk Revit 2025
- Windows x64
- Revit 2023/2024: .NET Framework 4.8
- Revit 2025: .NET 8

## Reeviz Ribbon

### Coordination

- **ProLink** — add, organize, inspect, monitor, transfer, reload, and manage RVT links from local storage and Autodesk cloud projects.

### Reeviz

- **About Reeviz** — version, licensing, appearance, update controls, bug/suggestion reporting, GitHub Releases, and LinkedIn.

## ProLink

ProLink provides one workspace for preparing new RVT links and managing links already loaded into the active Revit project.

### Add and Link Models

- Add local RVT files or browse Autodesk cloud projects through the Autodesk Forma / Docs browser.
- Review models in a pending queue before linking and remove pending items before they are committed.
- Link the full pending queue with **Link Pending**.
- Choose Overlay or Attachment reference behavior.
- Choose Shared Coordinates, Origin to Origin, Center to Center, or Project Base Point to Project Base Point placement.
- For Shared Coordinates links with multiple named sites, **Choose first site for multiple site link** can select the first site automatically and keep the real Revit Shared Site relationship.
- If Shared Coordinates are unavailable, ProLink can fall back to **Project Base Point to Project Base Point** and reports the fallback.
- **Suppress Warnings** helps unattended batches continue past suppressible Revit warnings while still reporting failed operations.
- A dedicated progress window shows the active model, completed and remaining counts, current stage, elapsed time, approximate cloud read activity, and cooperative cancellation.
- Every batch finishes with a user-facing linking report that can be exported.

### Reload From

- Stage one or multiple existing main links for **Reload From** without changing the Revit model until **Link Pending** runs.
- Map replacement models from local files or Autodesk Forma in a dedicated Reload From window.
- Use **Smart Find** against local folders, Autodesk Forma folders, or the current models pool.
- Search multiple selected folders and their subfolders using exact-name or partial-name matching.
- Successful Reload From operations finish loaded and apply transferred link/instance metadata where applicable.

### Links Metadata Transfer

- **Export Links Metadata** stores loaded link sources and settings in a Reeviz `.reevizlinks` transfer file.
- **Import Links Metadata** can recreate missing links, stage changed sources as Reload From, or apply settings to an already-matching source.
- Transfer includes reference type, type workset, instance workset, Shared Site, pinned state, Alert Me state, and multiple instances of the same main link.
- Exact-source duplicates and self-link attempts are ignored rather than creating duplicate pending operations.

### Manage Existing Links

- Review loaded, unloaded, pending, reload-required, and staged Reload From links.
- Edit Reference Type, Type Workset, Instance Workset, Shared Site, and pinned state where applicable.
- Apply compatible editable values to multiple highlighted links at once, including normal Shift/Ctrl multi-selection behavior.
- Reload, unload, unload for the current user, duplicate, remove, or purge links.
- Remove link types that have no remaining instances.
- Search and filter the link list.

### Groups

- Create persistent groups for link instances and transfer group arrangements between users/projects with Import/Export Groups.
- Rename groups, collapse or expand all groups, and temporarily hide groups.
- Hidden groups remain hidden after ProLink is reopened until explicitly shown again.
- Disable grouping temporarily without deleting group assignments.
- Group headers summarize shared values, show mixed states when members differ, and support aggregate editing.
- Group headers use persistent user-adjustable colors and a hatched visual treatment for quick identification.

### Autodesk Forma / Docs Browser

- Search models in the selected folder and its subfolders with an explicit Search action.
- Smart Find can search multiple selected cloud folders recursively.
- Selected cloud models remain available for normal linking and Reload From workflows.

### Change Monitoring

- **Alert Me** can monitor selected links at a configurable interval.
- **Check Updates** performs an immediate on-demand check.
- Local RVT links are checked against their acknowledged source state.
- Autodesk cloud links are checked for newer published model versions.
- Loaded Revit Cloud Worksharing links can also be checked against their central model state so synchronized changes can be detected without requiring an Autodesk Docs Publish first.

## Updates and Feedback

- Reeviz can notify you when a newer public release is available; update notifications can be enabled or disabled independently from Auto Update.
- **Report Bug / Suggestion** in About Reeviz can submit feedback with an optional image attachment.

## Links

- GitHub Releases: `https://github.com/mustafahafaec-spec/Reeviz-Releases`
- LinkedIn: `https://www.linkedin.com/in/mustafahaf/`

## Copyright

Copyright © 2026 Mustafa Hesham. All rights reserved.
