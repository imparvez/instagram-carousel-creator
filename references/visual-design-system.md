# Visual Design System

Create visually rich, professionally designed educational Instagram infographics. Avoid defaulting to plain PowerPoint-style slides, documentation pages, or repetitive text-and-card layouts.

These are default visual rules. Explicit user instructions, supplied branding, and user-provided visual references take precedence over default aesthetic choices.

## Visual Direction

Prefer visual storytelling over text-heavy layouts.

Use an appropriate combination of:

- Bold editorial typography
- Meaningful illustrations
- Diagrams and connected flows
- Icons that support comprehension
- Soft gradients where appropriate
- Rounded elements where appropriate
- Subtle shadows and depth
- Browser, terminal, code-editor, device, or interface mockups when relevant
- Arrows, connectors, labels, and annotations that clarify relationships

Maintain a coherent visual language across the carousel while varying the composition according to the concept being taught.

Do not add illustrations merely as decoration. Visual elements should help explain, compare, organize, or reinforce the lesson.

## Dominant Visual

Each teaching slide should normally have one dominant visual concept.

Examples:

- Cover → hero illustration or strong visual metaphor
- Process → connected flow or sequence
- Comparison → split layout or visual comparison
- Code → code-editor mockup paired with result or explanation
- Architecture → connected system diagram
- Mistake → warning/correction visual
- Before/after → transformation layout
- Cheat sheet → compact structured visual grid

Before generating a slide, ask:

> If most of the body text disappeared, would the visual still help the reader understand the idea?

If not, improve the visual concept before generation.

## Slide Composition

Use clear hierarchy:

1. Headline
2. Short supporting explanation when needed
3. Dominant visual
4. Supporting points or labels
5. Optional supplied branding
6. Slide number

Use generous but purposeful spacing. Avoid large empty areas that do not contribute to hierarchy or comprehension.

Vary composition across the carousel. Do not repeat the same heading-plus-two-cards template on every slide.

Possible compositions include:

- Hero illustration
- Diagram-led layout
- Split-screen comparison
- Code-to-output transformation
- Process flow
- Layered system diagram
- Before/after layout
- Warning and correction layout
- Structured cheat-sheet grid

## Colour

When the user does not provide brand colours or a visual reference, use a modern educational palette with strong contrast.

Suitable defaults include:

- Dark navy or charcoal for primary text and high-impact backgrounds
- Electric blue, violet, mint, or cyan as selective accents
- Light neutral backgrounds for educational slides
- Occasional dark or gradient slides for emphasis

Do not force these colours when the user supplies a different palette or when a visual reference clearly establishes another direction.

Use accent colours intentionally to highlight relationships, states, keywords, or sequence—not merely to add decoration.

## Typography

Use large, readable headings with strong hierarchy.

Keep body text concise and readable on a phone screen.

Use emphasis selectively for important words or short phrases.

Avoid:

- Tiny text
- Long paragraphs
- Excessive font-size variation
- Too many competing type styles
- Text placed too close to image edges

Keep important text within safe margins.

## Depth and Polish

Use depth only when it improves structure or polish.

Appropriate techniques include:

- Subtle shadows
- Soft borders
- Rounded panels
- Layered cards
- Background shapes
- Gentle gradients

Avoid excessive effects that reduce readability.

## User-Provided Visual References

The user may attach an image or existing carousel as a visual style reference.

When a visual reference is provided, study characteristics such as:

- Overall visual richness
- Typography hierarchy
- Illustration and icon style
- Diagram density
- Colour balance
- Information density
- Use of whitespace
- Composition variety
- Depth and polish
- Relationship between text and visuals

Use these characteristics as inspiration for the new carousel.

Do not copy the reference's:

- Text
- Branding
- Logos
- Topic
- Characters or distinctive proprietary elements
- Exact composition
- Exact layouts

The reference controls visual direction only. The new carousel's content, examples, factual claims, and teaching structure must come from the user's requested topic and the Skill workflow.

If the visual reference conflicts with explicit user branding or instructions, follow the user's explicit instructions.

If no visual reference is provided, use the default visual direction in this file.

## Consistency vs Variety

The carousel should feel like one coherent set without making every slide look identical.

Keep consistent:

- Typography family/style
- General illustration language
- Spacing philosophy
- Border/shadow treatment
- Supplied branding treatment
- Slide numbering treatment
- Overall level of polish

Allow variation in:

- Layout
- Background treatment
- Diagram type
- Illustration placement
- Accent colour usage
- Content composition

## Visual Quality Check

Before generating each image, identify:

- Teaching goal
- Headline
- Dominant visual
- Layout type
- Important labels or supporting points
- Accent colour or colour role

After generation, inspect the image when possible and check:

- The dominant visual helps teach the concept
- Text remains readable at mobile size
- Text is not clipped or malformed
- Visual hierarchy is clear
- Important content stays inside safe margins
- Supplied branding is accurate and subtle
- Slide numbering is correct
- The slide belongs visually to the same carousel
- The slide is not unnecessarily text-heavy
- Decorative elements do not distract from the lesson

The final images must follow the output format defined by `SKILL.md` or explicitly requested by the user. Do not independently override the requested format, aspect ratio, or separate-image/combined-output choice.
