# anvil

Static reference pages for a nursing simulation program. Each page is plain HTML
with no build step, no dependencies, and no server. GitHub Pages serves them.

Published at `https://m-k-stahl.github.io/anvil/`

## Why it exists

Equipment for a portable simulation setup travels in labeled boxes. An NFC sticker
on each box holds a URL. Tapping it with any phone opens that box's packing
checklist, with no app to install and nothing to log into. The tag is a shortcut,
not a database.

## Layout

```
anvil/
  index.html        landing page, links to everything below
  kit/index.html    box packing checklists
```

Each folder is its own page. Adding a section means adding a folder with an
`index.html` in it. Nothing else has to be configured.

## Box checklists

`kit/` serves every box from one file. The box number comes off the URL:

| Sticker on | URL written to the tag |
| --- | --- |
| Box 1 | `https://m-k-stahl.github.io/anvil/kit/?b=1` |
| Box 2 | `https://m-k-stahl.github.io/anvil/kit/?b=2` |

Open `kit/index.html` and find the block marked `ADD OR EDIT BOXES HERE`. Copy an
existing box, change the number, the name, and the items. Commit. The change is
live in about thirty seconds.

Two conventions worth keeping:

- List multiples as separate lines. `Ethernet cable 1 of 3` forces a count that
  `three ethernet cables` does not.
- Put each power supply directly under the thing it powers.

Checkboxes reset every time the page opens. Nothing is stored, so every tap is a
fresh check rather than a record of an old one.

## Writing the tags

NTAG213 stickers, written with the NFC Tools app as a URL record. Both iPhone and
Android open the page straight from the lock screen. Cover each sticker with clear
tape, since the boxes get dragged and stacked.

## Editing

Small fixes: edit the file on github.com, including from a phone.
Anything larger: clone the repo and work in an editor.

The page is loaded from the internet, so the phone needs a signal to open it. Keep
a printed copy of the checklists with the kit.

## Scope

Simulation training materials only. Not clinical guidance, not a patient record,
and not for clinical use. No network configuration, credentials, or patient
information belongs in this repo, which is public.

## License

MIT. See `LICENSE`.
