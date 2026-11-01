# Engine execution

## Common preflight
Inspect the project package manifest, lockfile, available CLIs and current documentation. Reuse installed dependencies. Check Node version against the selected tool's requirements. Do not install every engine to make one video. Do not copy shell snippets blindly across PowerShell and bash.

If upstream skill instructions exist locally, read the relevant entrypoint. Otherwise fetch current official docs or the narrowly relevant upstream file. The local workflow still supports planning when network access is absent. Never invent endpoint names, component props, CLI flags, or render commands.

## HyperFrames
Use for HTML/CSS compositions and its production/registry workflow.
- Official repository: https://github.com/heygen-com/hyperframes
- Docs: https://hyperframes.heygen.com/introduction
- Optional upstream core skill setup: npx hyperframes skills update (installs exactly the core set and is safe in non-interactive agent runs; `npx skills add heygen-com/hyperframes` without `--skill` installs all published skills when run non-interactively)
- Core references: hyperframes, hyperframes-cli, hyperframes-registry, media-use.
- License: Apache-2.0.
Inspect the current CLI help and quickstart before scaffolding. Preserve its render contract and seekable timeline. Use catalog blocks when they match the brief; verify previews and adapt their design to the user's brand.

## Remotion
Use for React compositions and product films.
- Official skills: https://github.com/remotion-dev/skills
- Docs: https://www.remotion.dev/docs/
- Optional skill setup: npx skills add remotion-dev/skills
- License: not open source. Remotion is free for individuals and small companies, but larger for-profit companies need a paid company license. Before choosing Remotion for a business, point the user to https://github.com/remotion-dev/remotion/blob/main/LICENSE.md and let them confirm eligibility; prefer HyperFrames when that is unresolved and the brief allows it.
Use remotion-best-practices as the broad entrypoint, or the current create, markup, studio and render references as needed. Inspect composition IDs, durationInFrames, fps and dimensions. Drive animated values from the frame and FPS. Preload media and fonts, and ensure studio and final render agree. Keep unrelated Next.js runtime code separate from video rendering unless integration was requested.

## Shotcraft with Remotion
- Repository: https://github.com/Vincentwei1021/video-shotcraft
- Read its current SKILL.md and the chosen shot card before adapting its implementation.
Use its recipe/gallery resources as optional production references, not an extra renderer. Use actual product screenshots. Match camera perspective, masks, movement, and typography to the story. Native editor/Workbench/CapCut exports are optional and must be implemented and checked before promised.

## fal.ai media assets
- Skills: https://github.com/fal-ai-community/skills
- CLI: https://github.com/fal-ai-community/genmedia-cli (install per its README for bash or PowerShell, then `genmedia setup`; the key comes from FAL_KEY or secret storage, never from chat)
Read genmedia and model-routing plus the relevant cinematography/storytelling/commercial workflow. Confirm executable availability and configured credentials.
The CLI exposes `models` (discovery), `schema`, `pricing`, `upload`, `run` and `status`; verify flags through `genmedia --help` before use. Model availability and costs change. Persist asynchronous job IDs and download finished assets into the project. Assemble footage in the one chosen renderer.

## Output QA with ffmpeg
Use these when ffprobe/ffmpeg are installed (both ship with ffmpeg). They read the rendered file, so they prove what the render produced, not what the code intended.

Container and streams (duration, size, frame rate, codec, pixel format, audio):
```sh
ffprobe -v error -show_entries format=duration:stream=codec_type,codec_name,width,height,r_frame_rate,pix_fmt,sample_rate,channels -of json out.mp4
```

Still frames to review the opening, a transition and the last frame (use `-sseof` for "from the end"):
```sh
ffmpeg -v error -ss 0.5 -i out.mp4 -frames:v 1 qa-open.png
ffmpeg -v error -sseof -0.1 -i out.mp4 -frames:v 1 qa-end.png
```

Contact sheet of the whole video, one frame per second:
```sh
ffmpeg -v error -i out.mp4 -vf "fps=1,scale=320:-1,tile=6x5" -frames:v 1 qa-sheet.png
```

Audio peaks and loudness (true peak should stay below about -1 dBTP; streaming platforms normalise to roughly -14 LUFS):
```sh
ffmpeg -hide_banner -i out.mp4 -af ebur128=peak=true -f null -
```

Re-encode to the default delivery format when an engine exports something else:
```sh
ffmpeg -i in.mov -c:v libx264 -pix_fmt yuv420p -crf 18 -preset slow -c:a aac -b:a 192k -movflags +faststart out.mp4
```

Quote paths that contain spaces. In PowerShell, call `ffmpeg.exe` directly and keep the quoted filter strings intact.
