# Reeviz

Reeviz is an Autodesk Revit add-in for **model coordination, RVT link management, and working with clash data from Neevis/Navisworks directly inside Revit**.

**Current public release:** v0.1.5  
**Current Beta release:** v0.2.0-beta.2.0

> Beta features are available for testing and may continue to change before the next stable public release.

## Compatibility

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
- Configure clash appearance colors for Item A, Item B, and non-clashing model content.
- Reset Analyzer-applied view changes with **Reset View**.

**Use Analyzer when:** you are resolving coordination issues in Revit and need to understand which clashes affect the current model, inspect the involved elements, or update clash information without switching constantly between Revit and Navisworks.

---

### Neevis Portal [BETA]

**Use Neevis Portal to bring the relevant part of a Navisworks federation into the current Revit view for coordination reference.**

The Portal works together with **Reeviz Portal** in Neevis/Navisworks.

Typical workflow:

1. Open a Revit 3D view and define the required Section Box.
2. Open **Neevis Portal**.
3. Click **Refresh** to send the current Revit scope to Neevis.
4. Review the Navisworks source files found in that area.
5. Click **Transfer/Update Geometry** to bring the returned coordination geometry into Revit.
6. Use **Clear Portal** when the temporary coordination geometry is no longer required.

Portal controls include:

- Show/hide individual Navisworks source files.
- Randomize source colors.
- **Keep Original Colors** from Navisworks.
- Re-transfer/update geometry without intentionally stacking duplicate Portal geometry.
- Progress feedback during geometry transfer.
- Automatic exclusion of the current Revit model from the returned source geometry.

In workshared Revit models, managed Portal geometry uses the temporary **Reeviz_Temp** workset. Clearing the Portal removes its managed geometry and cleans up the temporary workset when it is safe to do so.

Closing the Portal also clears the active Portal session.

**Use Neevis Portal when:** you need surrounding Navisworks coordination geometry visible in Revit to understand a clash or spatial condition without permanently importing the federation into the project.

---

### About Reeviz

Use **About Reeviz** to:

- Check the installed Reeviz version.
- Manage Reeviz appearance/preferences.
- Review update options.
- Submit a bug report or suggestion.
- Open the Reeviz GitHub Releases page.

## Recommended Workflow

For a typical coordination project:

1. Use **ProLink** to prepare and maintain the Revit link setup.
2. Load the applicable Neevis Workspace and use **Analyzer** to review clashes affecting the Revit model.
3. Use **Neevis Portal** when you need Navisworks federation geometry visible around a specific Revit Section Box.
4. Resolve the issue in Revit and update the coordination information through Analyzer/Neevis as required by the project workflow.

## Release Status

- **ProLink** — established Reeviz link-management tool.
- **Analyzer** — BETA.
- **Neevis Portal** — BETA.

Beta tools are intended for active testing. Keep normal project backups and report reproducible issues with the relevant Reeviz session information where possible.

## Links

- GitHub Releases: `https://github.com/mustafahafaec-spec/Reeviz-Releases`
- LinkedIn: `https://www.linkedin.com/in/mustafahaf/`

## Copyright

Copyright © 2026 Mustafa Hesham. All rights reserved.
