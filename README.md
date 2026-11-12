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

`kit/` serves every box, tote and load-out list from one file. Which one comes
off the URL, `https://m-k-stahl.github.io/anvil/kit/?b=` plus the key:

| Card on | Key | URL written to the tag |
| --- | --- | --- |
| OH day load-out | `oh` | `.../anvil/kit/?b=oh` |
| Quiz Code day load-out | `qc` | `.../anvil/kit/?b=qc` |
| Tote 1 (Anvil Rack, Boxes 1 and 2) | `t1` | `.../anvil/kit/?b=t1` |
| Tote 2 (Print Rack, panels, Boxes 3 and 4) | `t2` | `.../anvil/kit/?b=t2` |
| Tote 3 (clinical supplies) | `t3` | `.../anvil/kit/?b=t3` |
| Grey Tote (liquids) | `grey` | `.../anvil/kit/?b=grey` |
| Box 1 to Box 11 | `1` to `11` | `.../anvil/kit/?b=1` and so on |

The page with no key (`.../anvil/kit/`) lists everything, grouped, with how far
each one has got.

Open `kit/index.html` and find the block marked `ADD OR EDIT BOXES HERE`. Copy an
existing entry, change the key, the name, and the items. Commit. The change is
live in a minute or two.

Item lines:

- `"Wireless mouse"` is a thing to tick.
- `"- Spare battery"` is indented under the line above; `"--"` indents twice.
- `"@1"` means Box 1 is packed inside this one. That line ticks itself when Box 1
  is complete, and tapping it opens Box 1. Box 1's own page then says which tote
  it is packed in. This is how totes hold boxes, and how a load-out list holds
  totes.

Two conventions worth keeping:

- List multiples as separate lines. `Ethernet cable 1 of 3` forces a count that
  `three ethernet cables` does not.
- Put each power supply directly under the thing it powers.

Ticks are saved on the phone, per box, so scanning the next box or reloading the
page does not wipe them. They clear themselves 48 hours after the last tap on that
box. That is long enough to pack the night before, run class and pack up.
"Clear every box" on a load-out list wipes all of them at once: press it when
class ends, before packing up. "Start over" on any other page clears just that
one. The ticks live only on the phone that made them; a second phone sees its own.

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
