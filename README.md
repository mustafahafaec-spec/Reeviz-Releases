# Reeviz

Reeviz is an Autodesk Revit add-in focused on **coordination, management, and auditing workflows**.

**Current public release:** v0.1.5

## Compatibility

- Autodesk Revit 2023
- Autodesk Revit 2024
- Autodesk Revit 2025
- Autodesk Revit 2026
- Windows x64
- Revit 2023/2024: .NET Framework 4.8
- Revit 2025/2026: .NET 8

## Reeviz Ribbon

### Coordination

- **ProLink** — add, organize, inspect, monitor, transfer, reload, and manage RVT links from local storage, Autodesk cloud projects, and Autodesk Desktop Connector.

### Reeviz

- **About Reeviz** — version, licensing, appearance, update controls, bug/suggestion reporting, GitHub Releases, and LinkedIn.

## ProLink

ProLink provides one workspace for preparing new RVT links and managing links already loaded into the active Revit project.

### Add and Apply Pending Models

- Add local RVT files, browse Autodesk cloud projects through the Autodesk Forma / Docs browser, or select RVT files from Autodesk Desktop Connector.
- Review new links and staged changes in the pending queue before committing them to Revit.
- Commit new links, Reload From mappings, and Shared Site changes with **Apply Pending**.
- Choose Overlay or Attachment reference behavior.
- Choose Shared Coordinates, Origin to Origin, Center to Center, or Project Base Point to Project Base Point placement.
- For Shared Coordinates links with multiple named sites, **Choose first site for multiple site link** can select the first site automatically and keep the real Revit Shared Site relationship.
- If Shared Coordinates are unavailable, ProLink can fall back to **Project Base Point to Project Base Point** and reports the fallback.
- **Suppress Warnings** helps unattended batches continue past suppressible Revit warnings while still reporting failed operations.
- **Show Report after Applying** controls whether the completion report opens after Apply Pending.
- **Show Last Report** reopens the latest Apply Pending report from the current Revit session.
- Link-setting choices are remembered per Revit project when ProLink closes, reopens, or temporarily closes to execute Apply Pending.
- A dedicated progress window shows active operations, can be minimized, and supports cooperative cancellation.

### Linking Methods

The main ProLink pane includes a **Linking Method** column so the source type of each link is clear:

- **Local** — normal local or network file linking.
- **Cloud** — Autodesk cloud/Revit Cloud Worksharing models identified by their cloud model identity.
- **Desktop Connector** — files selected from the user's Autodesk Desktop Connector workspace.

Desktop Connector browsing is limited to the connected Autodesk workspace and projects available there. ProLink does not open the Desktop Connector browser when the connector is not installed, not running, or its workspace is unavailable.

### Autodesk Desktop Connector

- Use **Desktop Connector** from **New Link** to browse RVT files from the connected Autodesk Docs/Forma workspace.
- Use Desktop Connector in **Reload From** to replace an existing link from the same connected workspace workflow.
- **Smart Find** includes a Desktop Connector source for recursive matching inside selected connector folders.
- ProLink keeps Desktop Connector separate from Revit Cloud Worksharing/Autodesk Forma cloud-model linking.
- Revit's saved source is read back after linking/reloading so ProLink reports the path Revit actually retains rather than presenting a synthetic local-cache path.
- Links Metadata export/import preserves Desktop Connector as its own linking method and supports portable Autodesk Docs/Forma identities when available.

### Autodesk Forma / Docs Browser

- Browse Autodesk cloud projects and folders for Revit cloud models.
- Only models with authoritative Revit cloud Project GUID and Model GUID identity are offered as cloud-link candidates; ordinary uploaded `.rvt` files are not treated as cloud models merely because of their extension.
- Search models in the selected folder and its subfolders with an explicit Search action.
- Smart Find can search multiple selected cloud folders recursively.
- Selected cloud models remain available for normal linking and Reload From workflows.

### Shared Site Management

- The main **Shared Site** column can stage a different named site for an existing link instance.
- Existing link instances can also be staged as **`<Not Shared>`**.
- A staged site edit is shown as **Pending(Site Changed)** until Apply Pending runs.
- When Reload From and Shared Site are both staged for the same link, the row remains **Pending(Reload From)**; ProLink reloads the source first and then applies the requested site.
- Shared Site edits are handled per instance so different instances of one main link can remain on different named sites.
- Pinned instances are handled safely during Shared Site changes and restored to their requested pinned state afterward.

