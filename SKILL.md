---
name: instagram-carousel-creator
description: Create educational Instagram carousel posts from a topic. Use when asked to turn a topic into separate 4:5 carousel images with visual storytelling, clear explanations, practical examples, optional user-provided branding, an optional visual style reference, and an Instagram caption.
---

# Instagram Carousel Creator

## Purpose

Create educational Instagram carousel posts that explain a topic clearly through visual storytelling.

The skill can be used for software development, technology, AI, business, career, productivity, education, finance, science, and other educational subjects.

Adapt terminology, examples, complexity, and visual language to the topic and intended audience. Use clear language that is accessible to readers whose first language may not be English.

## User Inputs

The user may provide:

- Topic
- Instagram handle
- Target audience
- Preferred number of slides
- Brand name, logo, colours, or typography preferences
- Preferred visual style
- An attached image or carousel as a visual style reference
- A requested output format or aspect ratio

Only the topic is required. Do not require optional inputs before proceeding.

Never invent an Instagram handle, brand name, logo, or other user-specific branding.

## Instruction Priority

When instructions conflict, use this priority:

1. Explicit instructions in the user's current request
2. User-provided branding and visual references
3. Rules in this `SKILL.md`
4. Default rules in `references/visual-design-system.md`

User preferences may override default visual choices such as colours, typography style, visual density, and layout style.

Do not override factual accuracy or applicable safety requirements.

## Main Goal

Turn a topic into an educational Instagram carousel that:

- Is easy to understand
- Is easy to save and revisit
- Uses practical examples when appropriate
- Uses visual storytelling rather than decoration alone
- Avoids unnecessary jargon
- Explains necessary jargon
- Looks professionally designed
- Remains factually accurate
- Encourages learning rather than clickbait

## Output Format

Default output:

- Each carousel slide is a separate individual image
- Portrait 4:5 aspect ratio
- Target size: 1080 × 1350 pixels when supported by the available image-generation tool
- Mobile-readable typography
- Consistent slide numbering

Do not create a contact sheet, collage, grid, or one image containing all slides by default.

These are defaults. If the user explicitly requests another format, aspect ratio, combined preview, collage, contact sheet, or other output, follow the user's request.

## Branding

Use only branding explicitly provided by the user.

Branding may include:

- Instagram handle
- Brand name
- Logo
- Brand colours
- Typography preferences
- Other brand assets

If the user provides an Instagram handle, use it subtly where appropriate. Suitable placements include a lower corner, bottom centre, or final slide.

If the user provides other branding without an Instagram handle, use the supplied branding without inventing a handle.

If no branding is provided, generate an unbranded carousel.

Branding must not compete with the educational content.

## Visual Design

Before planning or generating carousel images, read:

[Visual Design System](references/visual-design-system.md)

Use it for visual composition, typography, colour, illustration, diagrams, layouts, visual-reference handling, and visual quality checks.

User-provided visual preferences and reference images take precedence over the default aesthetic choices in the reference file.

## Carousel Structure

Normally create 7–10 slides. Use fewer slides when the topic can be explained properly with fewer. Do not add unnecessary slides merely to reach a particular number.

If the user specifies a slide count, follow it when reasonable.

A typical educational flow is:

1. Hook / cover
2. Context or problem
3. Core concept
4. Supporting concepts or process
5. Practical example
6. Comparison, mistake, or deeper explanation when useful
7. Takeaway or cheat sheet
8. Final CTA when appropriate

Adapt the structure to the topic rather than forcing every carousel into the same sequence.

## Cover Slide

The first slide should make the topic immediately understandable and encourage the reader to continue.

Use a short, clear headline and an optional supporting line.

Examples:

- `Authentication vs Authorization`
- `What Actually Happens When React Hydrates?`
- `Why I Chose MongoDB as My First Database`

Avoid misleading hooks and clickbait.

## Teaching Slides

Each slide should primarily teach one idea.

Normally use:

- 1 clear heading
- 1 short explanation
- 1 dominant visual
- 2–4 supporting points when needed
- A practical example when useful

Avoid long paragraphs and excessive bullet lists.

If a slide becomes too dense, split the concept across slides.

## Practical Examples

Use practical examples when they make the concept easier to understand.

Examples must match the subject and target audience. Do not force software-development examples onto unrelated subjects.

For software topics, examples may involve applications, APIs, databases, authentication, testing, performance, deployment, or code.

For other subjects, choose examples naturally relevant to that subject.

## Comparisons

When concepts are commonly confused, consider a visual comparison.

Possible formats include:

- Side-by-side comparison
- Before vs after
- This vs that
- Compact table
- Connected diagram

Choose the format that explains the distinction most clearly.

## Cheat Sheet / Takeaway

When appropriate, make the final or second-last teaching slide a concise reference, summary, or cheat sheet.

It should summarize useful information from the carousel rather than introduce substantial new information.

Do not force a cheat sheet when the topic does not benefit from one.

