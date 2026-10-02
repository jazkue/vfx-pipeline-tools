# Pipeline Tools

Selected pipeline tools developed for VFX and real-time production workflows.

![b99e01a152aede1882484e21f08d906e.png](./assets/b99e01a152aede1882484e21f08d906e.png)

The original production source code is not included. This repository documents the tools, workflows, and technical solutions through screenshots and concise case studies.

## Projects

### [Unreal ↔ Nuke Publishing Pipeline](./unreal-nuke-publishing/)

![95b9a3cda1f4a70a9faeb7d2ba1c2a28.png](./assets/95b9a3cda1f4a70a9faeb7d2ba1c2a28.png)

A Nuke-based workflow for preparing Unreal render paths, processing multilayer EXRs, and publishing outputs. The workflow was designed to reduce render-farm load by publishing dailies from RGBA channels only, while keeping render paths consistent with the production pipeline.

**Unreal Engine · Nuke · Python · EXR · Deadline**

### [Unreal Render Submitter](./unreal-render-submitter/)

![f95da1f30197d223bbf1efdef0b3f712.png](./assets/f95da1f30197d223bbf1efdef0b3f712.png)

A custom Unreal Editor widget for preparing render outputs and publishing the resulting version to the production tracking system.

**Unreal Engine · Blueprints · Python · ShotGrid**