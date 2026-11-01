# Installation and invocation

This folder is a portable skill: keep SKILL.md at video-studio/SKILL.md and references beside it.

## Codex
Copy the video-studio folder into your Codex skills directory (usually ~/.codex/skills/), or .agents/skills/video-studio/ inside a project for that project. Invoke $video-studio or select it in the skills picker after discovery refresh/new turn. The bundled agents/openai.yaml is optional UI metadata.

## Claude Code
Copy the same folder to ~/.claude/skills/video-studio/ for personal use, or .claude/skills/video-studio/ inside a project for that project. Invoke /video-studio after the client discovers it, or describe the video and let the skill load from its description.

## Claude web or Desktop
If your Claude client/account offers custom Skill uploads, upload video-studio.zip through that feature and enable it. The ZIP has one root folder, video-studio, containing SKILL.md.
If custom Skills are unavailable, add SKILL.md and the relevant references as Project knowledge and request "Use video-studio". Project knowledge does not create a slash command.
Local CLI access, rendering, and provider credentials depend on the actual Claude environment. A successful skill upload does not enable local tools by itself.

## Runtime dependencies
Install only the chosen engine when creating a video. HyperFrames/Remotion need a compatible Node runtime and their rendering dependencies. Output QA uses ffprobe/ffmpeg when available. fal.ai requires its supported client/CLI and a configured funded API account for paid generation. Plans and storyboards can be made without these dependencies.
