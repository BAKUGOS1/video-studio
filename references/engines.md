# Engine execution

## Common preflight
Inspect the project package manifest, lockfile, available CLIs and current documentation. Reuse installed dependencies. Check Node version against the selected tool's requirements. Do not install every engine to make one video. Do not copy shell snippets blindly across PowerShell and bash.

If upstream skill instructions exist locally, read the relevant entrypoint. Otherwise fetch current official docs or the narrowly relevant upstream file. The local workflow still supports planning when network access is absent. Never invent endpoint names, component props, CLI flags, or render commands.

## HyperFrames
Use for HTML/CSS compositions and its production/registry workflow.
- Official repository: https://github.com/heygen-com/hyperframes
- Docs: https://hyperframes.heygen.com/introduction
- Optional upstream core skill setup: npx hyperframes skills update
- Core references: hyperframes, hyperframes-cli, hyperframes-registry, media-use.
Inspect the current CLI help and quickstart before scaffolding. Preserve its render contract and seekable timeline. Use catalog blocks when they match the brief; verify previews and adapt their design to the user's brand.

## Remotion
Use for React compositions and product films.
- Official skills: https://github.com/remotion-dev/skills
- Docs: https://www.remotion.dev/docs/
- Optional skill setup: npx skills add remotion-dev/skills
Use remotion-best-practices as the broad entrypoint, or the current create, markup, studio and render references as needed. Inspect composition IDs, durationInFrames, fps and dimensions. Drive animated values from the frame and FPS. Preload media and fonts, and ensure studio and final render agree. Keep unrelated Next.js runtime code separate from video rendering unless integration was requested.

## Shotcraft with Remotion
- Repository: https://github.com/Vincentwei1021/video-shotcraft
- Read its current SKILL.md and the chosen shot card before adapting its implementation.
Use its recipe/gallery resources as optional production references, not an extra renderer. Use actual product screenshots. Match camera perspective, masks, movement, and typography to the story. Native editor/Workbench/CapCut exports are optional and must be implemented and checked before promised.

## fal.ai media assets
- Skills: https://github.com/fal-ai-community/skills
- CLI: https://github.com/fal-ai-community/genmedia-cli
Read genmedia and model-routing plus the relevant cinematography/storytelling/commercial workflow. Confirm executable availability and configured credentials.
The current workflow exposes discovery, schema, pricing, upload, run, and status operations; verify flags through CLI help before use. Model availability and costs change. Persist asynchronous job IDs and download finished assets into the project. Assemble footage in the one chosen renderer.
