# Reeviz

Reeviz is an Autodesk Revit add-in focused on **coordination, management, and auditing workflows**.

**Current public release:** v0.1.2

## Compatibility

- Autodesk Revit 2023
- Autodesk Revit 2024
- Windows x64
- .NET Framework 4.8

## Reeviz Ribbon

### Coordination

- **ProLink** — add, organize, inspect, monitor, and manage RVT links from local storage and Autodesk cloud projects.

### Reeviz

- **About Reeviz** — version, licensing, appearance, update controls, GitHub Releases, and LinkedIn.

## ProLink

ProLink provides one workspace for preparing new RVT links and managing links already loaded into the active Revit project.

### Add and Link Models

- Add local RVT files or browse Autodesk cloud projects through the Autodesk Forma / Docs browser.
- Review models in a pending queue before linking.
- Remove pending items before they are linked.
- Link the full pending queue with **Link Pending**.
- Choose Overlay or Attachment reference behavior.
- Choose link placement, including Shared Coordinates, Origin to Origin, Center to Center, and Project Base Point to Project Base Point.
- If Shared Coordinates are unavailable, ProLink can fall back to **Project Base Point to Project Base Point** and reports the fallback to the user.
- A dedicated linking-progress window shows the current model, completed and remaining counts, current stage, elapsed time, and approximate Revit transfer activity for cloud links.
- Linking can be cancelled cooperatively so no additional pending links start after the active Revit load operation returns.

### Manage Existing Links

- Review loaded, unloaded, and reload-required RVT links.
- Edit Reference Type, Type Workset, Instance Workset, Shared Site, and pinned state where applicable.
- Apply compatible editable values to multiple highlighted links at once.
- Reload, unload, unload for the current user, duplicate, remove, or purge links.
- Remove link types that have no remaining instances.
- Search and filter the link list.

### Groups

- Create persistent groups for link instances.
- Rename groups.
- Collapse or expand all groups.
- Temporarily hide groups and restore them with **Show hidden**.
- Apply supported group-level values across all members.
- Group headers summarize shared values and show a mixed state when members differ.

### Change Monitoring

- **Alert Me** can monitor selected links at a configurable interval.
- **Check Updates** performs an immediate on-demand check.
- Local RVT links are checked against their acknowledged source state.
- Autodesk cloud links are checked for newer published model versions.
- Loaded Revit Cloud Worksharing links can also be checked against their central model state so synchronized changes can be detected without requiring an Autodesk Docs Publish first.

## Links

- GitHub Releases: `https://github.com/mustafahafaec-spec/Reeviz-Releases`
- LinkedIn: `https://www.linkedin.com/in/mustafahaf/`

## Copyright

Copyright © 2026 Mustafa Hesham. All rights reserved.
