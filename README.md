# Instagram Carousel Creator

A reusable AI Agent Skill for turning educational topics into visually designed Instagram carousel posts.

The project is designed as a **skills-only Agent Plugin**. It gives an AI agent reusable instructions for planning, designing, and generating educational Instagram carousels.

It can be used for topics such as:

- Software development
- AI and machine learning
- Databases
- Career education
- Finance education
- Science
- Productivity
- General educational content

The Skill is intentionally generic. It does not hardcode a particular Instagram account, brand, audience, or subject.

---

## Why I Built This

I built this project while learning how **AI Agents, Agent Skills, Plugins, and MCP** fit together.

Instead of repeatedly giving an AI a long prompt describing how I want an Instagram carousel designed, I wanted to create a reusable capability.

Without a Skill, I might repeatedly write prompts such as:

> Create an educational Instagram carousel. Use 4:5 slides, keep the explanation beginner-friendly, use diagrams, don't use too much text, maintain visual consistency, add my branding...

With the Skill installed, those reusable instructions live inside the Skill itself.

The user can simply ask:

> Create an Instagram carousel explaining authentication vs authorization for beginners.

The agent can then use the Skill's instructions to determine how the carousel should be structured and presented.

---

## What It Does

The Skill can:

- Plan an educational carousel from a topic
- Determine an appropriate slide structure
- Generate separate 4:5 carousel slides by default
- Adapt explanations to the intended audience
- Use practical examples
- Create diagrams and visual storytelling
- Apply optional user-provided branding
- Use an optional attached image/carousel as visual style inspiration
- Generate an Instagram caption
- Check generated slides for common visual problems
- Fall back to a complete slide plan when image generation is unavailable

The Skill separates **content instructions** from **visual design guidance**.

`SKILL.md` defines how the agent should approach the task.

`references/visual-design-system.md` defines the default visual direction.

---

## How It Works

A simple way to think about the project is:

```text
User request
     ↓
AI Agent
     ↓
Discovers Instagram Carousel Creator
     ↓
Reads SKILL.md
     ↓
Reads visual-design-system.md when required
     ↓
Plans the carousel
     ↓
Generates the slides
     ↓
Checks the result
     ↓
Generates the caption
```

For example, the user might ask:

```text
Create an Instagram carousel explaining JavaScript closures.

Audience: JavaScript beginners.
```

The user does not need to describe every design rule each time.

Those reusable instructions already exist inside the Skill.

---

## LLM vs Agent vs Skill vs Plugin vs MCP

If you're new to AI agents, this is a useful mental model.

### LLM

The **LLM is the intelligence**.

Examples include models used by ChatGPT, Codex, Claude, and other AI applications.

It can understand instructions, reason about a task, and generate content.

```text
LLM
↓
The intelligence
```

### Agent

An **Agent uses an LLM to accomplish a task**.

Depending on the environment, an agent may also have access to tools, files, Skills, APIs, browsers, or external systems.

```text
Agent
↓
LLM + instructions + available capabilities
```

### Skill

A **Skill is reusable knowledge/instructions for performing a particular type of task**.

In this project:

```text
instagram-carousel-creator
```

teaches the agent how to create educational Instagram carousels.

Instead of repeating the same large prompt every time, the instructions are stored in:

```text
SKILL.md
```

### Plugin

A **Plugin packages capabilities so they can be distributed and made available to an agent**.

This repository packages the Instagram Carousel Creator Skill as a skills-only plugin.

The root:

```text
plugin.json
```

contains metadata describing the plugin.

### MCP

**MCP (Model Context Protocol)** is useful when an agent needs to communicate with external tools or data sources exposed through MCP servers.

For example, an agent might need access to:

```text
AI Agent
   │
   ├── GitHub
   ├── Jira
   ├── database
   ├── internal API
   └── another external system
```

This project currently **does not require an MCP server**.

The Instagram Carousel Creator is primarily an instruction/resource-based capability, so a skills-only plugin is sufficient for its current functionality.

---

## Project Structure

```text
instagram-carousel-creator/
│
├── plugin.json
├── README.md
├── LICENSE
├── .gitignore
│
├── skills/
│   └── instagram-carousel-creator/
│       │
│       ├── SKILL.md
│       │
│       └── references/
│           └── visual-design-system.md
│
└── examples/
    ├── basic.md
    ├── branded.md
    └── visual-reference.md
```

### `plugin.json`

Contains metadata about the plugin, including:

- Plugin name
- Version
- Description
- Author
- Repository
- License
- Keywords

It describes **what the package is**.

