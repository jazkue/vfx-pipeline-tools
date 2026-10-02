# Unreal Render Submitter

A custom Unreal Editor widget for preparing and publishing render outputs.

## Workflow

1. Enter the production context.
2. Generate the output directory and filename.
3. Copy the settings to Unreal's Render Queue.
4. Render.
5. Return to the Submitter and publish the result.

The widget uses context such as task, version, layer, view, and colorspace to generate the output paths.

## Persistent data

The Submitter also uses a Data Asset to store configuration between sessions.

See [Persistent Data Assets](./technical-notes/persistent-data-assets.md).

## Technical focus

- Unreal Editor tooling
- Editor Utility Widgets
- Blueprint / Data Assets
- JSON persistence
- Render Queue integration
- Publishing workflows

The production source code is not included.
