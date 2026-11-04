# Contributing to the CadCraft language packs

Thank you for helping CadCraft speak your language. Most translations here are machine-made drafts that no native speaker has
reviewed yet, so a careful read by someone who uses the language every day is the most useful contribution there is.

You do not need to know how CadCraft works inside. If a word on screen reads wrong, awkward or too literal, you can fix it.

## Ways to help

- **Fix a translation:** a wrong word, a stiff phrase, a missing accent, the wrong tone (formal or informal).
- **Review a whole area:** pick a locale and a layer (for example `de/core.json`) and read it through.
- **Report a problem** without fixing it: open an issue naming the locale, the key and what is wrong.
- **Ask for a new language:** open an issue. Say which language and variant, and whether you could review it.

The newest languages (lt, lv, bs, mr, te, sq, af, fil, sw, uz, bg, et, sr-Latn, sr-Cyrl) are the least reviewed.

## How the files work

```
<locale>/<layer>.json
{"@format":"cadcraft-lang-layer","@layer":"core","@locale":"de","s":{ "some.key": ["translation", "dc4f7280fa96"] }}
```

- One folder per locale (`de`, `pt-BR`, `zh-Hans` ...), one file per layer: `core`, `studio`, `desktop`, `lib.<prefix>`,
  `app.<slug>` and `addon.<id>`.
- Every entry is `key: [translation, hash]`.
- The **hash** is the first 12 hex characters of the SHA-256 of the English sentence the entry translates. CadCraft only
  uses an entry when its own English text hashes the same, so a translation is never shown against a sentence it was not
  written for.

### The one rule: change the translation, leave the hash alone

Edit the first item of the pair and nothing else:

```diff
-"catalog.cadcraft.role": ["2D-Zeichnen und 3D-Modellierung", "160acef068a5"],
+"catalog.cadcraft.role": ["2D-Zeichnen und 3D-Modellieren", "160acef068a5"],
```

Do not change keys, hashes, `@format`, `@layer` or `@locale`, and do not reorder entries. If you think the English itself
is wrong, open an issue instead; the English text lives in CadCraft, not in this repository.

## Translating well

- **Keep placeholders exactly as written:** `{n}`, `{at}`, `{items}`, `{dir}` and the like must appear in your translation,
  spelled the same. The app fills them in. You may move them to fit your grammar.
- **Keep keyboard shortcuts** such as `Ctrl+Z` as they are, unless the key is named differently on keyboards in your language.
- **Plurals** are stored as an object instead of a string, with forms such as `one` and `other` (and `=0` where the English has it):
  `{"one":"{n} Assistent ist verbunden.","other":"{n} Assistenten sind verbunden."}`. Keep the same shape, keep `{n}`, and
  fill every form your language needs.
- **Be short.** Buttons, menu items and ribbon labels have little room. Prefer the shorter natural wording.
- **Be consistent.** Use the same word for the same thing across files. Search the locale folder for how a term (layer,
  block, snap, viewport ...) is already translated before choosing a new word, and follow the established one unless it is wrong.
- **Pick one register** (formal or informal "you") for the whole locale and keep it. Check the existing text first.
- **Proper names stay.** CadCraft, ModelCraft, BimCraft, PartCraft and the other app names, file formats (DWG, DXF, IFC, STEP,
  STL) and the names of other programs are not translated.
- **Regional variants** have their own folders (`es-ES` / `es-MX`, `pt-BR` / `pt-PT`, `zh-Hans` / `zh-Hant`, `sr-Latn` / `sr-Cyrl`).
  Change the variant you know; do not copy text from one to the other without checking it reads right.
- Keep the file **valid JSON in UTF-8** with no byte-order mark, and keep each entry on its own line, as it is now.

## Making a change

1. Fork this repository and create a branch, for example `de-fix-core-menus`.
2. Edit the translations in one or more layer files of your locale.
3. Check that the file is still valid JSON, for example `python3 -m json.tool de/core.json > /dev/null`.
4. Open a pull request. Keep it to **one locale** so a reviewer of that language can read it, and say in the description:
   - the locale and which files or area you reviewed,
   - whether you are a native speaker or use the language professionally,
   - anything you were unsure about.

Small pull requests are welcome and easier to review. For a large review, split it by layer.

Please do not open pull requests that add machine-translated text without telling us it is machine-translated.

## What happens next

This repository is the open, reviewable copy of the packs. CadCraft builds them from its own language files, and the
snapshot here is refreshed from that build, so a change merged here is carried into those source files by the maintainers
and then ships in a later pack version. Until then the apps keep showing the earlier text, and a refresh of this repository
can overwrite a merged change that has not been carried over yet. If a change you made is missing after a refresh, open an
issue and we will put it back.

We may ask questions or ask a second speaker of the language to look. We will say so in the pull request.

## Licence and trademarks

By contributing you agree that your contribution is licensed under the Apache License 2.0 (see [LICENSE](LICENSE)), the same
licence as the rest of the repository. Do not submit text copied from other products or from translations you do not have the
right to reuse.

Product and company names in these files belong to their owners and are used only to say which files or programs are meant.
Do not add wording that suggests CadCraft contains another product's code or is affiliated with it.

## Be kind

Language preferences differ between regions and people. Discuss differences politely, give a reason for a change, and assume
good intent. Harassment and abuse are not tolerated.