### `SKILL.md`

This is the main instruction file.

It defines things such as:

- Required and optional inputs
- Instruction priority
- Carousel structure
- Content rules
- Branding behaviour
- Image generation workflow
- Caption generation
- Fallback behaviour
- Quality checks

Think of this as the **instruction manual for the AI agent**.

### `visual-design-system.md`

Contains the default visual guidance.

For example:

- Typography hierarchy
- Visual storytelling
- Diagrams
- Illustrations
- Layout variation
- Colour usage
- Information density
- Readability
- Visual consistency

Keeping this separate makes the Skill easier to maintain.

### `examples/`

Contains example prompts demonstrating different ways to use the Skill.

---

## Inputs

Only the **topic** is required.

Everything else is optional.

For example:

```text
Topic: Authentication vs Authorization
```

Optional information can include:

```text
Audience: Junior frontend developers

Instagram handle: @yourhandle

Brand colours:
- Navy
- Purple
- Cyan

Number of slides: 6
```

You can also attach an image or existing carousel as a visual reference.

---

## Default Behaviour

Unless the user requests otherwise:

- Slides are generated separately
- Aspect ratio is 4:5
- Target size is 1080 × 1350 when supported
- Typical carousel length is 7–10 slides
- Explanations should be concise and educational
- Each slide should have a meaningful visual
- A caption is generated
- Branding is only used when supplied by the user

The user can override these defaults.

For example:

```text
Create only 5 slides.
```

or:

```text
Use a dark theme with orange accents.
```

Explicit user instructions take priority over the default visual preferences where appropriate.

---

# Using the Skill

## Basic Example

```text
Create an Instagram carousel explaining authentication vs authorization.

Audience: developers who are new to web security.
```

No Instagram handle or branding is required.

The Skill should not invent branding when none has been provided.

---

## Branded Example

```text
Create an Instagram carousel explaining React hydration.

Audience: frontend developers learning React internals.

Instagram handle: @codewithparvez

Brand colours:
- Dark navy
- Electric blue
- Purple
```

The Skill can use the supplied branding while following its normal educational and visual rules.

---

## Using a Visual Reference

You can attach an existing image or carousel.

Then ask:

```text
Create an Instagram carousel explaining why MongoDB can feel familiar
to developers coming from JavaScript and Node.js.

Audience: JavaScript developers who are new to databases.

Instagram handle: @codewithparvez

Use the attached carousel as a visual style reference.

Do not copy its content, branding, logos, or exact layouts.
```

The reference image should influence things such as:

- Visual richness
- Typography hierarchy
- Illustration style
- Diagram style
- Colour balance
- Information density
- Composition variety

It should **not** cause the Skill to copy the original creator's content, branding, logos, or exact layouts.

---

# Installation and Testing

This repository is packaged as a **skills-only portable Agent Plugin**.

The plugin metadata is stored in:

```text
plugin.json
```

and the Skill itself is located at:

```text
skills/instagram-carousel-creator/
```

The complete Skill directory should be kept together because `SKILL.md` references additional resources from its `references/` directory.

For current OpenAI installation options, see the official OpenAI Agent Plugins documentation:

https://developers.openai.com/plugins/

---

## Local Codex Testing

During development, the plugin can be tested using a local plugin marketplace.

A local development setup can look like:

```text
instagram-carousel-creator/
│
├── .agents/
│   └── plugins/
│       └── marketplace.json
│
├── plugins/
│   └── instagram-carousel-creator/
│
├── plugin.json
├── skills/
└── ...
```

The `.agents/` and local `plugins/` directories are development/testing infrastructure and do not need to be part of the distributed source package.

### Install the Plugin

After the local marketplace has been configured, install the plugin in Codex:

```bash
codex plugin add instagram-carousel-creator@personal
```

### Check Installed Plugins

Run:

```bash
codex plugin list
```

Confirm that:

```text
instagram-carousel-creator
```

appears as installed.

### Test the Plugin

Start a **new Codex conversation**.

Then try:

```text
Create a 5-slide educational Instagram carousel explaining
Git branches for beginners.

No branding.
```

A useful test is to **not explicitly tell Codex which Skill to use**.

This helps verify whether the installed capability can be discovered appropriately from the request.

Conceptually:

```text
User asks for Instagram carousel
             ↓
Codex understands the request
             ↓
Relevant Skill is discovered
             ↓
SKILL.md instructions are loaded
             ↓
Visual design guidance is loaded
             ↓
Carousel is created
```

---

## Standalone Skill Usage