## Final Slide and CTA

Finish with an appropriate key takeaway, summary, cheat sheet, or simple call to action.

Possible CTAs include:

- `Save this for later.`
- `Which topic should I explain next?`
- `Follow @handle for more.` when the user supplied that handle

Avoid aggressive engagement bait.

## Writing Style

Use clear, natural language and short sentences.

Explain complex concepts simply without making them incorrect. Adapt vocabulary and depth to the intended audience.

Do not sound like generic AI-generated marketing copy.

## Accuracy

Information must remain factually and technically accurate.

Do not:

- Invent statistics
- Invent technical facts
- Make unsupported claims
- Present assumptions as facts
- Oversimplify a concept until it becomes incorrect

If an important limitation or exception materially affects the explanation, mention it briefly.

When the topic requires current or externally verifiable information, use available research tools when appropriate before generating the final content.

## Jargon

When specialist terminology appears for the first time, explain it if the intended audience may not know it.

Keep definitions short and practical.

## Image Generation Workflow

### Step 1 — Understand

Determine:

- Topic
- Intended audience from the request or context
- User-provided branding
- User-provided visual preferences
- Whether a visual reference is attached
- Requested slide count or output format, if any

Do not invent missing user-specific branding.

### Step 2 — Plan the Carousel

Before generating images, determine for each slide:

- Teaching goal
- Headline
- Essential text
- Practical example when useful
- Dominant visual concept
- Layout type
- Important visual elements or icons
- Accent colour or colour role

Design the content and visual together rather than writing text first and decorating it afterward.

Do not begin image generation until every slide has a clear teaching goal and dominant visual concept.

### Step 3 — Check the Content

Verify that:

- Important concepts are covered
- Concepts are not unnecessarily duplicated
- Terminology is correct
- Claims are supportable
- Slides follow a logical learning order
- Examples match the intended audience
- Text density follows the shared 2–4 supporting-point guideline

### Step 4 — Generate

When image-generation capability is available, generate the carousel images according to the requested or default output format.

By default, generate every slide as its own individual image.

Maintain consistency in typography, design language, margins, related colour palette, supplied branding, and slide numbering while allowing compositions to vary according to the concept.

### Step 5 — Image-Generation Fallback

If image generation is unavailable:

- Do not claim that images were generated
- Provide the complete slide plan instead
- Include the exact proposed text for each slide
- Include the dominant visual and layout direction for each slide
- Clearly state that image generation was unavailable

### Step 6 — Quality Check

After generation, inspect the rendered images when the available tools allow it.

Verify:

- Correct number of slides
- Correct slide order and numbering
- Requested/default aspect ratio is respected
- Target dimensions are used when supported
- Text is readable on mobile
- Text is not clipped or unintentionally obscured
- No important content disappeared during rendering
- Branding matches only what the user supplied
- Spelling is correct
- Visuals explain the intended concept
- Visual style is coherent across the carousel
- No slide is accidentally a multi-slide collage unless requested

If a generated slide clearly fails these checks and regeneration is available, correct it before finishing.

## Caption Generation

Generate an Instagram caption unless the user asks not to.

The caption should:

1. Start with a short hook
2. Explain why the topic matters
3. Briefly summarize what the carousel teaches
4. Include a useful takeaway
5. Include a natural CTA when appropriate
6. Include a small set of relevant hashtags when appropriate

Keep the caption natural and aligned with the intended audience.

If an Instagram handle was supplied, it may be included naturally. Never invent one.

## Default Behaviour

If the user provides only a topic, automatically:

1. Understand the topic and infer a reasonable audience from context
2. Create an appropriate carousel structure
3. Simplify the explanation to the right level
4. Add useful practical examples
5. Plan a dominant visual for every slide
6. Generate individual 4:5 carousel images when image generation is available
7. Maintain visual consistency
8. Generate an Instagram caption
9. Provide the final slide order when useful

The user should not need to separately request separate images, 4:5 format, no collage, examples, visual storytelling, readable explanations, or a caption.

If no branding is provided, generate the carousel without personal branding.

## Example Request

User:

`Create an Instagram carousel about authentication vs authorization. My Instagram handle is @codewithparvez.`

Expected workflow:

1. Determine the audience and learning goal
2. Plan the teaching sequence
3. Explain authentication and authorization accurately
4. Compare them visually
5. Show how they work together
6. Include a practical example
7. Cover a useful mistake or misconception if appropriate
8. Create a takeaway or cheat sheet
9. Plan a distinct dominant visual for every slide
10. Generate each slide as a separate image by default
11. Apply `@codewithparvez` subtly because the user supplied it
12. Generate the caption

## Core Principle

Every educational carousel should help the reader understand:

- What is it?
- Why does it matter?
- How does it work?
- When would I use or encounter it?
- What does it look like in a practical example?

Adapt these questions when they do not naturally fit the subject.

The reader should finish the carousel with a useful understanding of the topic without requiring unnecessary additional explanation.
