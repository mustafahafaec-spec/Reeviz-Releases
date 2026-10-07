# Reeviz v0.2.0

Reeviz is an Autodesk Revit add-in for **model coordination, RVT link management, and working with clash data from Neevis/Navisworks directly inside Revit**.

**Current public release:** v0.2.0

## Compatibility

- Autodesk Revit 2021
- Autodesk Revit 2022
- Autodesk Revit 2023
- Autodesk Revit 2024
- Autodesk Revit 2025
- Autodesk Revit 2026
- Windows x64

## Reeviz Tools

### ProLink

**Use ProLink to add, organize, update, and manage RVT links in the current Revit project.**

ProLink brings the main Revit linking workflows into one place instead of managing links one by one through multiple Revit dialogs.

You can use it to:

- Add RVT links from **local files**, **Autodesk cloud projects**, or **Autodesk Desktop Connector**.
- Choose link positioning, including Shared Coordinates, Origin to Origin, Center to Center, and Project Base Point alignment.
- Set Overlay / Attachment behavior and worksets.
- Review loaded, unloaded, changed, and pending links.
- Reload, unload, duplicate, remove, or purge links.
- Use **Reload From** to replace an existing link with another source.
- Manage Shared Sites for linked-model instances.
- Organize links into persistent groups.
- Export and import link setup using Reeviz link metadata files.
- Use **Smart Find** to locate replacement models across supported sources.
- Monitor supported local/cloud links for newer versions with **Alert Me** and **Check Updates**.

**Use ProLink when:** you are setting up a coordinated Revit model, maintaining many linked models, replacing links, or transferring link configurations between projects.

---


### NWCGo

**Use NWCGo to prepare configured Revit views and export Navisworks NWC files from multiple Revit model sources in one batch.**

NWCGo supports:

- Adding target models from **Autodesk Forma / Autodesk Construction Cloud**, **Local RVT files**, and **Autodesk Desktop Connector**.
- Grouping multiple NWC export rows under the same RVT so the model opens once and all of its requested exports run in that session.
- Persistent user profiles containing model selections, naming rules, export settings, reference setup and per-row view/template/scope configuration.
- **Target Model**, **Reference Model**, and **Manual** data-source workflows for 3D View, View Template and Scope Box selection.
- Optional reference-model reload/mimic workflows for 3D views, templates and scope boxes.
- Per-row or bulk **Build Name** rules, custom NWC names, copy/paste settings and multi-row editing.
- Fault-tolerant batch processing that logs recoverable reference, worksharing, view-preparation and NWC-export errors while continuing with remaining models/exports.
- Optional detailed process logs in the selected export folder.

**Use NWCGo when:** you need repeatable NWC exports from many Revit models/views without manually opening and configuring each model one by one.

---

### Analyzer [BETA]

**Use Analyzer to review Neevis clash-coordination data directly inside Revit.**

Analyzer reads the Neevis Workspace associated with the coordination model and presents the clash information in Revit without requiring you to manually inspect the Navisworks clash tree.

Analyzer includes:

- **Clash Summary** — overview of True Clashes, Reviewed, and Approved clashes by Workspace group.
- **Clashes Table** — detailed group/item clash counts.
- **Clashes Matrix** — matrix view of clashes between Workspace Items/Search Sets.
- **Priority Items** — visual priority-based clash overview.
- **Clashes List** — individual clashes related to the current Revit model.
- **Workspace** — review the loaded Workspace groups/models used by Analyzer.

From Analyzer you can also:

- Filter coordination information to the current Revit model.
- Review or approve clashes and update comments/assignments where supported by the loaded Workspace.
- Filter clashes using selected Revit elements.
- Hide unselected clashes and restore the full list.
- Inspect Item A / Item B element, model, and ID information.
- Copy individual table values.
- Customize visible Clash List columns and export the current list to Excel.
- Create coordination views for individual clashes.
- Limit how many Reeviz clash views are retained.
- Jump from Summary/Table/Matrix/Priority selections directly to the matching Clashes List.
- Configure **Analyzer mode** (**Link Mode / Portal Mode**) from **Analyzer Settings → General**.
- Use **Apply Clash Appearance Automatically** (checked by default) to apply the configured clash appearance whenever **Show in Model** or **Create View for Clash** runs.
- Configure clash appearance colors for Item A, Item B, and non-clashing model content.
- In **Portal Mode**, **Show in Model** transfers the current Navisworks Section Box directly without opening the Portal UI. With automatic appearance enabled, the transfer follows Item A/Item B/non-clashing appearance settings; with it disabled, the full Section Box is transferred using original Navisworks colors. Revit links are turned off in the target view in either case.
- Reset Analyzer-applied view changes with **Reset View**.
- Closing Analyzer automatically runs the same **Reset View** cleanup before the window is disposed, so Analyzer visibility/filter/appearance changes are not left behind.

