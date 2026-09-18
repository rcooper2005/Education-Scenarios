# Ten Moments — active engagement coaching scenarios

An interactive coaching tool for instructional observation debriefs. Ten classroom
vignettes, each with three possible teacher moves. Every move gets a response,
including the ones that feel right, and each is labelled *more of the same*,
*a real improvement but partial*, or *shifts who's thinking*.

Coach's notes are hidden behind a toggle so the same page works two ways: assign it
to the teacher first, or work through it together with the notes showing.

## Files

- `index.html` — the entire site. No build step, no dependencies, nothing to install.
- `.nojekyll` — tells GitHub Pages to serve the files as-is.

## Publishing

1. Create a new repository.
2. Upload `index.html` and `.nojekyll` to the root.
3. Settings → Pages → Source: *Deploy from a branch* → branch `main`, folder `/ (root)`.
4. The URL appears in a minute or two: `https://USERNAME.github.io/REPO-NAME/`

## Editing the content

All ten scenarios live in the `SCENARIOS` array near the top of the `<script>` block
at the bottom of `index.html`. Each entry is:

```js
{
  t: "Scenario title",
  m: ["First paragraph of the classroom moment.", "Second paragraph."],
  o: [
    { x: "The choice as the teacher sees it",
      v: "same",            // "same" | "partial" | "shift"
      vl: "More of the same",  // the label shown after choosing
      r: ["First paragraph of the response.", "Second paragraph."],
      i: "Optional 'Try this:' line" }
  ],
  c: ["Coach's note paragraph.", "<span class='ask'>The question to ask.</span>"]
}
```

To swap the science examples for another subject, edit the `m` and `r` strings only —
the structure and labels stay the same.

Choices are kept in the visitor's own browser via `localStorage` and are not sent
anywhere. Nothing is collected.
