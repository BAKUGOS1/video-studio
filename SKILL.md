---
name: video-studio
description: Plan, create, edit, preview, and render polished AI-assisted videos, product promos, explainers, and cinematic multi-shot stories. Combines HyperFrames or Remotion rendering, Shotcraft-style product direction, and fal.ai footage workflows.
---

# Video Studio

One production workflow from brief to editable source and verified video. Work in the user's language. Claude Code invocation: /video-studio. Codex invocation: $video-studio. Natural-language requests also work.

This is an original orchestration skill, not a bundled copy of upstream engines, shot libraries, or paid generation services. It works without other skills for planning and direction; execution requires the selected runtime or available media tools.

## Route the work

Preserve the existing project engine and the user's explicit choices. Otherwise:
- HTML/CSS motion design and standalone videos: HyperFrames.
- Existing React/Remotion projects, precise React animation, or product films using Shotcraft recipes: Remotion.
- Realistic or stylized generated footage: fal.ai as an asset source, then assemble with the chosen renderer.
- Product launch films: use the product direction workflow in references/direction.md. Retrieve a Shotcraft card only when it helps; do not imply its library is bundled.
- No execution tools, credentials, or renderer: finish the script, storyboard, shot prompts, timing, and an explicit execution handoff. Do not claim a video was rendered.

Choose one renderer per composition. A hybrid means generated assets plus that renderer, not competing animation engines in one timeline.

Before engine work, read references/engines.md. For cinematic shots and product films, read references/direction.md. For fresh tool syntax and optional upstream resources, follow references/sources.md. Read references/portability.md for installation or Claude web limitations.

## Brief and production plan

Infer what the conversation already gives: audience, message, duration, aspect ratio, language, brand, assets, narration, output path, and cost constraints. Ask only for missing inputs that materially prevent progress. For an otherwise unspecified short promo, state assumptions: 20 seconds, 1920x1080, 30 fps, one clear message. Do not assume permission for paid generation from those defaults.

Inspect actual logos, screenshots, footage, fonts, source code, and applicable project instructions before inventing visuals. Use real product UI and accurate copy. Apply repository brand rules when working in that repository; do not force Phere styling on unrelated brands.

Write a concise brief and shot list before implementation. Each shot needs its purpose, frame range, visual asset, copy/narration, movement, transition, and audio cue. Give each shot enough time to read; narration length determines timing when supplied. Establish the opening promise and a final payoff or useful CTA.

## Asset generation

Prefer existing user assets when suitable. For generated footage:
1. Discover a currently supported endpoint; inspect its schema, pricing, duration and resolution before submitting.
2. Define framing, subject action, camera movement, light, palette, and continuity constraints separately. Use reference frames for product or scene consistency.
3. Generate a representative shot first, review it, then expand the sequence.
4. Save request IDs before polling. Resume known jobs; check their state before retrying to avoid duplicate charges.
5. Track prompts, model/endpoint, source references, job IDs, local asset paths, usage rights, and actual cost when known.

Use provider credentials from configured secret storage or environment variables without printing them. Never request API keys in chat. Honor existing spending authorization; if none exists, provide an estimate and get a budget before billable requests. Do not re-ask when the session already grants that budget. Limit retries to the remaining budget.

Keep text, logos, and accurate interface details in the code-rendered overlay when generated footage would distort them.

## Build and preview

Keep source editable. Implement timing with seekable frame/time functions, not wall-clock timers or random values that change between renders. Seed any randomness. Resolve assets and fonts before rendering. Use engine-native animation APIs and current documentation.

Compose a hierarchy of foreground subject, supporting context, and readable copy. Prefer a few intentional transitions over an effect on every cut. Align major changes to meaningful narration or musical beats. Use licensed audio; keep speech intelligible and music ducked below narration.

Produce a draft preview before an expensive full-resolution render. Inspect the opening, middle, ending, transition boundaries, and the busiest frame. Correct clipping, unreadable type, distorted assets, broken continuity, missing fonts, and dead frames. Review the moving preview as well as still frames.

## Verify and deliver

Render using the selected engine's documented commands. Inspect the actual result with available media tools: duration, dimensions, frame rate, codec, start/end frames, and audio tracks. Play/listen where supported. State any QA that could not be performed. Never equate successful compilation with successful rendering.

Deliver:
- Final video, if rendering succeeded.
- Editable project and local asset paths.
- Brief/storyboard and an asset manifest sufficient to resume.
- Short account of what was verified and any remaining limitations or service cost.

Default export is MP4/H.264 with yuv420p and AAC audio when audio exists, unless the brief or platform needs another format. Provide captions when requested or needed by the target format. Do not publish or upload assets outside the requested production workflow without authorization.
