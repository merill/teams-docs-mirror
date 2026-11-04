---
layout: Conceptual
title: 3D model guidance - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/immersive-events-3d-models
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Guidance for creating and adding 3D models to immersive events in Teams
author: Sean-Kerawala
ms.author: sekerawa
manager: tyadams
ms.service: msteams
ms.topic: concept-article
ms.date: 2025-11-13T00:00:00.0000000Z
ms.subservice: teams-events
locale: en-us
document_id: 69347c56-23fb-c0bd-fd81-0b3f86e70250
document_version_independent_id: 69347c56-23fb-c0bd-fd81-0b3f86e70250
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/immersive-events-3d-models.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: immersive-events-3d-models
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/immersive-events-3d-models.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 64569f76-4872-9dfa-186e-0f07500c34c0
---

# 3D model guidance - Microsoft Teams | Microsoft Learn

## Overview

In immersive events today, organizers can select an immersive template (a customizable environment containing content) such as Cascades, Oasis, and Canvas. These environments enable all hands, showcases, and company events, among other scenarios you envision. To make the experience unique for your scenario, we recommend adding objects including to Image, Video, Text, and 3D model. 3D models in particular require a little extra consideration but provide great return for your time investment by providing a more engaging and immersive experience.

## Getting started with 3D models

The 3D model object is a unique content object as it enables spatial viewing of 3D models for attendees of immersive events. The 3D model allows you to specify the URL of a .glb file stored in OneDrive or SharePoint. Once loaded, the 3D model can be repositioned and scaled to match your desired attendee outcome. For models added to immersive events, the following considerations help ensure a great viewing and animation experience for .glb format 3D models added to the space.

To add a 3D model, schedule an immersive event, then select **Customize in immersive**. Once you enter a customization session, open the **Editor** &gt; **Catalog** &gt; select **3D model**. See the [step-by-step tutorial](https://support.microsoft.com/office/customize-an-immersive-event-in-microsoft-teams-9b8100eb-11b9-4b55-82d6-718655101d53) to see the no-code flow that enables you to easily add multiple in a matter of minutes (or seconds!).

If you want your experience to be rich in content, we recommend adding at least two 3D model objects to your immersive event. Thankfully, you don't have to be a 3D artist, or have one on your team, to assemble the assets you need to realize your vision. There are many ways to obtain premade models free, or at a reasonable cost, which we introduce here. We also discuss how you can get started on creating your own 3D models. First, let's start by explaining the file format of the 3D model you add to your immersive event.

### What are GLTF and GLB?

**GLTF (Graphics Library Transmission Format)**: This open standard file format is designed for efficient transmission and loading of 3D scenes and models. It's human-readable and based on JSON (JavaScript Object Notation), making it easy for developers to understand and modify. However, the readability results in larger file sizes compared to binary formats.

**GLB (.glb)**: This file format is the binary version of GLTF. It encapsulates all the components of a 3D model (including textures, animations, and other data) into a single binary file. This file format is more compact and efficient for transmission, as it reduces file size and enhances loading speed, making it ideal for real-time applications and web use.

Tip

For those new to 3D models, many websites offer an intuitive way to download .glb files and 3D modeling tools present clear export options for turning your creation into the .glb format.

### Optimize and convert existing 3D models

Many organizations might already have 3D models on hand for business purposes. We encourage reaching out to people across your organization to curate content. Organizations that have their own 3D models can export models as .glb (in your tool of choice), then store in SharePoint or OneDrive before specifying the URL to an object during an immersive event customization session.

For best practices on preparing your own 3D models for use in Immersive events in Teams, see Microsoft's [real-time 3D model conversion and optimization guide](/en-us/dynamics365/mixed-reality/guides/3d-content-guidelines/overview).

### Find or create 3D models (.glb)

#### Premade assets

There are numerous websites that offer pre-made 3D models at reasonable or no cost. Some of the more popular ones are:

- [3D Viewer](https://apps.microsoft.com/detail/9nblggh42ths?hl=en-us&amp;gl=US&amp;ocid=pdpshare)
- [SketchFab](https://sketchfab.com/)
- [Turbo Squid](https://www.turbosquid.com/)
- [CGTrader](https://www.cgtrader.com/)
- [Mixamo](https://www.mixamo.com/#/)
- [Blender Market](https://www.blendermarket.com/)
- [3DExport](https://3dexport.com/)
- [3D Warehouse](https://3dwarehouse.sketchup.com/)

You might also want to consider "kit bashing," where you download a "kit" of premade 3D parts. Kit bashing allows you to assemble a complex model without the need for advanced modeling skills. In many cases the 3D parts don't have UV maps set up--you have to take care of that part. You can find many kits at [ArtStation](https://www.artstation.com/), for example.

### Make your own 3D models

If you can't find premade 3D models that fulfill your needs, it might be worth your while to develop 3D modeling skills or find a creator to help. At its highest level, 3D modeling is a vast, complex skill that encompasses numerous subdisciplines.

As you can imagine, it requires considerable time and effort to become a highly proficient 3D modeler. The good news is that you don't have to become an expert to reap some benefits. Simply having a few basic skills in your toolbox, such as the ability to change materials on a model or convert a high-poly model to a low-poly one, can result in significant improvements to your experiences.

Here are some of the more popular 3D modeling programs.

- [Autodesk Maya](https://www.autodesk.com/products/maya/overview?term=1-YEAR&amp;tab=subscription)
- [Blender](https://www.blender.org/)
- [3ds Max](https://www.autodesk.com/products/3ds-max/overview?term=1-YEAR&amp;tab=subscription)
- [Houdini](https://www.sidefx.com/)
- [ZBrush](http://pixologic.com/features/about-zbrush.php)

## Model performance

Depending on your scenario, scene complexity might differ. It’s important to be mindful of your attendees (end user’s) device capabilities.

Consider the following framework for approximate scene complexity using moderately complex 3D models:

| Device | Low scene complexity | Medium scene complexity | High scene complexity |
| --- | --- | --- | --- |
| PC, Mac, and Meta Quest 3 devices | Objects: 1-3 3D model objects, Triangles: 100k per object, Materials: 50, Textures: Forty-eight 1k textures per object | Objects: 4-10 3D model objects, Triangles: 30k per object, Materials: 24, Textures: Twelve 2k textures per object | Objects: 10+ 3D model objects, Triangles: 10k per object, Materials: 8, Textures: Three 4k textures per object |

*\*The table is framed as a per-object set of recommendations.*

Important

If most of your attendees are going to be on minimum spec devices, try to target low complexity events. Keep in mind that image, video, and audio Objects can be added in addition to the 3D model object usage recommendations given they consume less performance budget from the immersive event experience.

Common pitfalls & recommendations:

- Too many triangles: Keep your gLTF files under 100k triangles.
- Too many materials (batches/draw calls): Less than 50 materials recommended.
- Too much texture memory (number of pixels and megapixels across all textures): Stay under 48 megapixels, which could be forty-eight 1k textures, twelve 2k textures, or three 4k textures.