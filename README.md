# Tidy Tasks

A SCSS snippet that redesignes [Obsidian Tasks](https://publish.obsidian.md/tasks/) queries into cards-like blocks, changes metadata (priorities, dates) to colour-coded tags, and generally makes the interface more clean. It's theme-agnostic, so it should work with any theme that uses Obsidian's variables.

> Requires the community plugin **Tasks**. The styles apply to every rendered query

## Install

1. Download `tidy-tasks.css` from the [latest release](../../releases/latest).
2. Drop it into your vault's snippets folder: `<your-vault>/.obsidian/snippets/`.
3. In Obsidian, go to **Settings → Appearance → CSS snippets**, hit the refresh icon,
   and toggle **tidy-tasks** on.

## Build it yourself

The source is SCSS, so you need a Sass compiler. Easiest path is via npm:

```bash
# clone, then from the project root:
npm install        # installs the `sass` dev dependency
npm run build      # compiles src/main.scss -> dist/tidy-tasks.css
npm run watch      # optional: recompile on every save while you tweak
```

Or, if you'd rather not use npm, install [Dart Sass](https://sass-lang.com/install)
standalone and run:

```bash
sass src/main.scss dist/tidy-tasks.css --no-source-map --style=compressed
```

Then copy `dist/tidy-tasks.css` into your snippets folder as described above.

## Project structure

```
src/
  main.scss              # entry/build point, pulls in partials and applies them
  date-tags.scss         # turns dates (scheduled, due, start) into tag pills
  priorities.scss        # colour-codes prioritiy levels
  task-item.scss         # card layout + hover animations
  footer-buttons.scss    # EDIT/POSTPONE text buttons
  minor-adjustments.scss # small optional tweaks (checkbox alignment, etc.)
```

Most of the customisation lives in `priorities.scss` — the `$priorities` map controls
the colour, opacity and label of each priority tag.

## Customise

Want to change priority colours, labels, the corner radius, or the button text without
editing SCSS by hand? Try the [Tidy Tasks Customiser](#) (web), which lets you tweak the
options live and download a ready-to-use CSS file.

## License

MIT
