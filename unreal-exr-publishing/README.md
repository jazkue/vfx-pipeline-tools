# Unreal EXR Publishing

![77d64a905f176bd04d6e8d134f1292809cdda94e_3RaA.png](images/77d64a905f176bd04d6e8d134f1292809cdda94e_3RaA.png)

A Nuke tool for splitting multilayer EXRs rendered from Unreal Engine into individual outputs and preparing them for publishing. The main objective is to avoid bottlenecks on render farm and only publish dailies using RGBA channels.

## Workflow

![78f8fcadfb06e0e2e0ec9baadf0bd167f911ec4a_3RaA.png](images/78f8fcadfb06e0e2e0ec9baadf0bd167f911ec4a_3RaA.png)

The tool creates the required Nuke graph automatically, creating a read node based on task variables set before launching program.

![e0ab4e4ab53f1b5b39d328f77bc7a82c533f2b83_3RaA.jpeg](images/e0ab4e4ab53f1b5b39d328f77bc7a82c533f2b83_3RaA.jpeg)

**Read → Remove → Write → Publish**

Tool isolates channels and creates output nodes according to the type of channel being processed.

| Channel | Format |
|---|---|
| RGBA | DWAA, 16-bit |
| Position | PIZ, 16-bit |
| Depth | PIZ, 16-bit |
| Normals | PIZ, 16-bit |
| Cryptomatte | ZIP, 32-bit |

And for RGBA channels the workflow creates a custom publishing node based on the write node and a final `cookAll` gizmo, which sends all jobs as batches.

Write nodes will render locally, and publish node will publish daily using RGBA only.

## Technical focus

- Nuke Python automation
- Multilayer EXR processing
- Automatic node creation
- Channel-specific output rules
- Render farm / publishing workflow

## DEMO

\[▶ Watch the demo]\(unreal-exr-publishing/videos/2024-11-25%2015-51-50\_edit.mp4)

Production source code is not included.
