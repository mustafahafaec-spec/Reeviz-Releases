# Reeviz

Reeviz is an Autodesk Revit add-in focused on **coordination, management, and auditing workflows**.

**Current public release:** v0.1.4

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

### Add and Apply Pending Models

- Add local RVT files or browse Autodesk cloud projects through the Autodesk Forma / Docs browser.
- Review new links and staged changes in the pending queue before committing them to Revit.
- Commit new links, Reload From mappings, and Shared Site changes with **Apply Pending**.
- Choose Overlay or Attachment reference behavior.
- Choose Shared Coordinates, Origin to Origin, Center to Center, or Project Base Point to Project Base Point placement.
- For Shared Coordinates links with multiple named sites, **Choose first site for multiple site link** can select the first site automatically and keep the real Revit Shared Site relationship.
- If Shared Coordinates are unavailable, ProLink can fall back to **Project Base Point to Project Base Point** and reports the fallback.
- **Suppress Warnings** helps unattended batches continue past suppressible Revit warnings while still reporting failed operations.
- **Show Report after Applying** controls whether the completion report opens after Apply Pending.
- Link-setting choices are remembered per Revit project when ProLink closes, reopens, or temporarily closes to execute Apply Pending.
- A dedicated progress window shows active operations and supports cooperative cancellation.

### Shared Site Management

- The main **Shared Site** column can stage a different named site for an existing link instance.
- Existing link instances can also be staged as **`<Not Shared>`**.
- A staged site edit is shown as **Pending(Site Changed)** until Apply Pending runs.
- When Reload From and Shared Site are both staged for the same link, the row remains **Pending(Reload From)**; ProLink reloads the source first and then applies the requested site.
- Shared Site edits are handled per instance so different instances of one main link can remain on different named sites.

### Reload From

- Stage one or multiple existing main links for **Reload From** without changing the Revit model until **Apply Pending** runs.
- Map replacement models from local files or Autodesk Forma in a dedicated Reload From window.
- Use **Smart Find** against local folders, Autodesk Forma folders, or the current models pool.
- Search multiple selected folders and their subfolders using exact-name or partial-name matching.
- Successful Reload From operations finish loaded and apply transferred link/instance metadata where applicable.

### Links Metadata Transfer

- **Export Links Metadata** stores loaded link sources and settings in a Reeviz `.reevizlinks` transfer file.
- **Import Links Metadata** can recreate missing links, restore missing instances, stage changed sources as Reload From, and stage Shared Site differences.
- Transfer includes Reference Type, Type Workset, Instance Workset, Shared Site, pinned state, Alert Me state, and multiple instances of the same main link.
- Existing instance identity is matched by **Shared Site first** when repeated instances of the same link type are imported. An instance already on the requested site is preserved instead of being moved unnecessarily.
- If metadata contains more instances than the active model, ProLink adds the missing instances and restores their corresponding site and metadata. Extra existing model instances are not deleted by import.
- An existing link is treated as fully matching only when its source and required per-instance Shared Site configuration are already satisfied.
- Exact-source duplicates and self-link attempts are ignored rather than creating duplicate pending links.

### Manage Existing Links

- Review loaded, unloaded, pending, reload-required, staged Reload From, and staged Shared Site changes.
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