### Reload From

- Stage one or multiple existing main links for **Reload From** without changing the Revit model until **Apply Pending** runs.
- Map replacement models from local files, Autodesk Forma, or Autodesk Desktop Connector in the dedicated Reload From workflow.
- Use **Smart Find** against local folders, Autodesk Forma folders, Desktop Connector folders, or the current models pool.
- Search selected folders and their subfolders using exact-name or partial-name matching.
- Successful Reload From operations finish loaded and apply transferred link/instance metadata where applicable.

### Links Metadata Transfer

- **Export Links Metadata** stores loaded link sources and settings in a Reeviz `.reevizlinks` transfer file.
- **Import Links Metadata** can recreate missing links, restore missing instances, stage changed sources as Reload From, and stage Shared Site differences.
- Transfer includes Linking Method/source identity, Position, Reference Type, Type Workset, Instance Workset, Shared Site, pinned state, both Alert Me modes, group membership, group order, and multiple instances of the same main link.
- Imported Position and Reference Type come from the metadata rather than the current Add/Change Links controls.
- If an imported user workset does not exist in the destination model, ProLink attempts to create it; when that is not possible, it falls back to an available destination user workset and continues instead of failing the whole import.
- Existing instance identity is matched by **Shared Site first** when repeated instances of the same link type are imported. An instance already on the requested site is preserved instead of being moved unnecessarily.
- If metadata contains more instances than the active model, ProLink adds the missing instances and restores their corresponding site and metadata. Extra existing model instances are not deleted by import.
- Exact-source duplicates and self-link attempts are ignored rather than creating duplicate pending links.
- Desktop Connector metadata remains Desktop Connector on import instead of being converted into a Local link.

### Manage Existing Links

- Review loaded, unloaded, pending, reload-required, staged Reload From, and staged Shared Site changes.
- Review each link's **Linking Method** before its Path.
- Edit Reference Type, Type Workset behavior, Instance Workset, Shared Site, and pinned state where applicable.
- Apply compatible editable values to multiple highlighted links at once, including normal Shift/Ctrl multi-selection behavior.
- Reload, unload, unload for the current user, duplicate, remove, or purge links.
- Remove link types that have no remaining instances.
- Search and filter the link list.
- Right-click an errored row and choose **Show Error** to inspect its recorded diagnostic message.

### Groups

- Create persistent groups for link instances.
- Reorder groups with **Move Group Up** and **Move Group Down**; the custom order persists per Revit project.
- Links Metadata carries group membership and group order so arrangements can be restored with the link metadata.
- Standalone group transfer uses the Reeviz `.reevizgroups` format.
- Rename groups, collapse or expand all groups, and temporarily hide groups.
- Hidden groups remain hidden after ProLink is reopened until explicitly shown again.
- Disable grouping temporarily without deleting group assignments.
- Group headers summarize shared values, show mixed states when members differ, and support aggregate editing.
- Group headers use persistent user-adjustable colors and a hatched visual treatment for quick identification.

### Change Monitoring

- **Alert Me** has separate **On Publish** and **On Sync** options for supported cloud links.
- Enabling **On Sync** also enables **On Publish** so synchronized-model monitoring does not omit published updates.
- **On Publish** watches for newer published Autodesk cloud model versions.
- **On Sync** uses the live Revit Cloud Worksharing state when it is available to the signed-in user and model; unavailable/denied live access keeps the sync-only option disabled rather than reporting an unknown state as a change.
- Local RVT links are checked against their acknowledged source state.
- **Check Updates** performs an immediate on-demand check.
- Alert popups can reopen ProLink with **Show**.

## Updates and Feedback

- Reeviz can notify you when a newer public release is available; update notifications can be enabled or disabled independently from Auto Update.
- The update prompt provides **Update Now**, **Later**, and **Stop Notification** actions.
- **Report Bug / Suggestion** in About Reeviz can submit feedback with an optional image attachment.

## Links

- GitHub Releases: `https://github.com/mustafahafaec-spec/Reeviz-Releases`
- LinkedIn: `https://www.linkedin.com/in/mustafahaf/`

## Copyright

Copyright © 2026 Mustafa Hesham. All rights reserved.
