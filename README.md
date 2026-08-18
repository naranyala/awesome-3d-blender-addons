# Awesome 3D Blender Addons (OSS / FOSS)

A curated list of **open source** and **free & open source** extensions (add-ons / extensions) for [Blender](https://www.blender.org/).

Blender itself is licensed under the **GPL**, so all add-ons must be GPL-compatible; most community add-ons are GPL, with some under MIT/BSD/Apache. This list focuses on projects with **public source repositories** and avoids "free-to-use but closed-source" add-ons (marked 🆓 only where a notable free version exists).

> 💡 Legend: 🔓 = Open Source (source available, libre) · 🆓 = Free (gratis) but source not fully open · ⚠️ = caveats (e.g. paid edition exists).

---

## Table of Contents

- [Modeling & Mesh](#modeling--mesh)
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
- [Architecture, AEC & BIM](#architecture-aec--bim)
- [Engineering, Robotics & Technical Science](#engineering-robotics--technical-science)
- [Medical & Dental](#medical--dental)
- [Game Engine Integration](#game-engine-integration)
- [Asset Management](#asset-management)
- [Camera, Lighting & Compositing](#camera-lighting--compositing)
- [Workflow & Utilities](#workflow--utilities)
- [Motion Capture & VFX](#motion-capture--vfx)
- [Render Farms, Distributed & Compute](#render-farms-distributed--compute)
- [Launchers & Version Management](#launchers--version-management)
- [Development & Dev Tools](#development--dev-tools)
- [Specialized, Research & Domain Tools](#specialized-research--and-domain-tools)
- [Before vs After](#before-vs-after)
- [Complementary Workflows & Stacks](#complementary-workflows--stacks)
- [Learning & Community](#learning--community)

---

## Before vs After

This list is useful because it changes the shape of the work, not just the speed. The table below compares what usually happens if you stay with Blender alone versus using the add-ons in this repository.

| Area | Without add-ons | With these add-ons | Pros | Cons / tradeoffs |
| --- | --- | --- | --- | --- |
| Modeling & hard-surface | Manual booleans, snapping, mirroring, and cleanup take more steps and are easier to break. | `ND`, `Bool Tool`, `LoopTools`, `Auto Mirror`, `EdgeFlow`, `Modern Primitive`, `Modifier List`, `CAD Transforms`, `CAD Sketcher`. | Faster blockout, cleaner modifiers, better precision, less repetitive cleanup. | More tooling to learn, overlapping features, and some workflows depend on exact addon versions. |
| Sculpting & retopo | Sculpting can drift into messy topology and manual retopo becomes slow. | `Sculpt Pie`, `Sculpt Tools UI`, `BSurfaces`, `RetopoFlow`, `Instant Meshes`, `AutoRemesher`. | Cleaner topology, faster handoff from sculpt to production mesh, better control over edge flow. | Add-ons can impose their own interaction style and may not fit every artist’s muscle memory. |
| UV & texturing | UV packing, baking, and layered painting are often split across many manual operations. | `Magic UV`, `TexTools`, `UVPackmaster`, `UVPacker`, `SimpleBake`, `Ucupaint`, `Layer Painter`, `DeepBump`, `Sprytile`. | More consistent UVs, faster baking, stronger layered texture workflows, better photo-to-normal conversion. | Some tools are paid or freemium, and the stack can become fragmented if you mix incompatible packers or paint systems. |
| Materials & shading | Material setup is workable, but repeating complex node graphs is tedious. | `Material Nodes`, `PBR Node`, `MaterialX`, `BlenderKit`, `BAM Tool`, `Substance Textures Importer`, `img2mat_pro`. | Reusable materials, quicker lookdev, easier interchange, better library management. | Asset libraries can hide complexity, and not every material system round-trips perfectly across engines. |
| Animation & rigging | Rig building, weighting, face setup, and crowd motion are mostly manual. | `Rigify`, `Animation Nodes`, `Easy Weight`, `Cats Blender Plugin`, `COA Tools`, `CrowdMaster`, `Space Switching`, `animaide`, `StoryPencil`, `Auto-Rig Pro (free build)`, `CharMorph`, `MPFB`, `MB-Lab`. | Faster character creation, better weighting tools, more automation, and more animation-specific workflows. | Character pipelines become more opinionated, and some tools are best for specific targets like VRChat, cut-out animation, or humanoid generation. |
| Procedural & data-driven work | You can do it in nodes or scripts, but large parametric scenes take longer to build and maintain. | `Geometry Nodes`, `Sverchok`, `BagaPie`, `GeoScatter`, `OpenScatter`, `Gscatter`, `Molecular Nodes`, `Bioxel Nodes`, `CSV Importer`, `Data-FX`, `Mesh Maze`, `Modular Tree`, `Scifi Generator`. | Much better reuse, reproducibility, and parameter control for scenes, data, and scientific visualization. | Setup cost is higher, debugging can be harder, and node-heavy scenes may need discipline to stay readable. |
| Simulation & technical domains | Specialized physical, engineering, or scientific tasks usually require manual approximations or external software. | `FLIP Fluids`, `Jet Fluids`, `Molecular Script`, `PPF Contact Solver`, `Phobos`, `BlenderCAM`, `pcb2blender`, `Blendmsh`, `OptiCore`, `BlenderGeoModeller`, `Driving Scenario Creator`, `LinkForge`. | Real domain workflows become possible inside Blender, with better interoperability and more credible technical output. | These tools are narrower in scope, often more technical to configure, and sometimes depend on external solvers or standards. |
| Import, export, and interoperability | File exchange is usually the most fragile part of production. | `glTF 2.0 I/O`, `Better Collada`, `Blender Source Tools`, `Niftools`, `VRM Addon`, `MMD Tools`, `fSpy`, `io_scene_psk_psa`, `Sollumz`, `Mixamo Converter`, `Send to Unreal`, `Godot Engine Exporter`, `Send to Unity`. | Better handoff to engines, DCCs, and pipelines; less rework when moving assets around. | Every target ecosystem has its own constraints, so export success still depends on naming, scale, rigging, and material discipline. |
| Asset, workflow, and delivery | Large scenes get harder to rename, package, annotate, and distribute cleanly. | `Asset Browser`, `Simple Renaming Panel`, `BAM Tool`, `BlendPack`, `Node Wrangler`, `Node Pie`, `MeasureIt`, `3D Print Toolbox`, `Screencast Keys`, `BlendNet`, `Sheepit`, `Blender Launcher V2`. | More repeatable handoff, cleaner libraries, easier team collaboration, and less manual project wrangling. | Tooling overlap is common, and some add-ons improve one stage while adding complexity to another. |
| Niche, research, and domain-specific work | You can force Blender to do a lot, but niche workflows usually stay awkward or external. | `BlenderGeoModeller`, `OptiCore`, `Blendmsh`, `LinkForge`, `PPF Contact Solver`, `Compify`, `Driving Scenario Creator`, `ND`. | Opens up specialized pipelines that would otherwise require another application or a lot of custom scripting. | These are the most version-sensitive tools in the list, so they need the most careful validation before you commit them to production. |

Short version: the upside is speed, consistency, and domain coverage. The cost is more surface area to maintain, more version compatibility to watch, and more decisions about which tool owns which part of the workflow.

## Modeling & Mesh

- [Sverchok](https://github.com/nortikin/sverchok) 🔓 — Node-based parametric/procedural modeling toolkit (GPL).
- [TinyCAD](https://github.com/zeffii/Blender_CAD) 🔓 — CAD-style tools (extend, intersect) for meshes.
- [Mesh Align Plus](https://github.com/egtwoes/MeshAlignPlus) 🔓 — Precise alignment, snapping and measurement.
- [Auto Mirror](https://github.com/braingamer/auto-mirror) 🔓 — Fast mirror/modifier workflow.
- [Fast Carve](https://github.com/jraylab/fast-carve) 🔓 — Boolean carving helper.
- [ND](https://github.com/hugemenace/nd) 🔓 — Non-destructive modeling toolkit (booleans, bevels, generators).
- [Bool Tool](https://docs.blender.org/manual/en/latest/addons/object/bool_tools.html) 🔓 — Built-in boolean operations helper.
- [Extra Objects](https://docs.blender.org/manual/en/latest/addons/add_mesh/extra_objects.html) 🔓 — Built-in collection of extra mesh generators.
- [LoopTools](https://docs.blender.org/manual/en/latest/addons/mesh/looptools.html) 🔓 — Built-in loop tools (bridge, circle, relax…); also used in retopology and UV work.
- [Mifth Tools](https://github.com/mifth/mifthtools) 🔓 — Assorted modeling helpers (edge split, radial clone).
- [EdgeFlow](https://extensions.blender.org/add-ons/edgeflow/) 🔓 — Adjust mesh geometry to curved surfaces.
- [Modern Primitive](https://extensions.blender.org/add-ons/modern-primitive/) 🔓 — Non-destructive primitive modeling.
- [Modifier List](https://extensions.blender.org/add-ons/modifier-list/) 🔓 — Enhanced modifier UI/features.
- [CAD Transforms](https://github.com/s-leger/blender_cad_transforms) 🔓 — CAD-like precision move, rotate, and scale tools.
- [CAD Sketcher](https://github.com/hlorus/CAD_Sketcher) 🔓 — CAD-like precision sketching and constraints inside Blender (also used in AEC/Engineering stacks).

## Sculpting

- [Sculpt Pie](https://github.com/xrogueleaderx/BlenderSculptPie) 🔓 — Pie-menu workflow for sculpting.
- [Sculpt Tools UI](https://github.com/blender/blender/tree/main/release/scripts/addons) 🔓 — Built-in sculpt helpers.
- [BSurfaces GPL](https://github.com/KeithPinson/bsurfaces) 🔓 — Guided quad-remeshing / Grease-Pencil surface (see also Retopology).

## Retopology

- [RetopoFlow](https://github.com/CGCookie/retopoflow) 🔓 — Streamlined retopology toolset (GPL).
- [Instant Meshes (bridge)](https://github.com/wjakob/instant-meshes) 🔓 — Interactive field-aligned mesh generator.
- [AutoRemesher](https://github.com/huxingyi/autoremesher) 🔓 — Auto-retopology to clean all-quad geometry.
- [BSurfaces GPL](https://github.com/KeithPinson/bsurfaces) 🔓 — Quad-by-grease-pencil retopology (see also Sculpting).

## UV & Texturing

- [Magic UV](https://github.com/NumesSanguis/Magic-UV) 🔓 — Advanced UV editing (copy/paste, align, world scale).
- [TexTools](https://github.com/franMarz/TexTools-Blender) 🔓 — UV and texture baking toolkit.
- [UVPackmaster](https://github.com/Maple-Software/uvpackmaster) 🆓⚠️ — GPU packing (core free; pro edition paid).
- [UVPacker](https://www.uv-packer.com/) 🆓⚠️ — Free/libre CPU packer companion.
- [SimpleBake](https://github.com/chartset/simplebake) 🆓 — Easy PBR baking.
- [Ucupaint](https://github.com/ucupumar/ucupaint) 🔓 — Layer-based texture painting (Cycles/EEVEE).
- [Layer Painter](https://github.com/joshuaKnauber/layer_painter) 🔓 — Node-based texture layer system.
- [DeepBump](https://github.com/HugoTini/DeepBump) 🔓 — Generate normal & height maps from photos via ML.
- [Sprytile](https://github.com/CCPRO/Sprytile) 🔓 — Tilemap painting workflow for pixel-art textures.
- [Brushstroke Tools](https://extensions.blender.org/add-ons/brushstroke-tools/) 🔓 — Painting tools by Blender Studio (Geometry Nodes based).

## Materials & Shaders

- [Material Nodes](https://github.com/AdrienDelessert/material_nodes) 🔓 — Material layers via nodes.
- [PBR Node](https://github.com/Andrej730/pbr-node) 🔓 — Quick PBR material setup.
- [MaterialX](https://github.com/AcademySoftwareFoundation/MaterialX) 🔓 — Open standard for materials (Blender support).
- [BlenderKit](https://github.com/BlenderKit/blenderkit) 🔓 — Materials, HDRIs and asset library (add-on GPL; many assets CC0).
- [BAM Tool](https://extensions.blender.org/add-ons/bam/) 🆓 — Mass-install and manage materials.
- [Substance Textures Importer](https://extensions.blender.org/add-ons/substance-textures-importer/) 🔓 — Import Substance exports into Blender.
- [img2mat_pro](https://extensions.blender.org/add-ons/img2mat-pro/) 🔓 — Image palettes, PMS matches, and material callouts.

## Animation & Rigging

- [Rigify](https://docs.blender.org/manual/en/latest/addons/rigging/rigify.html) 🔓 — Built-in automatic rig generation.
- [Animation Nodes](https://github.com/JacquesLucke/animation_nodes) 🔓 — Node-based animation system.
- [Easy Weight](https://github.com/BlenderDefender/easy_weight) 🔓 — Weight painting helpers.
- [Cats Blender Plugin](https://github.com/GiveMeAllYourCats/cats-blender-plugin) 🔓 — Rigging/optimization for VRChat (MIT).
- [COA Tools](https://github.com/ndee85/coa_tools) 🔓 — Cut-out animation toolset (see also Grease Pencil).
- [CrowdMaster](https://github.com/johnbauer4/CrowdMaster) 🔓 — Procedural crowd animation.
- [Space Switching](https://github.com/IngoClemens/blender-space-switching) 🔓 — IK/FK space switching.
- [animaide](https://github.com/arevell/Animaide) 🔓 — Animation curve helper (ghosting, easing, breakdowns).
- [StoryPencil](https://extensions.blender.org/add-ons/storypencil-storyboard-tools/) 🔓 — Storyboard tools (see also Grease Pencil).
- [Auto-Rig Pro (free build)](https://github.com/GunjaGupta1233/autorig-pro-free) 🆓⚠️ — Free subset of the commercial auto-rigger.
- [CharMorph](https://github.com/Upliner/CharMorph) 🔓 — Open source character creation (spiritual successor to MB-Lab), with Rigify support.
- [MPFB](https://github.com/makehumancommunity/mpfb2) 🔓 — MakeHuman Plugin for Blender: parametric human generator with CC0 assets.
- [MB-Lab](https://github.com/animate1978/MB-Lab) 🔓 — Original Manuel Bastioni Lab generator (unmaintained; see CharMorph/MPFB).

## Procedural & Geometry Nodes

- [Geometry Nodes (built-in)](https://docs.blender.org/manual/en/latest/modeling/geometry_nodes/index.html) 🔓 — Native procedural node system.
- [Sverchok](https://github.com/nortikin/sverchok) 🔓 — See Modeling.
- [BagaPie](https://extensions.blender.org/add-ons/bagapie/) 🔓 — Large Geometry Nodes modifiers collection (scatter, arrays, architecture).
- [GeoScatter](https://github.com/Geo-Scatter/geoscatter) 🔓 — Scattering ecosystem (open core).
- [OpenScatter](https://github.com/GitMay3D/OpenScatter) 🔓 — Free/open-source scattering tool.
- [Gscatter](https://www.graswald3d.com/gscatter) 🆓 — Artist-friendly free scattering (Graswald).
- [Molecular Nodes](https://github.com/BradyAJohnston/MolecularNodes) 🔓 — Import & animate molecular structures via Geometry Nodes (see also Specialized).
- [Bioxel Nodes](https://extensions.blender.org/add-ons/bioxel-nodes/) 🔓 — Scientific volumetric data visualization (see also Specialized).
- [Sorcar](https://github.com/aachman98/Sorcar) 🔓 — Procedural modeling using the Node Editor.
- [T3D GN Presets](https://extensions.blender.org/add-ons/t3d-gn-presets/) 🔓 — Useful node-group presets.
- [Geo Nodes Guide](https://extensions.blender.org/add-ons/geo-nodes-guide/) 🔓 — Live docs/examples for Geometry Nodes.
- [CSV Importer](https://extensions.blender.org/add-ons/csv-importer/) 🔓 — Import CSV data into meshes.
- [Data-FX](https://github.com/LandonFerg/Data-FX) 🔓 — Load & visualize data from CSV files.
- [Mesh Maze](https://github.com/elfnor/mesh_maze) 🔓 — Generate mazes on any mesh.
- [Modular Tree](https://github.com/MaximeHerpin/modular_tree) 🔓 — Procedural realistic trees via nodes.
- [Scifi Generator](https://github.com/Stubblefield-Development/scifi-generator) 🔓 — Procedural sci-fi panel generator.

## Simulation & Physics

- [Molecular Script](https://github.com/scorpion81/Blender-Molecular-Script) 🔓 — Particle collision / particle-linking addon.
- [FLIP Fluids](https://github.com/rlguy/Blender-FLIP-Fluids) 🔓 — Liquid fluid simulation (open source core; paid marketplace build).
- [Jet Fluids](https://github.com/PavelBlend/blender_jet_fluids_addon) 🔓 — Jet fluid simulator integration.
- [CubeSurfer](https://github.com/pyromuggle/CubeSurfer) 🔓 — Metaball / meshing helper.
- [PPF Contact Solver](https://github.com/st-tech/ppf-contact-solver) 🔓 (Apache-2.0) — Penetration-free contact solver for shells, solids, rods, rigid bodies, and sand (CUDA GPU or remote; see also Specialized).
- [Driving Scenario Creator](https://github.com/johschmitz/blender-driving-scenario-creator) 🔓 — Build OpenDRIVE / OpenSCENARIO automotive scenes in Blender.
- [Blender Physics (built-in)](https://docs.blender.org/manual/en/latest/physics/index.html) 🔓 — Rigid body, cloth, soft body, fluid, smoke.
- [Phobos](https://github.com/dfki-ric/phobos) 🔓 — Create URDF/SDF/SMURF robot models (see also Engineering).

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
- [BlendNet](https://github.com/state-of-the-art/BlendNet) 🔓 — Distributed rendering / AI on cloud (see also Render Farms).
- [BlenderMCP](https://github.com/ahujasid/blender-mcp) 🔓 — Control Blender from any LLM via the Model Context Protocol (also under Specialized).
- [DeepBump](https://github.com/HugoTini/DeepBump) 🔓 — See UV.

## Photogrammetry & Scanning

- [Photogrammetry Importer](https://github.com/SBCV/Blender-Addon-Photogrammetry-Importer) 🔓 (MIT) — Import Meshroom/COLMAP/Metashape/OpenMVG results + NeRF.
- [Meshroom](https://alicevision.org/) 🔓 — Open-source photogrammetry software (standalone, pairs with Blender).
- [COLMAP](https://colmap.github.io/) 🔓 — Structure-from-motion reconstruction (standalone).
- [MicMac](https://github.com/micmacIGN/micmac) 🔓 — Open-source photogrammetric suite.
- [RealityScan](https://www.capturingreality.com/introducing/realityscan) 🆓 — Free 3D scanning app (capture with phone).

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

## Architecture, AEC & BIM

- [BlenderGIS](https://github.com/domlysz/BlenderGIS) 🔓 — Terrain, OSM, georeferencing from GIS data.
- [Blender-OSM](https://github.com/domlysz/blender-osm) 🔓 — OpenStreetMap 3D buildings/terrain.
- [BlenderGeoModeller](https://github.com/bsomps/BlenderGeoModeller) 🔓 — 3D geological modeling for drill holes, block models, and GemPy workflows.
- [BlenderBIM](https://github.com/IfcOpenShell/IfcOpenShell) 🔓 — IFC/BIM authoring (IfcOpenShell).
- [Speckle](https://github.com/specklesystems/speckle-blender) 🔓 — AEC data interoperability (FOSS core).
- [PyClone](https://github.com/CH3-Dev/pyclone) 🔓 — Parametric cabinet/kitchen designer.
- [Building Tools](https://github.com/ranjian0/building_tools) 🔓 — Procedural building generation.
- [Archimesh](https://github.com/Antonioya/blender-archimesh) 🔓 — Parametric architecture (rooms, windows, stairs).
- [CAD Sketcher](https://github.com/hlorus/CAD_Sketcher) 🔓 — See Modeling (precision CAD workflow).

## Engineering, Robotics & Technical Science

- [BlenderCAM](https://github.com/vasmakk/blender-cam) 🔓 — CNC / CAM toolpath generation (GPL).
- [pcb2blender](https://github.com/Volcomix/pcb2blender) 🔓 — Import PCB designs as 3D models.
- [STEP Importer](https://extensions.blender.org/add-ons/step-importer/) 🔓 — Import STEP files natively (no 3rd-party CAD).
- [OptiCore](https://github.com/CodeFHD/OptiCore) 🔓 — Optical elements and optomechanical components for Blender.
- [Blendmsh](https://github.com/senthurayyappan/blendmsh) 🔓 — Bridge Blender with Gmsh for finite-element mesh generation.
- [Phobos](https://github.com/dfki-ric/phobos) 🔓 — URDF/SDF/SMURF robot model creation (see also Simulation).
- [LinkForge](https://github.com/arounamounchili/linkforge) 🔓 — Compose and validate URDF/XACRO/SRDF robot descriptions from Blender or Python (ROS 2).
- [Molecular Nodes](https://github.com/BradyAJohnston/MolecularNodes) 🔓 — See Procedural (molecular data).
- [Bioxel Nodes](https://extensions.blender.org/add-ons/bioxel-nodes/) 🔓 — See Procedural (volumetric data).

## Medical & Dental

- [B Dental](https://github.com/DavidGamedev/bdental) 🔓 — Open source dental 3D (CBCT, implants, splints).
- [MedBlend](https://blender-addons.org/medblend/) 🔓 — Radiation therapy DICOM plan/image/dose visualization.
- [DICOMator](https://pmc.ncbi.nlm.nih.gov/articles/PMC12738608/) 🔓 — Generate synthetic CT datasets from 3D meshes (OSS add-on).

## Game Engine Integration

- [Send to Unreal](https://github.com/EpicGamesExt/BlenderTools) 🔓 — Epic's Blender→Unreal pipeline.
- [Blender for Unreal Engine](https://github.com/xavierlecas/Blender-For-UnrealEngine-Addons) 🔓 — Export rigs/levels to UE.
- [Godot Engine Exporter](https://github.com/godotengine/godot-blender-exporter) 🔓 — Export to Godot .escn.
- [Send to Unity](https://github.com/EdyJ/blender-to-unity) 🔓 — FBX export helpers for Unity.
- [io_scene_psk_psa](https://github.com/DarklightGames/io_scene_psk_psa) 🔓 — See Import/Export (Unreal).
- [Source Engine Collision Tools](https://extensions.blender.org/add-ons/source-engine-collision-tools/) 🔓 — Source engine collision models.
- [Armory](https://github.com/armory3d/armory) 🔓 — Open source 3D game engine with Blender integration.
- [UPBGE](https://github.com/UPBGE/upbge) 🔓 — Open source game engine forked from Blender Game Engine.
- [Embark Studios Blender Tools](https://github.com/EmbarkStudios/blender-tools) 🔓 — Game-dev workflow tools (import/export, modeling).

## Asset Management

- [Asset Browser (built-in)](https://docs.blender.org/manual/en/latest/files/asset_libraries/index.html) 🔓 — Native asset library.
- [BlenderKit](https://github.com/BlenderKit/blenderkit) 🔓 — See Materials (also materials/HDRIs/assets).
- [Simple Renaming Panel](https://github.com/Weisl/simple_renaming_panel) 🔓 — Batch rename objects/data.
- [BAM Tool](https://extensions.blender.org/add-ons/bam/) 🆓 — See Materials (material manager).
- [BlendPack](https://github.com/MeRahulAhire/BlendPack) 🔓 — Package external assets into a portable archive and relink paths.
- [Pataz Thumbnail Toolz](https://extensions.blender.org/add-ons/pataz-thumbnail-toolz/) 🔓 — Manage asset thumbnails.

## Camera, Lighting & Compositing

- [Gaffer](https://github.com/GregZaal/Gaffer) 🔓 — Lighting and HDRI management.
- [Photographer](https://github.com/chafouin/photographer) 🔓 — Physical camera & lighting controls.
- [Sun Position](https://docs.blender.org/manual/en/latest/addons/lighting/sun_position.html) 🔓 — Built-in sun/sky from geolocation & time.
- [Physical Starlight and Atmosphere](https://github.com/Physical-Starlight-and-Atmosphere/PSA-Blender-Addon) 🔓 — Physically based sky/atmosphere.
- [Auto Exposure](https://github.com/RedHorn/auto-exposure) 🔓 — Automatic camera exposure.
- [camera_shakify](https://github.com/EatTheFuture/camera_shakify) 🔓 — Natural camera shake.
- [Compify](https://github.com/EatTheFuture/compify) 🔓 — Compositing in 3D space for VFX-style node workflows.

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
- [Texel Density Checker](https://extensions.blender.org/add-ons/texel-density-checker/) 🔓 — UV texel density toolset.
- [Mio3 UV](https://extensions.blender.org/add-ons/mio3-uv/) 🔓 — UV editing assistant.
- [Flat UV Mapper](https://extensions.blender.org/add-ons/flat-uv-mapper/) 🔓 — CSG-style planar face UV mapping (tile/offset/rotate).
- [Font Selector](https://extensions.blender.org/add-ons/font-selector/) 🔓 — Live-preview all system fonts on text objects.
- [Lip Sync](https://extensions.blender.org/add-ons/lip-sync/) 🔓 — Automatic lip-sync for armatures.
- [Bas Relief](https://extensions.blender.org/add-ons/bas-relief/) 🔓 — Create bas-reliefs from images.
- [Rigify-To-Unity](https://github.com/vignedev/Rigify-To-Unity) 🔓 — Make Rigify rigs work in Unity.
- [Collection2Empty](https://github.com/ScottRaffertyCG/BlenderCollection2Empty) 🔓 — Convert collections into parented Empties.
- [Blend_My_NFTs](https://github.com/torrinwitty/Blend_My_NFTs) 🔓 — Generate NFT collections from Blender.
- [Brush Manager](https://github.com/CMedinaDev/Brush-Menu) 🔓 — Sculpt/paint brush management.

## Motion Capture & VFX

- [BlendArMocap](https://github.com/semagnum/blendarmocap) 🔓 — Webcam mocap via MediaPipe.
- [Faceit](https://github.com/riedeletc/faceit) 🔓 — Automatic face rigging.
- [Rokoko Video](https://www.rokoko.com/products/video) 🆓⚠️ — Free webcam/video mocap (not OSS).
- [Camera Tracking (built-in)](https://docs.blender.org/manual/en/latest/movie_clip/index.html) 🔓 — Native motion tracking.

## Render Farms, Distributed & Compute

- [Sheepit](https://www.sheepit-renderfarm.com/) 🔓 — Free, distributed community render farm.
- [BlendNet](https://github.com/state-of-the-art/BlendNet) 🔓 — Self-hosted / cloud distributed rendering (see also AI).
- [3S Cloud Render Farm](https://3sfarm.com/) 🆓⚠️ — Commercial cloud farm with free credits.

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

## Specialized, Research & Domain Tools

A grab-bag of niche tools that didn't fit the pipelines above but are full open source.

#### Scientific & Data Visualization
- [SciBlend](https://github.com/SciBlend/SciBlend) 🔓 (GPLv3) — Data import (.vtk/.vtu/.nc/.shp/.vdb), scientific colormaps, legends, compositor tools.
- [BioBlender](https://github.com/MonZop/BioBlender) 🔓 (BSD-2) — Import/elaborate biological molecules.
- [BioBlender 2.1](https://github.com/PabloEnmanuelRamos/BioBlender2.1) 🔓 — Python 3 rewrite for modern Blender.
- [ChemBlender](https://www.chemblender.com/) 🔓 — Molecules & micro/nano structures via geometry nodes.
- [CellBlender](http://mcell.org/) 🔓 — MCell/Blender for cell-scale reaction-diffusion simulation.
- [AstroBlend](http://www.astroblend.com/) 🔓 — Astrophysics visualization integrating the `yt` analysis toolkit.
- [blender_plots](https://github.com/Linusnie/blender_plots) 🔓 — Matplotlib-style plotting inside Blender.
- [BlenderSciViz](https://github.com/zeffii/BlenderSciViz) 🔓 — Scripts to build meshes from functions/CSV data.
- [Rendersynth](https://extensions.blender.org/add-ons/rendersynth/) 🔓 — Generate labeled synthetic data for computer vision.

#### Research-Grade Modeling
- [Polyhedral Splines](https://github.com/UF-CISE-Surflab/blender-polyhedral-splines) 🔓 (WIP) — Convert quad meshes into B-spline patches.
- [Sorcar](https://github.com/aachman98/Sorcar) 🔓 — See Procedural (node-based procedural modeling).
- [CAD Sketcher](https://github.com/hlorus/CAD_Sketcher) 🔓 — See Modeling/Architecture (precision CAD workflow).

#### LLM & AI Tooling
- [BlenderMCP](https://github.com/ahujasid/blender-mcp) 🔓 — Control Blender 3D from any LLM via the Model Context Protocol.

#### Niche Helpers
- [Texel Density Checker](https://extensions.blender.org/add-ons/texel-density-checker/) 🔓 — See Workflow (UV texel density).
- [Mio3 UV](https://extensions.blender.org/add-ons/mio3-uv/) 🔓 — See Workflow (UV editing assistant).
- [Lip Sync](https://extensions.blender.org/add-ons/lip-sync/) 🔓 — See Workflow (automatic lip-sync).
- [Bas Relief](https://extensions.blender.org/add-ons/bas-relief/) 🔓 — See Workflow (bas-reliefs from images).
- [camera_shakify](https://github.com/EatTheFuture/camera_shakify) 🔓 — See Camera & Lighting (camera shake).
- [Compify](https://github.com/EatTheFuture/compify) 🔓 — See Camera & Lighting (compositing in 3D space).
- [Rigify-To-Unity](https://github.com/vignedev/Rigify-To-Unity) 🔓 — See Workflow (Rigify→Unity).
- [Collection2Empty](https://github.com/ScottRaffertyCG/BlenderCollection2Empty) 🔓 — See Workflow (collections→Empties).
- [Source Engine Collision Tools](https://extensions.blender.org/add-ons/source-engine-collision-tools/) 🔓 — See Game Engines (Source collision).
- [ND](https://github.com/hugemenace/nd) 🔓 — See Modeling (non-destructive modeling).

> Notes: duplicate "see also" links above are intentional cross-references only — each tool has its **full entry in one primary section** to avoid maintenance drift.

## Complementary Workflows & Stacks

Practical combinations for common pipelines. Pick the pieces you need per stage.

- **Hard-surface / non-destructive modeling** — `Bool Tool` + `LoopTools` + `Auto Mirror` + `Modifier List` + `EdgeFlow` + `Modern Primitive` + `CAD Sketcher`. Block out forms, cut details, clean loops, and refine topology while keeping a manageable modifier stack.
- **Procedural environments & scattering** — `GeoScatter` / `Gscatter` / `OpenScatter` + `BagaPie` + `Sverchok` + `Geometry Nodes` + `SimpleBake`. Scatter and populate, generate parametric props, then bake PBR for export.
- **Character creation & rigging** — `CharMorph` / `MPFB` / `MB-Lab` + `Rigify` + `Easy Weight` + `Faceit` + `Cats Blender Plugin`. Generate a base human, auto-rig, paint weights, drive the face, and optimize for VRChat.
- **Texturing & baking pipeline** — `Ucupaint` + `Layer Painter` + `TexTools` + `Magic UV` + `DeepBump` + `SimpleBake`. Layered painting, UV prep, derive normal/height from photos, and bake final maps.
- **Architecture, visualization & BIM** — `BlenderBIM` + `Speckle` + `BlenderGIS` + `Archimesh` + `CAD Sketcher` + `Sun Position` + `Physical Starlight & Atmosphere`. Author OpenBIM, sync AEC data, pull terrain/OSM, draft precisely, and light by location.
- **Geological & technical surveying** — `BlenderGeoModeller` + `BlenderGIS` + `Blendmsh` + `MeasureIt`. Model drillhole/block volumes, geo-reference context, export FE meshes, and annotate.
- **Game asset export** — `Send to Unreal` / `Blender for Unreal Engine` + `Mixamo Converter` + `io_scene_psk_psa` + `Simple Renaming Panel` + `3D Print Toolbox`. Model/rig, retarget, export, rename, and validate.
- **Simulation & VFX** — `FLIP Fluids` / `Molecular Script` + `PPF Contact Solver` + `Geometry Nodes` + `BlendNet` / `Sheepit`. Fluids + particles, cloth/solid contact, procedural enhancement, distributed render.
- **Motion capture → final animation** — `BlendArMocap` + `Faceit` + `Rigify` + `Easy Weight` + `Camera Tracking`. Body capture, facial rig, apply to a production rig, solve the camera.
- **Live-action VFX integration** — `fSpy` + `Camera Tracking` + `Photographer` + `Physical Starlight & Atmosphere` + `Cycles`. Match a still or tracked shot, recreate camera/lighting, and render a compositable element.
- **AI-assisted concept & rendering** — `Dream Textures` + `AI Render` + `BlenderNeRF` + `Gaffer` + `Photographer`. Generate concepts/textures, build NeRF scenes, and art-direct lighting.
- **Scientific & data visualization** — `MolecularNodes` + `Bioxel Nodes` + `Data-FX` / `CSV Importer` + `Geometry Nodes`. Molecules, volumes, and tabular data turned into geometry.
- **Photogrammetry → clean model** — `Photogrammetry Importer` + `Meshroom` / `COLMAP` + `Instant Meshes` + `RetopoFlow` + `Ucupaint`. Reconstruct scans, retopo, and texture.
- **Engineering, PCB & technical** — `pcb2blender` + `BlenderCAM` + `MeasureIt` + `CAD Sketcher`. Import PCBs, generate CNC paths, annotate, and precision-draft.
- **2D / storyboard production** — `StoryPencil` + `Grease Pencil Tools` + `GP Tween` + `COA Tools`. Storyboard, refine, tween, and build cut-out animation.
- **Physics simulation research** — `PPF Contact Solver` + `Molecular Script` + `Geometry Nodes` + `fake-bpy-module`. Advanced FEM/contact simulation with scripting and reproducible data.
- **Distributed rendering & dev** — `BlendNet` / `Sheepit` + `Blender Launcher V2` + `fake-bpy-module`. Manage builds, distribute renders, and develop custom add-ons.
- **Asset packaging & handoff** — `BlendPack` + `Simple Renaming Panel` + `Asset Browser` + `Pataz Thumbnail Toolz`. Normalize names, bundle externals, and keep handoff reproducible.
- **Compositing in 3D space** — `Compify` + `Camera Tracking` + `Photographer`. Spatial compositing matched to tracked footage.

## Learning & Community

- [Blender Manual](https://docs.blender.org/manual/en/latest/) 🔓 — Official documentation.
- [Blender Extensions Platform](https://extensions.blender.org/) 🔓 — Official OSS extension registry (900+ add-ons).
- [Blender Artists Forum](https://blenderartists.org/) — Community & add-on releases.
- [BlenderNation](https://www.blendernation.com/) — Daily news, art and tutorials.
- [Bfor Artists](https://github.com/BforArtists/BforArtists) 🔓 — Blender fork with a refined UI.
- [awesome-blender](https://github.com/agmmnn/awesome-blender) 🔓 — The broader community "awesome list".
- [r/blender](https://www.reddit.com/r/blender/) — Reddit community.
- [blender.chat](https://blender.chat/) — Official chat server.
- [Blender Stack Exchange](https://blender.stackexchange.com/) — Q&A.

---

## Contributing

Found an awesome OSS/FOSS Blender extension missing? Open a pull request! Please ensure:

1. The project is **open source** (link to a public source repository) — or clearly marked 🆓 if free-only.
2. It is compatible with a recent Blender release.
3. It fits one of the categories above (or propose a new one), with no existing duplicate entry.

## License

This list is licensed under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). Blender add-ons linked here retain their own respective licenses (mostly GPL-compatible).
