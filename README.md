# Forrest Drury — Portfolio

Single-file static site. Open `index.html` in a browser or serve the folder from any static host (GitHub Pages works as-is). No build step.

## Editing content

All content below the hero lives in the `SITE` object near the top of the `<script>` in `index.html`:

| Array | What it drives |
| --- | --- |
| `text` | Headings, hero intro, button and contact text |
| `about` | About paragraphs |
| `resume` | Resume PDF the download buttons open |
| `portraits` | About slideshow (set `src` to an image path) |
| `gallery` | Photo strip near the bottom |
| `facts` | The quick-facts panel in About |
| `experience` | Timeline roles |
| `projects` | Project cards and their detail dialogs |
| `research` | Research entries (set `link` to a PDF path to show "Read paper") |
| `skills` | Skill groups |
| `contact` | Contact rows |

### Adding a project

Append an object to `SITE.projects`. Cards share a row and expand on hover. Each item in `media` is either a real image or a generated placeholder:

```js
{ src: 'img/gr27-cp.png', caption: 'Cp, front wing midspan' }   // real image (add fit: 'contain' for transparent renders: shown uncropped on the card)
{ kind: 'contour', caption: 'Placeholder' }                      // 'contour' | 'mesh' | 'cad' | 'layup'
```

The first `media` item is the card thumbnail; all of them appear in the detail dialog. `detail.sections` takes any number of `{ heading, items }` blocks (CFD approach, manufacturing, results, and so on).

## Theme

Colours are CSS custom properties at the top of the `<style>` block: light values on `:root`, dark values repeated in the two dark blocks. The hero streamlines and placeholder figures read the same tokens.
