---
layout: Conceptual
title: Use custom environments in Teams immersive events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-immersive-custom-environments
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how to prepare and use custom environments in Teams immersive events.
author: Sean-Kerawala
ms.author: sekerawa
manager: tyadams
ms.service: msteams
ms.subservice: teams-events
ms.topic: concept-article
ms.date: 2026-05-15T00:00:00.0000000Z
locale: en-us
document_id: 5bad930a-b953-b8af-cb3b-f155ecdac0d6
document_version_independent_id: 5bad930a-b953-b8af-cb3b-f155ecdac0d6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-immersive-custom-environments.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-immersive-custom-environments
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-immersive-custom-environments.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: af416c75-76ef-a04c-9a42-fcb023a93487
---

# Use custom environments in Teams immersive events - Microsoft Teams | Microsoft Learn

Note

This feature is now generally available.

Microsoft Teams Immersive events support custom 3D environments that you build and upload yourself. This article explains how to prepare a custom environment, meet file requirements, and upload it so it's available when you schedule an immersive event.

## Overview

Bringing a custom environment into a Teams immersive event involves three stages:

1. **Build**: Create your 3D environment in a 3D authoring tool and export it as a `.glb` file.
2. **Upload**: Add the environment to an Immersive Collection in the Teams desktop app.
3. **Publish**: Create a template from the environment and use it when scheduling an event.

## File requirements and recommendations

Before you upload, make sure your assets meet the following guidelines. Files outside these ranges might fail to upload or cause performance issues during an event.

### Environment file (`.glb`)

| Attribute | Recommended | Limit |
| --- | --- | --- |
| File size | 100 MB or less | Uploads must be under 250 MB |
| Textures | Under 60 megapixels¹ | — |
| Draw calls² | Under 500 | ~1,000 for min spec devices |

¹1 megapixel = 1024 x 1024, 4 megapixels = 2048 x 2048, and so on. ²Draw calls can be measured via **Settings** &gt; **Developer Settings** &gt; **Performance Profiler**.

Note

Files larger than 100 MB aren't blocked at upload time, but might cause degraded event performance. Files approaching 250 MB might fail to upload entirely. The upload process doesn't block files larger than 100 MB, but large files might cause degraded event performance. Files approaching 250 MB might fail to upload entirely.

## Prepare your environment: Create a `.glb` file

Teams Immersive environments must be provided as a `.glb` file (binary glTF). You can create `.glb` files using any 3D authoring tool that supports glTF export, including:

- **Unity** via the `com.unity.cloud.gltfast` package
- **Blender** via the built-in glTF 2.0 export under **File** &gt; **Export** &gt; **glTF 2.0**
- **Autodesk Maya** via the glTF export plugin
- **Autodesk 3ds Max** via the Babylon.js or Gestaltor glTF exporter
- **Cinema 4D** via third-party glTF exporters

Regardless of which tool you use, validate your `.glb` in an external viewer such as the [Babylon.js Sandbox](https://sandbox.babylonjs.com/) before uploading to Teams.

The following steps walk through the export process using **Unity**, which has additional cleanup requirements due to its game engine object model. If you're using a different tool, your workflow will vary.

## Unity GLB workflow (recommended practices)

### Build your scene in Unity

- Use prefabs to speed up scene creation.
- Use **Universal Render Pipeline/Lit** for all Materials.
- Create a single root node in the Hierarchy that contains the entire environment.
- Use the `com.unity.cloud.gltfast` plugin to export the root node as a `.glb`.

### Mesh topology

- Keep geometry low poly (no LODs are supported in Teams Immersive).

### UVs and textures

- UV unwrap based on desired visual fidelity.
- Use tiling materials to maintain high texel density.
- Use a second UV channel for lightmaps.
- Enable **Generate Lightmap UVs** in Unity where possible.

### Lighting

- Only directional light is baked into Teams Immersive.
- Point and spot lights are real-time only; use them sparingly.

### Materials

- Use **Universal Render Pipeline/Lit** for all materials.
- Use any relevant texture slots (Albedo, Normal, etc.) as needed.

### Collision

- Rendered geometry is used for collision by default.
- For custom collision (for example, smoothing stairs), use transparent planes.

### Convert an existing Unity project into a `.glb`

#### Prerequisites

- Unity with the **Universal Render Pipeline (URP)** configured
- Git source control (recommended)
- The `com.unity.cloud.gltfast` package

#### Step 1: (Optional) Back up your project

1. Commit your project to Git.
2. Duplicate the scene before changes.

#### Step 2: Clean up the scene

- Remove baked lights and cameras
- Remove legacy Mesh prefabs and scripting objects
- Remove Teams-managed objects (for example, screen share surfaces, text objects)
- Uninstall old Mesh Toolkit or sample packages

#### Step 3: Update materials and shaders

1. Use **URP/Lit** (preferred) for all materials.
2. Convert transparent materials to appropriate URP/Lit equivalents when needed.

#### Step 4: Adjust renderers

1. Replace non-mesh renderers (for example, SpriteRenderer → mesh quad).
2. Remove all `LODGroup` components.

#### Step 5: Export the scene

1. Add `com.unity.cloud.gltfast`.
2. Go to **File** &gt; **Export Scene** &gt; **glTF-Binary (.glb)**.
3. Save inside the `Assets` folder.

#### Step 6: Validate the export

1. Import the `.glb` into a new Unity scene.
2. Inspect for missing materials or geometry issues.

#### Step 7: Iterate if needed

1. Fix issues in the source scene.
2. Repeat export and validation.

Tip

If the `.glb` fails in external viewers, re-import and export again to resolve format issues.

## Upload the environment to Teams

1. Open Teams desktop and go to **Meet** &gt; **Manage**.
2. Scroll to **Immersive Collections**.
3. Create or open a Collection.
4. Select **Environments** &gt; **Upload environment**.
5. Enter details and upload the file.

## Publish the environment as a template

1. Find the environment in **Environments**.
2. Select **...** &gt; **Create a template**.
3. The template appears in the event scheduler.

From the scheduler, you can:

- Customize the template (images, video, 3D content)
- Save configurations for reuse
- Launch events using the template