**Use Analyzer when:** you are resolving coordination issues in Revit and need to understand which clashes affect the current model, inspect the involved elements, or update clash information without switching constantly between Revit and Navisworks.

---

### Portal [BETA]

**Use Portal to bring the relevant part of a Navisworks federation into the current Revit view for coordination reference.**

The Blue Portal in Reeviz works together with the Orange Portal in Neevis/Navisworks and remains in front of other windows while it is open.

Typical workflow:

1. Open the Revit and Navisworks models used for coordination.
2. Open **Portal** in Reeviz and ensure the Neevis/Navisworks coordination session is running.
3. Open a Revit 3D view and define the required Section Box.
4. Click **Refresh** to send the current Revit scope to the active Neevis/Navisworks Portal listener. Use **Clear Cache** beside Refresh when the local Portal geometry cache must be rebuilt.
5. Review the Navisworks source files found in that area.
6. Click **Transfer/Update** to bring the returned coordination geometry into Revit.
7. Use **Clear Portal** when the temporary coordination geometry is no longer required.

Portal controls include:

- Show/hide individual Navisworks source files.
- Randomize source colors.
- **Keep Original Colors** from Navisworks.
- Re-transfer/update geometry without intentionally stacking duplicate Portal geometry.
- Progress feedback during geometry transfer.
- Automatic exclusion of the current Revit model from the returned source geometry.

In workshared Revit models, managed Portal geometry uses a temporary **per-Autodesk-user workset** named from `Reeviz_Temp_<current Autodesk username>` and Reeviz requests ownership so that workset is editable by the current user. Before model Save, Save As, or Synchronize with Central, Reeviz synchronously closes the Portal UI first and then removes and verifies the absence of all Reeviz-managed Portal geometry before Revit continues persistence, even when **Keep Created Elements** is enabled. If any managed Portal element cannot be removed, the cancellable persistence operation is stopped instead of saving/synchronizing the cache geometry. **Clear Portal** still removes the current user's managed Portal geometry/workset explicitly.

**Use Portal when:** you need surrounding Navisworks coordination geometry visible in Revit to understand a clash or spatial condition without permanently importing the federation into the project.

---

### About Reeviz

Use **About Reeviz** to:

- Check the installed Reeviz version.
- Manage Reeviz appearance/preferences.
- Review update options.
- Submit a bug report or suggestion.
- Open the Reeviz GitHub Releases page.

### License change in v0.2.0

When Public v0.2.0 or a later Public release first validates an existing **perpetual** Reeviz license, that entitlement is converted locally to a **90-day validity period**. The 90-day period starts with the first Revit session after the Public update is installed and remains tied to that license ID and machine; later Reeviz updates do not restart the period. Existing RSA-signed license certificates are preserved and the local conversion deadline is protected separately.

## Recommended Workflow

For a typical coordination project:

1. Use **ProLink** to prepare and maintain the Revit link setup.
2. Load the applicable Neevis Workspace and use **Analyzer** to review clashes affecting the Revit model.
3. Use **NWCGo** when coordinated NWC exports must be generated from multiple target Revit models/views.
4. Use **Portal** when you need Navisworks federation geometry visible around a specific Revit Section Box.
5. Resolve the issue in Revit and update the coordination information through Analyzer/Neevis as required by the project workflow.

## Release Status

- **ProLink** — established Reeviz link-management tool.
- **NWCGo** — established NWC export/coordination tool.
- **Analyzer** — BETA.
- **Portal** — BETA.

Beta tools are intended for active testing. Keep normal project backups and report reproducible issues with the relevant Reeviz session information where possible.

## Links

- GitHub Releases: `https://github.com/mustafahafaec-spec/Reeviz-Releases`
- LinkedIn: `https://www.linkedin.com/in/mustafahaf/`

## Copyright

Copyright © 2026 Mustafa Hesham. All rights reserved.
