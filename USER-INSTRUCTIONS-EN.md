# Megamind Content Studio

## User Instructions

Megamind Content Studio is a Windows desktop app for generating research drafts and turning them into social posts with a local Ollama model.

This Version 1 release is not fully self-contained.

Before you open the app, make sure these prerequisites are installed on the target Windows machine:

1. Python 3.14 or another compatible Python 3.x version available in `PATH`
2. Ollama installed and available in `PATH`
3. Node.js installed if you plan to run the project from source

## Required Ollama Setup

The app expects Ollama to be available at:

- `http://localhost:11434`

The default model for this release is:

- `fil-catalyst`

If the model does not exist yet, the project launcher can create it from the local `Modelfile`.

## Recommended Way To Start The App

For the most reliable startup, use the project launcher:

1. Double-click `run.bat`
2. Wait for the backend health check to pass
3. The desktop app will open automatically

The launcher will:

- recreate the Python virtual environment
- start the FastAPI backend
- wait for backend readiness
- then open the Electron app

## How To Use The App

### Screen 1

1. Enter a topic
2. Optionally add context
3. Click `Start Research`
4. Wait for the app to finish the Ollama research call
5. When complete, the button changes to `Research Complete`
6. Click `Let's Check - Researched Data`

### Screen 2

1. Review the generated research text
2. Edit the text if needed
3. Choose the platform and mood
4. Click `Cook a Social Post`
5. When complete, the button changes to `Format Complete`
6. Click `View Final Post`

### Screen 3

1. Review the final post
2. Edit it directly if needed
3. Use `Flash Copy` to copy the final result
4. Use the export buttons in the sidebar if needed

## Known Release Notes For Version 1

- This release depends on a local Python backend
- This release depends on a local Ollama installation
- Long Ollama requests can take several minutes
- If the backend is unavailable, generation will fail before Ollama is called

## Troubleshooting

### If the app opens but generation fails

Check:

1. Ollama is running
2. The backend is running on `http://127.0.0.1:8000`
3. The model `fil-catalyst` exists in Ollama

### If the backend does not start

Check:

1. Python is installed and available in `PATH`
2. Port `8000` is free
3. Port `11434` is free for Ollama

### If Windows warns about the installer

This build is not code signed, so Windows SmartScreen may show a warning on some systems.
