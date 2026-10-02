# Pipeline Tools

Selected pipeline tools developed for VFX and real-time production workflows.

The original production source code is not included. This repository documents the tools, workflows, and technical solutions through screenshots and concise case studies.

## Projects

### [Unreal Publish Template](./unreal-publish-template/)
Connects Unreal rendering with a Nuke publishing workflow, generating context-based output paths and rebuilding the rendered EXR inside Nuke.

**Unreal Engine · Nuke · Python · EXR**

### [Unreal EXR Publishing](./unreal-exr-publishing/)
Automates the processing of multilayer Unreal EXRs into individual channel/view outputs and prepares the resulting Nuke graph for publishing.

**Nuke · Python · EXR · Deadline**

### [Unreal Render Submitter](./unreal-render-submitter/)
A custom Unreal Editor widget for preparing render outputs and publishing the resulting version to the production tracking system.

**Unreal Engine · Blueprints · Python · ShotGrid**