If your AI client supports standalone Agent Skills, use the complete:

```text
skills/instagram-carousel-creator/
```

directory.

Do not copy only `SKILL.md`.

Keep:

```text
instagram-carousel-creator/
├── SKILL.md
└── references/
    └── visual-design-system.md
```

together so the Skill can access its visual design reference.

---

# Validation

The Skill should be validated before publishing changes.

If you have OpenAI's `skill-creator` system Skill available in Codex, its validation script can be used.

Example:

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py \
  /path/to/instagram-carousel-creator/skills/instagram-carousel-creator
```

A successful validation should report:

```text
Skill is valid!
```

Validation checks the Skill's structure and metadata, but validation alone does not guarantee good runtime output.

Runtime testing is still important.

---

## Recommended Runtime Tests

At minimum, test these scenarios:

1. **Basic carousel**

   Topic + audience, with no branding.

2. **Branded carousel**

   Topic + audience + Instagram handle/brand colours.

3. **Visual-reference carousel**

   Topic + attached visual reference.

4. **Explicit override**

   Request a specific number of slides or visual preference.

5. **No image generation**

   Verify that the Skill produces a useful slide plan rather than pretending images were generated.

6. **Natural discovery**

   Ask for a carousel without explicitly naming the Skill and check whether the installed capability is selected appropriately.

---

# Image Generation Fallback

Image-generation capabilities depend on the AI environment in which the Skill is running.

If image generation is available, the Skill can use it to create the carousel slides.

If image generation is unavailable, the Skill should **not claim that images were generated**.

Instead, it should return a complete carousel specification containing information such as:

```text
Slide 1
Headline:
Authentication vs Authorization

Teaching goal:
Introduce the difference.

Visual:
Split illustration showing identity verification on one side
and permission checking on the other.

Supporting text:
Authentication = Who are you?
Authorization = What can you access?
```

This specification can then be used with another image-generation or design tool.

---

# Branding

Branding is completely optional.

The Skill can accept:

- Instagram handle
- Brand name
- Brand colours
- Logo
- Visual preferences

For example:

```text
Instagram handle: @codewithparvez

Brand colours:
Dark navy, electric blue and purple
```

If no branding information is provided, the Skill should **not invent a brand or Instagram handle**.

---

# Design Philosophy

The goal is not to produce slides that look like plain presentation slides.

Each slide should ideally have a **dominant visual that helps teach the concept**.

Depending on the topic, this might include:

```text
Process
→ Flow diagram

Comparison
→ Split layout

Code concept
→ Code editor mockup

Architecture
→ System diagram

Summary
→ Visual cheat sheet

Concept relationship
→ Connected diagram

Story/example
→ Illustration
```

A useful test is:

> If most of the body text disappeared, would the visual still help explain the idea?

If the answer is yes, the visual is probably doing useful educational work.

---

# Factual Accuracy

Visual quality should never come at the expense of accuracy.

The Skill should:

- Avoid inventing statistics
- Avoid fake facts
- Avoid misleading technical simplifications
- Explain unfamiliar terminology where appropriate
- Distinguish simplified teaching explanations from exact technical behaviour

For technical topics, explanations should remain beginner-friendly while still being technically defensible.

---

# Contributing

Contributions, ideas, bug reports, and improvements are welcome.

If you want to contribute:

```bash
git clone https://github.com/imparvez/instagram-carousel-creator.git

cd instagram-carousel-creator
```

Create a branch:

```bash
git checkout -b feature/my-improvement
```

Make your changes, validate the Skill, and test the relevant scenarios before opening a pull request.

Useful contribution areas include:

- Better visual design guidance
- Additional examples
- Improved carousel structures
- Better QA checks
- Additional educational use cases
- Documentation improvements

Please avoid introducing hardcoded personal branding into the generic Skill.

---

# License

This project is licensed under the **MIT License**.

See the `LICENSE` file for details.

---

# Author

**Parvez Alam Shaikh**

GitHub:

https://github.com/imparvez

Project:

https://github.com/imparvez/instagram-carousel-creator

---

## Project Status

Current version:

```text
0.1.0
```

The project has been:

```text
Idea
 ↓
Skill implementation
 ↓
Generic reusable design
 ↓
Visual design system
 ↓
Skill validation
 ↓
Runtime testing
 ↓
GitHub publication
 ↓
Plugin packaging
 ↓
Plugin validation
 ↓
Local Codex installation
 ↓
End-to-end testing
```

The next goal is to continue improving the Skill through real-world usage and explore additional reusable Agent Skills and integrations.