# Instagram Carousel Creator Skill

A reusable Agent Skill for turning educational topics into visually designed Instagram carousel posts.

## What it does

The Skill can:

- Plan an educational carousel from a topic
- Generate separate 4:5 carousel slides by default
- Adapt explanations to the intended audience
- Use practical examples
- Apply optional user-provided branding
- Use an optional attached carousel/image as visual style inspiration
- Generate an Instagram caption
- Fall back to a complete slide plan if image generation is unavailable

The Skill is intentionally generic. It does not hardcode an Instagram account, brand, or subject area.

## Structure

```text
instagram-carousel-creator/
├── plugin.json
├── README.md
├── LICENSE
├── .gitignore
├── skills/
│   └── instagram-carousel-creator/
│       ├── SKILL.md
│       └── references/
│           └── visual-design-system.md
└── examples/
    ├── basic.md
    ├── branded.md
    └── visual-reference.md
```

## Installation

This repository is a skills-only portable Agent Plugins package for ChatGPT and Codex. Keep the root `plugin.json` and the complete `skills/` directory together when distributing the plugin. Skills are discovered automatically from `skills/`.

Follow the [OpenAI plugin installation and testing guidance](https://developers.openai.com/plugins/quickstart) for the options available in your product or workspace. This repository is not a published directory listing.

For a standalone Skill installation in a compatible client, use `skills/instagram-carousel-creator/`, including its `references/` directory.

## Example

```text
Create an Instagram carousel explaining React hydration.

Audience: frontend developers who are new to React internals.
Instagram handle: @codewithparvez
```

The Instagram handle is optional. If no branding is supplied, the Skill should not invent any.

## Using a visual reference

Attach an image or existing carousel and prompt:

```text
Create an Instagram carousel explaining why MongoDB can feel familiar
to developers coming from JavaScript and Node.js.

Audience: JavaScript developers who are new to databases.
Instagram handle: @codewithparvez

Use the attached carousel as a visual style reference.
Do not copy its content, branding, or exact layouts.
```

The reference image influences visual direction only. Content and factual claims should be created for the requested topic.

## Defaults

Unless the user requests otherwise:

- Each slide is generated separately
- Aspect ratio is 4:5
- Target size is 1080 × 1350 when supported
- Typical carousel length is 7–10 slides
- A caption is generated
- Branding is used only when supplied by the user

## Validation

If you have OpenAI's `skill-creator` system Skill installed in Codex, you can validate the folder with its `quick_validate.py` script.

For example:

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py \
  /path/to/instagram-carousel-creator/skills/instagram-carousel-creator
```

Then test runtime behaviour with both:

1. A topic with no branding/reference image.
2. The same topic with branding and an attached visual reference.

This helps distinguish default design quality from reference-guided design quality.
