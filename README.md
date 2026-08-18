# Awesome 3D Blender Addons (OSS / FOSS)

A curated list of **open source** and **free & open source** extensions (add-ons / extensions) for [Blender](https://www.blender.org/).

Blender itself is licensed under the **GPL**, so all add-ons must be GPL-compatible; most community add-ons are GPL, with some under MIT/BSD/Apache. This list focuses on projects with **public source repositories**.

> 💡 Legend: 🔓 = Open Source (libre, source available) · 🆓 = Free (gratis) but source may be restricted. Entries marked 🆓 only are noted because they are free to use yet not fully open source. Always verify the current license before use.

---

## Complementary Add-on Stacks

Practical combinations for common workflows. Each stack joins tools that cover different stages of the same task; choose the pieces you need rather than installing every option.

| Use case | Combine | How the tools complement each other |
| --- | --- | --- |
| Hard-surface and product modeling | [Modern Primitive](#modeling) + [Bool Tool](#modeling) + [EdgeFlow](#modeling) + [Modifier List](#modeling) | Block out clean forms, cut details, refine topology, then keep the modifier stack manageable. |
| Precise architectural modeling | [CAD Sketcher](#modeling) + [Archimesh](#modeling) + [Building Tools](#gis-architecture-bim--cad) + [BlenderBIM](#gis-architecture-bim--cad) | Sketch constrained plans, generate architectural elements, develop building forms, and exchange IFC/BIM data. |
| Geolocated environments | [BlenderGIS](#gis-architecture-bim--cad) + [Blender-OSM](#gis-architecture-bim--cad) + [BagaPie](#procedural--geometry-nodes) + [Sun Position](#camera--lighting) | Bring in terrain and map data, populate it procedurally, and match the lighting to a real location and time. |
| Retopology through textured asset | [RetopoFlow](#retopology) + [Magic UV](#uv--texturing) + [TexTools](#uv--texturing) + [Ucupaint](#uv--texturing) | Rebuild clean topology, unwrap efficiently, prepare texture sets, and paint layered materials in Blender. |
| Scan cleanup and look development | [Photogrammetry Importer](#photogrammetry--scanning) + [RetopoFlow](#retopology) + [DeepBump](#uv--texturing) + [SimpleBake](#uv--texturing) | Import reconstructed scans, make them animation- or game-ready, derive surface detail, and bake the result. |
| Game-ready characters | [CharMorph](#animation--rigging) or [MPFB](#animation--rigging) + [Rigify](#animation--rigging) + [Easy Weight](#animation--rigging) + [VRM Addon](#import--export--interop) | Create a base character, generate and refine its rig, then export an avatar-friendly VRM. |
| Unreal or Godot delivery | [RetopoFlow](#retopology) + [TexTools](#uv--texturing) + [Send to Unreal](#game-engine-integration) or [Godot Engine Exporter](#game-engine-integration) | Prepare meshes and UVs before handing assets off through an engine-specific export pipeline. |
| Procedural natural scenes | [Geometry Nodes](#procedural--geometry-nodes) + [BagaPie](#procedural--geometry-nodes) + [Modular Tree](#procedural--geometry-nodes) + [Gaffer](#camera--lighting) | Build a controllable scene system, scatter set dressing, generate vegetation, and iterate HDRI lighting quickly. |
| Data and scientific visualization | [CSV Importer](#procedural--geometry-nodes) or [Data-FX](#procedural--geometry-nodes) + [Geometry Nodes](#procedural--geometry-nodes) + [MeasureIt](#workflow--utilities) | Import datasets, turn them into visual geometry, and add clear measurements or annotations. |
| Mocap character animation | [BlendArMocap](#motion-capture--vfx) + [Faceit](#motion-capture--vfx) + [Rigify](#animation--rigging) + [animaide](#animation--rigging) | Capture body motion, create a facial rig, apply it to a production rig, and polish the resulting curves. |
| Live-action VFX integration | [fSpy](#import--export--interop) + [Camera Tracking](#motion-capture--vfx) + [Photographer](#camera--lighting) + [Cycles](#rendering--engines) | Match a still or tracked shot, recreate its camera and lighting, then render a compositable element. |
| Repeatable rendering and handoff | [Asset Browser](#asset-management) + [Simple Renaming Panel](#asset-management) + [BAM Tool](#materials--shaders) + [BlendNet](#render-farms--distributed) | Standardize reusable assets and names, manage material libraries, then distribute final renders. |

---

## Table of Contents

- [Complementary Add-on Stacks](#complementary-add-on-stacks)
- [Modeling](#modeling)
- [Sculpting](#sculpting)
- [Retopology](#retopology)
- [UV & Texturing](#uv--texturing)
- [Materials & Shaders](#materials--shaders)
- [Animation & Rigging](#animation--rigging)
- [Procedural & Geometry Nodes](#procedural--geometry-nodes)
- [Simulation & Physics](#simulation--physics)
- [Grease Pencil](#grease-pencil)
- [Rendering & Engines](#rendering--engines)
- [AI & Machine Learning](#ai--machine-learning)
- [Photogrammetry & Scanning](#photogrammetry--scanning)
- [Import / Export & Interop](#import--export--interop)
- [GIS, Architecture, BIM & CAD](#gis-architecture-bim--cad)
- [Engineering, PCB & Science](#engineering-pcb--science)
- [Medical & Dental](#medical--dental)
- [Game Engine Integration](#game-engine-integration)
- [Asset Management](#asset-management)
- [Workflow & Utilities](#workflow--utilities)
- [Camera & Lighting](#camera--lighting)
- [Motion Capture & VFX](#motion-capture--vfx)
- [Render Farms & Distributed](#render-farms--distributed)
- [Launchers & Version Management](#launchers--version-management)
- [Development & Dev Tools](#development--dev-tools)
- [Learning & Community](#learning--community)
- [Complementary Add-ons & Workflows](#complementary-add-ons--workflows)

---

## Modeling

- [Sverchok](https://github.com/nortikin/sverchok) 🔓 — Node-based parametric/procedural modeling toolkit (GPL).
- [TinyCAD](https://github.com/zeffii/Blender_CAD) 🔓 — CAD-style tools (extend, intersect) for meshes.
- [Mesh Align Plus](https://github.com/egtwoes/MeshAlignPlus) 🔓 — Precise alignment, snapping and measurement.
- [Auto Mirror](https://github.com/braingamer/auto-mirror) 🔓 — Fast mirror/modifier workflow.
- [Fast Carve](https://github.com/jraylab/fast-carve) 🔓 — Boolean carving helper.
- [Bool Tool](https://docs.blender.org/manual/en/latest/addons/object/bool_tools.html) 🔓 — Built-in boolean operations helper.
- [Extra Objects](https://docs.blender.org/manual/en/latest/addons/add_mesh/extra_objects.html) 🔓 — Built-in collection of extra mesh generators.
- [LoopTools](https://docs.blender.org/manual/en/latest/addons/mesh/looptools.html) 🔓 — Built-in loop tools (bridge, circle, relax…).
- [Mifth Tools](https://github.com/mifth/mifthtools) 🔓 — Assorted modeling helpers (edge split, radial clone).
- [EdgeFlow](https://extensions.blender.org/add-ons/edgeflow/) 🔓 — Adjust mesh geometry to curved surfaces.
- [Modern Primitive](https://extensions.blender.org/add-ons/modern-primitive/) 🔓 — Non-destructive primitive modeling.
- [Modifier List](https://extensions.blender.org/add-ons/modifier-list/) 🔓 — Enhanced modifier UI/features.
- [CAD Sketcher](https://github.com/hlorus/CAD_Sketcher) 🔓 — CAD-like precision tools inside Blender (GPL).
- [Archimesh](https://github.com/Antonioya/blender-archimesh) 🔓 — Parametric architecture (rooms, windows, roofs).

## Sculpting

- [BSurfaces GPL](https://github.com/KeithPinson/bsurfaces) 🔓 — Guided quad-remeshing / grease-pencil surface.
- [Sculpt Pie](https://github.com/xrogueleaderx/BlenderSculptPie) 🔓 — Pie-menu workflow for sculpting.
- [Sculpt Tools UI](https://github.com/blender/blender/tree/main/release/scripts/addons) 🔓 — Built-in sculpt helpers.

## Retopology

- [RetopoFlow](https://github.com/CGCookie/retopoflow) 🔓 — Streamlined retopology toolset (GPL).
- [Instant Meshes (bridge)](https://github.com/wjakob/instant-meshes) 🔓 — Interactive field-aligned mesh generator.
- [AutoRemesher](https://github.com/huxingyi/autoremesher) 🔓 — Auto-retopology to clean all-quad geometry.
- [LoopTools](https://docs.blender.org/manual/en/latest/addons/mesh/looptools.html) 🔓 — Built-in (see Modeling).

## UV & Texturing

- [Magic UV](https://github.com/NumesSanguis/Magic-UV) 🔓 — Advanced UV editing (copy/paste, align, world scale).
- [TexTools](https://github.com/franMarz/TexTools-Blender) 🔓 — UV and texture baking toolkit.
- [UVPackmaster](https://github.com/Maple-Software/uvpackmaster) 🆓⚠️ — GPU packing (pro version paid; core free).
- [SimpleBake](https://github.com/chartset/simplebake) 🆓 — Easy PBR baking.
- [Ucupaint](https://github.com/ucupumar/ucupaint) 🔓 — Layer-based texture painting (Cycles/EEVEE).
- [Layer Painter](https://github.com/joshuaKnauber/layer_painter) 🔓 — Node-based texture layer system.
- [DeepBump](https://github.com/HugoTini/DeepBump) 🔓 — Generate normal & height maps from photos via ML.
- [Sprytile](https://github.com/CCPRO/Sprytile) 🔓 — Tilemap painting workflow for pixel-art textures.
- [Brushstroke Tools](https://extensions.blender.org/add-ons/brushstroke-tools/) 🔓 — Painting tools by Blender Studio (Geometry Nodes based).

## Materials & Shaders

- [Material Nodes](https://github.com/AdrienDelessert/material_nodes) 🔓 — Material layers via nodes.
- [PBR Node](https://github.com/Andrej730/pbr-node) 🔓 — Quick PBR material setup.
- [BlenderKit](https://github.com/BlenderKit/blenderkit) 🔓 — Asset library (add-on GPL, many assets CC0).
- [MaterialX](https://github.com/AcademySoftwareFoundation/MaterialX) 🔓 — Open standard for materials (Blender support).
- [Physical Starlight and Atmosphere](https://github.com/Physical-Starlight-and-Atmosphere/PSA-Blender-Addon) 🔓 — Physically based sky/atmosphere.
- [BAM Tool](https://extensions.blender.org/add-ons/bam/) 🆓 — Mass-install and manage materials.
- [Font Selector](https://extensions.blender.org/add-ons/font-selector/) 🔓 — Live-preview all system fonts on text objects.
- [Substance Textures Importer](https://extensions.blender.org/add-ons/substance-textures-importer/) 🔓 — Import Substance exports into Blender.

## Animation & Rigging

- [Rigify](https://docs.blender.org/manual/en/latest/addons/rigging/rigify.html) 🔓 — Built-in automatic rig generation.
- [Animation Nodes](https://github.com/JacquesLucke/animation_nodes) 🔓 — Node-based animation system.
- [Easy Weight](https://github.com/BlenderDefender/easy_weight) 🔓 — Weight painting helpers.
- [Cats Blender Plugin](https://github.com/GiveMeAllYourCats/cats-blender-plugin) 🔓 — Rigging/optimization for VRChat (MIT).
- [COA Tools](https://github.com/ndee85/coa_tools) 🔓 — Cut-out animation toolset.
- [CrowdMaster](https://github.com/johnbauer4/CrowdMaster) 🔓 — Procedural crowd animation.
- [Space Switching](https://github.com/IngoClemens/blender-space-switching) 🔓 — IK/FK space switching.
- [animaide](https://github.com/arevell/Animaide) 🔓 — Animation curve helper (ghosting, ease, etc.).
- [StoryPencil](https://extensions.blender.org/add-ons/storypencil-storyboard-tools/) 🔓 — Storyboard tools (Grease Pencil 2D/3D).
- [Auto-Rig Pro (free build)](https://github.com/GunjaGupta1233/autorig-pro-free) 🆓⚠️ — Free subset of the commercial auto-rigger.
- [CharMorph](https://github.com/Upliner/CharMorph) 🔓 — Open source character creation (spiritual successor to MB-Lab), with Rigify support.
- [MPFB](https://github.com/makehumancommunity/mpfb2) 🔓 (GPLv3) — MakeHuman Plugin for Blender: parametric human generator with CC0 assets.
- [MB-Lab](https://github.com/animate1978/MB-Lab) 🔓 — Original Manuel Bastioni Lab character generator (now unmaintained; see CharMorph/MPFB).

## Procedural & Geometry Nodes

- [Geometry Nodes (built-in)](https://docs.blender.org/manual/en/latest/modeling/geometry_nodes/index.html) 🔓 — Native procedural node system.
- [Sverchok](https://github.com/nortikin/sverchok) 🔓 — See Modeling.
- [BagaPie](https://extensions.blender.org/add-ons/bagapie/) 🔓 — Large Geometry Nodes modifiers collection (scatter, arrays, architecture).
- [GeoScatter](https://github.com/Geo-Scatter/geoscatter) 🔓 — Scattering ecosystem (open core).
- [Gscatter](https://www.graswald3d.com/gscatter) 🆓 — Artist-friendly free scattering (Graswald).
- [Molecular Nodes](https://github.com/BradyAJohnston/MolecularNodes) 🔓 — Import & animate molecular structures via Geometry Nodes.
- [Bioxel Nodes](https://extensions.blender.org/add-ons/bioxel-nodes/) 🔓 — Scientific volumetric data visualization.
- [T3D GN Presets](https://extensions.blender.org/add-ons/t3d-gn-presets/) 🔓 — Useful node-group presets.
- [Geo Nodes Guide](https://extensions.blender.org/add-ons/geo-nodes-guide/) 🔓 — Live docs/examples for Geometry Nodes.
- [CSV Importer](https://extensions.blender.org/add-ons/csv-importer/) 🔓 — Import CSV data into meshes.
- [Data-FX](https://github.com/LandonFerg/Data-FX) 🔓 — Load & visualize data from CSV files.
- [Mesh Maze](https://github.com/elfnor/mesh_maze) 🔓 — Generate mazes on any mesh.
- [Modular Tree](https://github.com/MaximeHerpin/modular_tree) 🔓 — Procedural realistic trees via nodes.
- [Scifi Generator](https://github.com/Stubblefield-Development/scifi-generator) 🔓 — Procedural sci-fi panel generator.

## Simulation & Physics

- [Molecular Script](https://github.com/scorpion81/Blender-Molecular-Script) 🔓 — Particle collision/addon.
- [FLIP Fluids](https://github.com/rlguy/Blender-FLIP-Fluids) 🔓 — Liquid fluid simulation (open source core; paid marketplace build).
- [Jet Fluids](https://github.com/PavelBlend/blender_jet_fluids_addon) 🔓 — Jet fluid simulator integration.
- [CubeSurfer](https://github.com/pyromuggle/CubeSurfer) 🔓 — Metaball / meshing helper.
- [Blender Physics (built-in)](https://docs.blender.org/manual/en/latest/physics/index.html) 🔓 — Rigid body, cloth, soft body, fluid, smoke.
- [Phobos](https://github.com/dfki-ric/phobos) 🔓 — Create URDF/SDF/SMURF robot models.

## Grease Pencil

- [Grease Pencil Tools](https://github.com/Pullusb/greasepencil-addon) 🔓 — Box decomposition, import/export.
- [COA Tools](https://github.com/ndee85/coa_tools) 🔓 — See Animation.
- [StoryPencil](https://extensions.blender.org/add-ons/storypencil-storyboard-tools/) 🔓 — See Animation.
- [GP Tween](https://extensions.blender.org/add-ons/gp-tween/) 🔓 — Quick Grease Pencil tweening.

## Rendering & Engines

- [Cycles](https://www.cycles-renderer.org/) 🔓 — Built-in path tracer (GPL).
- [EEVEE](https://docs.blender.org/manual/en/latest/render/eevee/index.html) 🔓 — Built-in real-time renderer.
- [LuxCoreRender](https://github.com/LuxCoreRender/BlendLuxCore) 🔓 — Physically based unbiased renderer (Apache-2).
- [YafaRay](https://github.com/YafaRay/YafaRay) 🔓 — Open source ray tracer (LGPL).
- [Appleseed](https://github.com/appleseedhq/blenderseed) 🔓 — Open source GI rendering engine.
- [Mitsuba](https://github.com/mitsuba-renderer/mitsuba-blender) 🔓 — Research-oriented retargetable renderer.
- [RenderMan for Blender](https://github.com/prman-pkgs/RenderManForBlender) 🔓 — Pixar RenderMan integration (open source add-on).
- [AMD Radeon ProRender](https://github.com/GPUOpen-LibrariesAndSDKs/RadeonProRenderBlenderAddon) 🔓 — Cross-platform GPU renderer (Apache-2).
- [Blend4Web](https://www.blend4web.com/) 🔓 — Framework for interactive 3D on the web (archived but OSS).

## AI & Machine Learning

- [Dream Textures](https://github.com/carson-katri/dream-textures) 🔓 — Stable Diffusion inside Blender.
- [AI Render](https://github.com/benrugg/AI-Render) 🔓 — Render with Stable Diffusion / AI.
- [BlenderNeRF](https://github.com/maximeraafat/BlenderNeRF) 🔓 — NeRF / Gaussian Splatting setup helper.
- [BlenderProc](https://github.com/DLR-RM/BlenderProc) 🔓 — Procedural data generation for ML.
- [Infinigen](https://github.com/princeton-vl/infinigen) 🔓 — Procedural natural scene generator (Blender-based).
- [BlendNet](https://github.com/state-of-the-art/BlendNet) 🔓 — Distributed rendering / AI on cloud.
- [DeepBump](https://github.com/HugoTini/DeepBump) 🔓 — See UV.

## Photogrammetry & Scanning

- [Photogrammetry Importer](https://github.com/SBCV/Blender-Addon-Photogrammetry-Importer) 🔓 (MIT) — Import Meshroom/COLMAP/Metashape/OpenMVG results + NeRF.
- [Meshroom](https://alicevision.org/) 🔓 — Open-source photogrammetry software (standalone, pairs with Blender).
- [COLMAP](https://colmap.github.io/) 🔓 — Structure-from-motion reconstruction (standalone).
- [MicMac](https://github.com/micmacIGN/micmac) 🔓 — Open-source photogrammetric suite.

## Import / Export & Interop

- [glTF 2.0 I/O](https://github.com/KhronosGroup/glTF-Blender-IO) 🔓 — Built-in Khronos glTF importer/exporter.
- [Better Collada](https://github.com/godotengine/collada-exporter) 🔓 — Improved Collada export.
- [Blender Source Tools](https://github.com/ValveSoftware/blender_source_tools) 🔓 — Valve Source engine export.
- [Niftools](https://github.com/niftools/blender_niftools) 🔓 — Bethesda/Gamebryo .nif import/export.
- [VRM Addon](https://github.com/saturday06/VRM_Addon_for_Blender) 🔓 — VRM avatar import/export.
- [MMD Tools](https://github.com/MMD-Blender/blender_mmd_tools) 🔓 — MikuMikuDance import/export.
- [X3D / Web3D](https://docs.blender.org/manual/en/latest/addons/io_scene_x3d.html) 🔓 — Built-in X3D import/export.
- [fSpy](https://github.com/stuffmatic/fSpy-Blender) 🔓 — Camera matching from still images.
- [io_scene_psk_psa](https://github.com/DarklightGames/io_scene_psk_psa) 🔓 — Unreal PSK/PSA import/export.
- [Sollumz](https://github.com/Sollumz/Sollumz) 🔓 — Grand Theft Auto V modding suite.
- [Mixamo Converter](https://github.com/enziop/mixamo_converter) 🔓 — Convert Mixamo animations for Unreal with root motion.

## GIS, Architecture, BIM & CAD

- [BlenderGIS](https://github.com/domlysz/BlenderGIS) 🔓 — Terrain, OSM, georeferencing from GIS data.
- [Blender-OSM](https://github.com/domlysz/blender-osm) 🔓 — OpenStreetMap 3D buildings/terrain.
- [BlenderBIM](https://github.com/IfcOpenShell/IfcOpenShell) 🔓 — IFC/BIM authoring (IfcOpenShell).
- [Speckle](https://github.com/specklesystems/speckle-blender) 🔓 — AEC data interoperability (FOSS core).
- [PyClone](https://github.com/CH3-Dev/pyclone) 🔓 — Parametric cabinet/kitchen designer.
- [Building Tools](https://github.com/ranjian0/building_tools) 🔓 — Procedural building generation.
- [CAD Sketcher](https://github.com/hlorus/CAD_Sketcher) 🔓 — See Modeling.
- [Archimesh](https://github.com/Antonioya/blender-archimesh) 🔓 — See Modeling.

## Engineering, PCB & Science

- [BlenderCAM](https://github.com/vasmakk/blender-cam) 🔓 — CNC / CAM toolpaths (GPL).
- [pcb2blender](https://github.com/Volcomix/pcb2blender) 🔓 — Import PCB designs as 3D models.
- [Molecular Nodes](https://github.com/BradyAJohnston/MolecularNodes) 🔓 — See Procedural.
- [Bioxel Nodes](https://extensions.blender.org/add-ons/bioxel-nodes/) 🔓 — See Procedural.
- [Phobos](https://github.com/dfki-ric/phobos) 🔓 — See Simulation (robotics URDF/SDF).

## Medical & Dental

- [B Dental](https://github.com/DavidGamedev/bdental) 🔓 — Open source dental 3D (CBCT, implants, splints).

## Game Engine Integration

- [Send to Unreal](https://github.com/EpicGamesExt/BlenderTools) 🔓 — Epic's Blender→Unreal pipeline.
- [Blender for Unreal Engine](https://github.com/xavierlecas/Blender-For-UnrealEngine-Addons) 🔓 — Export rigs/levels to UE.
- [Godot Engine Exporter](https://github.com/godotengine/godot-blender-exporter) 🔓 — Export to Godot .escn.
- [Send to Unity](https://github.com/EdyJ/blender-to-unity) 🔓 — FBX export helpers for Unity.
- [Armory](https://github.com/armory3d/armory) 🔓 — Open source 3D game engine integrated with Blender.
- [UPBGE](https://github.com/UPBGE/upbge) 🔓 — Open source game engine forked from Blender Game Engine.
- [Embark Studios Blender Tools](https://github.com/EmbarkStudios/blender-tools) 🔓 — Game-dev workflow tools (import/export, modeling).

## Asset Management

- [BlenderKit](https://github.com/BlenderKit/blenderkit) 🔓 — See Materials.
- [Asset Browser (built-in)](https://docs.blender.org/manual/en/latest/files/asset_libraries/index.html) 🔓 — Native asset library.
- [Simple Renaming Panel](https://github.com/Weisl/simple_renaming_panel) 🔓 — Batch rename objects/data.
- [BAM Tool](https://extensions.blender.org/add-ons/bam/) 🆓 — See Materials.

## Workflow & Utilities

- [Node Wrangler](https://docs.blender.org/manual/en/latest/addons/node/node_wrangler.html) 🔓 — Built-in node editing shortcuts.
- [Node Pie](https://extensions.blender.org/add-ons/node-pie/) 🔓 — Add nodes faster via pie menu.
- [Hot Node](https://extensions.blender.org/add-ons/hot-node/) 🔓 — Add nodes like typing.
- [quickmenu](https://github.com/passivestar/quickmenu) 🔓 — Customizable quick-access menu.
- [Screencast Keys](https://github.com/nutti/Screencast-Keys) 🔓 — Display keystrokes on screen (tutorials).
- [Right Mouse Navigation](https://extensions.blender.org/add-ons/right-mouse-navigation/) 🔓 — Game-style walk navigation.
- [Apply Modifiers with Shape Keys](https://extensions.blender.org/add-ons/apply-modifiers-with-shape-keys/) 🔓 — Fix "modifier cannot be applied" error.
- [3D Print Toolbox](https://extensions.blender.org/add-ons/3d-print-toolbox/) 🔓 — Utilities for 3D printing (overlap, thickness checks).
- [MeasureIt](https://extensions.blender.org/add-ons/measureit/) 🔓 — Measurements and annotations.
- [Blend_My_NFTs](https://github.com/torrinwitty/Blend_My_NFTs) 🔓 — Generate NFT collections from Blender.
- [Brush Manager](https://github.com/CMedinaDev/Brush-Menu) 🔓 — Sculpt/paint brush management.

## Camera & Lighting

- [Gaffer](https://github.com/GregZaal/Gaffer) 🔓 — Lighting and HDRI management.
- [Photographer](https://github.com/chafouin/photographer) 🔓 — Physical camera & lighting controls.
- [Sun Position](https://docs.blender.org/manual/en/latest/addons/lighting/sun_position.html) 🔓 — Built-in sun/sky from geolocation & time.
- [Auto Exposure](https://github.com/RedHorn/auto-exposure) 🔓 — Automatic camera exposure.

## Motion Capture & VFX

- [BlendArMocap](https://github.com/semagnum/blendarmocap) 🔓 — Webcam mocap via MediaPipe.
- [Faceit](https://github.com/riedeletc/faceit) 🔓 — Automatic face rigging.
- [Rokoko Video](https://www.rokoko.com/products/video) 🆓⚠️ — Free webcam/video mocap (not OSS).
- [Camera Tracking (built-in)](https://docs.blender.org/manual/en/latest/movie_clip/index.html) 🔓 — Native motion tracking.

## Render Farms & Distributed

- [Sheepit](https://www.sheepit-renderfarm.com/) 🔓 — Free, distributed community render farm.
- [BlendNet](https://github.com/state-of-the-art/BlendNet) 🔓 — Self-hosted / cloud distributed rendering (see AI).

## Launchers & Version Management

- [Blender Launcher V2](https://github.com/DotBow/Blender-Launcher-V2) 🔓 — Manage official builds (standalone client).
- [Blender Version Manager](https://github.com/DotBow/Blender-Version-Manager) 🔓 — Minimal download manager (standalone).

## Development & Dev Tools

- [fake-bpy-module](https://github.com/nutti/fake-bpy-module) 🔓 — Fake Blender Python API for code completion.
- [Geometry Script](https://github.com/carson-katri/geometry-script) 🔓 — Scripting API for Geometry Nodes.
- [Node To Python](https://extensions.blender.org/add-ons/node-to-python/) 🔓 — Turn node groups into Python code.
- [Node Annotator](https://extensions.blender.org/add-ons/node-annotator/) 🔓 — Document your node trees.
- [Advanced Blender Add-on](https://github.com/eliemichel/AdvancedBlenderAddon) 🔓 — Add-on starter kit / design patterns.
- [3DN BIP](https://github.com/3dninjas/3dn-bip) 🔓 — Python library for fast image previews in add-ons.

## Learning & Community

- [Blender Manual](https://docs.blender.org/manual/en/latest/) 🔓 — Official documentation.
- [Blender Extensions Platform](https://extensions.blender.org/) 🔓 — Official OSS extension registry (900+ add-ons).
- [Blender Artists Forum](https://blenderartists.org/) — Community & add-on releases.
- [BlenderNation](https://www.blendernation.com/) — Daily news, art and tutorials.
- [BforArtists](https://github.com/BforArtists/BforArtists) 🔓 — Blender fork with a refined UI.
- [awesome-blender](https://github.com/agmmnn/awesome-blender) 🔓 — The broader "awesome" list this page is inspired by.
- [r/blender](https://www.reddit.com/r/blender/) — Reddit community.
- [blender.chat](https://blender.chat/) — Official chat server.
- [Blender Stack Exchange](https://blender.stackexchange.com/) — Q&A.

---

## Complementary Add-ons & Workflows

Many OSS/FOSS add-ons shine when **combined** for a specific pipeline. Below are battle-tested stacks that work well together (all entries link to the sections above).

### Hard-surface / Non-destructive Modeling
- **Bool Tool** + **LoopTools** + **Auto Mirror** + **Modifier List** + **EdgeFlow** + **Modern Primitive**
- Boolean cut with Bool Tool, clean up loops with LoopTools/EdgeFlow, mirror details with Auto Mirror, and drive everything non-destructively via Modifier List.

### Procedural Environments & Scattering
- **GeoScatter** / **Gscatter** + **BagaPie** + **Sverchok** + **Geometry Nodes** + **SimpleBake**
- Scatter vegetation/assets with GeoScatter, build parametric props with BagaPie/Sverchok, then bake PBR maps with SimpleBake for export.

### Character Creation & Rigging
- **CharMorph** / **MPFB** + **Rigify** + **Easy Weight** + **Faceit** + **Cats Blender Plugin**
- Generate a base human (CharMorph/MPFB), auto-rig with Rigify, paint weights with Easy Weight, rig the face with Faceit, and optimize for VRChat with Cats.

### Texturing & Baking Pipeline
- **Ucupaint** + **Layer Painter** + **TexTools** + **Magic UV** + **SimpleBake** + **DeepBump**
- Layered painting in Ucupaint/Layer Painter, UV prep with Magic UV/TexTools, generate normal/height maps with DeepBump, bake final maps with SimpleBake.

### Architecture, Visualization & BIM
- **BlenderBIM** + **Speckle** + **BlenderGIS** + **Archimesh** + **CAD Sketcher** + **Sun Position** + **Physical Starlight and Atmosphere**
- Author OpenBIM with BlenderBIM, sync with AEC tools via Speckle, pull real terrain/OSM with BlenderGIS, draft with Archimesh/CAD Sketcher, light with Sun Position + PSA.

### Game Asset Export
- **Send to Unreal** / **Blender for Unreal Engine** + **Mixamo Converter** + **io_scene_psk_psa** + **Simple Renaming Panel** + **3D Print Toolbox**
- Model/rig in Blender, retarget Mixamo animations, export to UE/Unreal (PSK/PSA), batch-rename with Simple Renaming Panel, and validate meshes with 3D Print Toolbox.

### Simulation & VFX
- **FLIP Fluids** / **Molecular Script** + **Geometry Nodes** + **BlendNet** / **Sheepit**
- Run fluid/particle sims, enhance with Geometry Nodes, then distribute the final render via BlendNet or Sheepit.

### Motion Capture to Final Animation
- **BlendArMocap** + **Faceit** + **Rigify** + **Easy Weight** + **Camera Tracking**
- Capture body with BlendArMocap, face with Faceit, apply rig via Rigify/Easy Weight, and solve camera with built-in tracking.

### AI-assisted Concept & Rendering
- **Dream Textures** + **AI Render** + **BlenderNeRF** + **Gaffer** + **Photographer**
- Generate concepts/textures with Dream Textures/AI Render, build NeRF scenes with BlenderNeRF, and art-direct lighting with Gaffer + Photographer.

### Scientific & Data Visualization
- **MolecularNodes** + **Bioxel Nodes** + **Data-FX** + **CSV Importer** + **Geometry Nodes**
- Import molecules (MolecularNodes), volumetric data (Bioxel Nodes), and tabular data (Data-FX/CSV Importer), all driven by Geometry Nodes.

### Photogrammetry to Clean Model
- **Photogrammetry Importer** + **Meshroom** / **COLMAP** + **Instant Meshes** + **RetopoFlow** + **Ucupaint**
- Reconstruct with Meshroom/COLMAP, import via Photogrammetry Importer, auto-retopo with Instant Meshes/RetopoFlow, then texture with Ucupaint.

### Engineering, PCB & Technical
- **pcb2blender** + **BlenderCAM** + **MeasureIt** + **CAD Sketcher**
- Import PCB layouts with pcb2blender, generate CNC toolpaths with BlenderCAM, annotate with MeasureIt, and do precision drafting with CAD Sketcher.

### 2D / Storyboard Production
- **StoryPencil** + **Grease Pencil Tools** + **GP Tween** + **COA Tools**
- Storyboard with StoryPencil, refine with Grease Pencil Tools, tween with GP Tween, and build cut-out animation with COA Tools.

### Distributed Rendering & Dev
- **BlendNet** / **Sheepit** + **Blender Launcher V2** + **fake-bpy-module**
- Manage builds with Blender Launcher V2, distribute renders with BlendNet/Sheepit, and develop custom add-ons with fake-bpy-module.

---

## Contributing

Found an awesome OSS/FOSS Blender extension missing? Open a pull request! Please ensure:

1. The project is **open source** (link to a public source repository) — or clearly marked 🆓 if free-only.
2. It is compatible with a recent Blender release.
3. It fits one of the categories above (or propose a new one).

## License

This list is licensed under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). Blender add-ons linked here retain their own respective licenses (mostly GPL-compatible).
