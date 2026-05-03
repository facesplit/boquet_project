# Local AI Assets

This folder is reserved for local AI runtime assets (ComfyUI, models, caches, and tools).

Rules for this repository:
- Keep this `_README_local.md` file tracked in Git.
- Do not commit large local binaries, model files, or generated caches.
- Use this directory for machine-specific setup only.

If you need to run local generation:
- Install and run ComfyUI locally.
- Point backend settings to your local ComfyUI endpoint.
- Keep all heavyweight assets inside this folder so the repository stays lightweight.
