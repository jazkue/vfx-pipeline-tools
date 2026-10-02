# Unreal EXR Publishing

![77d64a905f176bd04d6e8d134f1292809cdda94e_3RaA.png](images/77d64a905f176bd04d6e8d134f1292809cdda94e_3RaA.png)

A Nuke tool for processing multilayer EXRs rendered from Unreal Engine and preparing them for publishing.

The main goal was to reduce render-farm load by publishing dailies from the RGBA channels only, while keeping the output paths consistent with the production pipeline for rendering directly and locally from Unreal Engine.

## Workflow

![78f8fcadfb06e0e2e0ec9baadf0bd167f911ec4a_3RaA.png](images/78f8fcadfb06e0e2e0ec9baadf0bd167f911ec4a_3RaA.png)

The tool generates output paths for local rendering based on the current production context and pipeline conventions. These paths can be copied directly into Unreal Engine's render settings.

![da26a783b2ed95e6778cb5a6b57866b9e5140915_3RaA.jpeg](images/da26a783b2ed95e6778cb5a6b57866b9e5140915_3RaA.jpeg)

After rendering, the user returns to Nuke. The tool creates a Read node from the production context and automatically builds the required processing graph.

![e0ab4e4ab53f1b5b39d328f77bc7a82c533f2b83_3RaA.jpeg](images/e0ab4e4ab53f1b5b39d328f77bc7a82c533f2b83_3RaA.jpeg)

**Read → Remove → Write → Publish**

The tool isolates individual channels and creates output nodes according to the type of data being processed.

| Channel | Format |
|---|---|
| RGBA | DWAA, 16-bit |
| Position | PIZ, 16-bit |
| Depth | PIZ, 16-bit |
| Normals | PIZ, 16-bit |
| Cryptomatte | ZIP, 32-bit |

For RGBA channels, the workflow creates a custom publishing node based on the Write node, followed by a `cookAll` gizmo that batches the rendering and publishing process.

Write nodes render the individual outputs locally, while the publishing node publishes the RGBA version for dailies.

## Technical focus

- Nuke Python automation
- Multilayer EXR processing
- Automatic node creation
- Channel-specific output rules
- Render farm and publishing workflows

## Demo

https://github.com/user-attachments/assets/fe760048-676a-4f6b-9eb0-6fff6dfdfa68

Production source code is not included.