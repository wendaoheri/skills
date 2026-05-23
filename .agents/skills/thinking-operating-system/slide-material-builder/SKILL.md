---
name: slide-material-builder
description: >
  Turn a structured training outline into a polished HTML presentation.
  This skill applies best‑practice slide design (minimal text, clear
  hierarchy, white space and cohesive colours) using the WebSlides
  framework so that your output looks like a professional PPT but can be
  delivered as an accessible HTML file.
version: 1.0.0
tags:
  - design
  - slides
  - html
requires:
  - training-storyline-builder
  - pyramid-structure
---

# Slide Material Builder

## Overview

Slides should support the speaker, not serve as a script. Effective
presentations follow the “less is more” principle: use key words rather
than full sentences, limit bullet points and word counts (e.g. the 6×6
rule – no more than six lines of text and six words per line), and let
white space direct attention【54861850057867†L64-L173】. Good slide design
also limits fonts to two or three, selects colours deliberately,
creates visual hierarchy through contrast and alignment, and uses
icons or images to aid memory【54861850057867†L64-L173】. The WebSlides
framework provides a simple HTML structure where each `<section>`
inside `<article id="webslides">` represents an individual slide and
navigation is built in【23240728403102†L26-L47】. This skill helps you
translate your training storyline into such an HTML slide deck.

## When to Use

Use this skill:

- After outlining your training content and narrative using
  `training-storyline-builder` and organising your argument with
  `pyramid-structure`.
- When you need a lightweight presentation that can be viewed in a
  browser, embedded in a web page or converted to other formats.
- To design slides for remote workshops, webinars or asynchronous
  courses where learners may access materials on different devices.

## Process

Follow these steps to create a slide deck in HTML:

### Step 1 – Plan your deck

1. Extract the slide outline from your storyline: each major point
   becomes a slide or set of slides. Ensure each slide communicates a
   single key message.
2. Apply the 6×6 rule: limit each slide to a maximum of six bullets or
   lines and six words per line【54861850057867†L64-L173】. Break complex
   ideas across multiple slides.
3. Decide on a cohesive colour palette and two to three fonts. Ensure
   sufficient contrast for readability. Choose icons or images to
   illustrate concepts where appropriate【54861850057867†L64-L173】.

### Step 2 – Create the HTML structure

1. Start with a basic HTML document. In the `<head>`, include the
   WebSlides stylesheet and optionally a minimal custom CSS file for
   colours and fonts. For example:

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
     <meta charset="UTF-8">
     <title>Your Deck Title</title>
     <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/webslides/1.6.0/css/webslides.min.css" />
     <!-- Optional: link to your own CSS file for colours/fonts -->
   </head>
   <body>
     <article id="webslides">
       <!-- Slides go here -->
     </article>
   </body>
   </html>
   ```

2. For each slide, add a `<section>` inside `<article id="webslides">`【23240728403102†L26-L47】. Wrap content in `<div class="wrap">` to enable
   consistent margins. Use semantic tags (`<h1>`, `<h2>`, `<p>`, `<ul>`,
   `<img>`). Keep HTML clean; avoid inline styling except minor
   alignment classes provided by WebSlides (e.g. `class="aligncenter"`).

3. Include alt text for images for accessibility. If icons are used,
   embed them as SVGs or link to a local assets folder. Do not link to
   remote images that may break offline.

### Step 3 – Populate slide content

1. Summarise each key message in a heading. Use short phrases instead
   of sentences and avoid paragraphs when bullets suffice【54861850057867†L64-L173】.
2. Use lists sparingly; prefer one idea per slide. If you need to
   compare options or show sequences, consider using two adjacent
   columns or a numbered list.
3. Insert relevant images, diagrams or icons to illustrate concepts.
   Leave adequate white space around elements to avoid clutter【54861850057867†L64-L173】.
4. Maintain alignment: centre elements horizontally and vertically,
   align text left where appropriate. Use headings at least 30–50 % larger
   than body text for clear hierarchy【54861850057867†L64-L173】.

### Step 4 – Refine and test

1. Preview your HTML file in a browser. Use keyboard or scroll to
   navigate slides. Check that text is readable at typical viewing
   distances, that colours render well and that images scale
   appropriately.
2. Adjust spacing, contrast and content distribution as needed.
3. If you intend to convert to PDF or another format, test conversion
   using appropriate tools (e.g. browser print to PDF or external
   conversion tools). For PPTX verification only, you may use the
   `pptx_to_img` script after exporting to PPTX via external tools.

### Step 5 – Deliver your deck

1. Save the HTML file with a descriptive name (e.g. `ai-office-training.html`).
2. Package any local assets (images, CSS) alongside the HTML file.
3. Provide an outline of the slides in your report so others can
   understand the structure without reading the entire HTML.
4. Optionally include instructions on how to host or open the HTML
   offline (e.g. “open in any modern browser; no server needed”).

## Output Format

When using this skill, produce two artefacts:

1. **Slide Outline:** A numbered list where each entry includes
   - **Title**: the slide heading.
   - **Key Points**: a bulleted list of the main ideas on that slide.
   - **Visuals:** notes on any images or icons to include.
   - **Notes (optional):** presenter reminders or transitions.

2. **HTML File:** A fully formed `.html` file following the WebSlides
   structure described above. Save it to the path requested by the user
   (e.g. `/home/oai/share/ai-office-training.html`). Ensure it contains
   all slides and any necessary assets in sub‑directories (e.g. `assets/`).
   Do not embed the entire HTML in the output text; instead, mention
   that the file has been created and provide its location.

## Example

**Slide Outline:**

1. **Title:** AI Office Training – Introduction  
   **Key Points:** purpose of the workshop; agenda overview.  
   **Visuals:** company logo; simple graphic of a person overwhelmed by
   paperwork.
2. **Title:** Why AI for Productivity?  
   **Key Points:** information overload; AI accelerates research;
   efficiency statistics.  
   **Visuals:** bar chart or infographic illustrating time saved.
3. **Title:** Your Role in the Journey  
   **Key Points:** learner is the hero; call to adventure; overview of
   stages.  
   **Visuals:** icon of a hero or path; timeline showing training phases.

**HTML File:** The skill will generate a file (e.g.
`ai-office-training.html`) containing:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>AI Office Training</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/webslides/1.6.0/css/webslides.min.css">
</head>
<body>
  <article id="webslides">
    <section>
      <div class="wrap">
        <h1>AI Office Training</h1>
        <p>Unlock productivity through AI tools.</p>
      </div>
    </section>
    <section>
      <div class="wrap">
        <h2>Why AI for Productivity?</h2>
        <ul>
          <li>Reduce information overload</li>
          <li>Accelerate research and writing</li>
          <li>Focus on high‑value tasks</li>
        </ul>
      </div>
    </section>
    <!-- More slides here -->
  </article>
</body>
</html>
```

## Notes

- Do not cram paragraphs of text onto slides; let the narrative be told
  by the presenter or accompanying notes. Slides are signposts for
  ideas【54861850057867†L64-L173】.
- When creating your own CSS, follow basic design principles: high
  contrast between text and background, generous line spacing, and
  consistent margins. Avoid too many colours or animations.
- Test your HTML offline to ensure it functions without internet
  connectivity. If linking external CSS, provide instructions to
  download or host the file locally.