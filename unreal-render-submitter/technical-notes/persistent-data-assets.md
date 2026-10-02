# Persistent Data Assets

A small Unreal workflow for keeping editor-tool values between sessions.

## Approach

A `Primary Data Asset` stores the persistent state as JSON.

The editor widget can:

1. Read the stored values.
2. Update the JSON object.
3. Save the Data Asset.
4. Load the values again when the project starts.

This provides persistent configuration for editor tooling without requiring an external configuration file.

## Technical focus

- Blueprint Classes
- Primary Data Assets
- Editor Utility Widgets
- JSON
- Asset persistence

The production implementation is not included.
