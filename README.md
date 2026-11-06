# CadCraft language packs

The published translations for the CadCraft apps, CadCraft Studio and add-ons: 54 languages, one folder per locale.

```
<locale>/<layer>.json     {"@format":"cadcraft-lang-layer","@layer","@locale","s":{key:[translation, hash]}}
```

Layers: `core`, `studio`, `desktop`, `lib.<prefix>` (words shared by several apps), `app.<slug>` and `addon.<id>`.
The hash is the first 12 hex characters of the SHA-256 of the English sentence the entry translates. A build only takes an entry when
its own English hashes the same, so a pack never shows a translation of a sentence the build does not have.

Pack version of this snapshot: 2026.11.01.1353 The apps fetch packs from getcadcraft.com; this repository is the open, reviewable copy.

## Repository relationships

Where these layers are consumed:

- App repos (for example `bimcraft`): `app.<slug>` and `addon.<id>` layers.
- `studio` repo: the hub/UI language layers when composing a suite.
- `desktop-shell` repo: desktop-specific `desktop.*` strings in shell surfaces.
- `addons` repo: add-on authors should keep their own source strings stable so packs can track hash changes.

## Drafts

Most translations are machine-made drafts that native speakers have not reviewed yet, and the newest languages
(lt, lv, bs, mr, te, sq, af, fil, sw, uz, bg, et, sr-Latn, sr-Cyrl) most of all. Corrections are welcome: open an issue or a pull request
that changes the translation in the layer file and leaves the hash alone.

## Languages

| Locale | Language | Keys |
|---|---|---|
| af | Afrikaans | 44,723 |
| ar | العربية | 44,723 |
| bg | Български | 44,723 |
| bn | বাংলা | 44,723 |
| bs | Bosanski | 44,723 |
| ca | Català | 44,723 |
| cs | Čeština | 44,723 |
| da | Dansk | 44,723 |
| de | Deutsch | 44,723 |
| el | Ελληνικά | 44,723 |
| es-ES | Español (España) | 44,723 |
| es-MX | Español (México) | 44,797 |
| et | Eesti | 44,723 |
| fa | فارسی | 44,723 |
| fi | Suomi | 44,723 |
| fil | Filipino | 44,723 |
| fr | Français | 44,723 |
| he | עברית | 44,723 |
| hi | हिन्दी | 44,723 |
| hr | Hrvatski | 44,723 |
| hu | Magyar | 44,723 |
| id | Bahasa Indonesia | 44,723 |
| it | Italiano | 44,723 |
| ja | 日本語 | 44,723 |
| ko | 한국어 | 44,723 |
| lt | Lietuvių | 44,723 |
| lv | Latviešu | 44,723 |
| mr | मराठी | 44,723 |
| ms | Bahasa Melayu | 44,723 |
| my | မြန်မာ | 44,723 |
| nb | Norsk bokmål | 44,723 |
| nl | Nederlands | 44,723 |
| pl | Polski | 44,723 |
| pt-BR | Português (Brasil) | 44,723 |
| pt-PT | Português (Portugal) | 44,723 |
| ro | Română | 44,723 |
| ru | Русский | 44,723 |
| sk | Slovenčina | 44,723 |
| sl | Slovenščina | 44,723 |
| sq | Shqip | 44,723 |
| sr-Cyrl | Српски (ћирилица) | 44,723 |
| sr-Latn | Srpski (latinica) | 44,723 |
| sv | Svenska | 44,723 |
| sw | Kiswahili | 44,723 |
| ta | தமிழ் | 44,723 |
| te | తెలుగు | 44,723 |
| th | ไทย | 44,723 |
| tr | Türkçe | 44,723 |
| uk | Українська | 44,723 |
| ur | اردو | 44,723 |
| uz | Oʻzbekcha | 44,723 |
| vi | Tiếng Việt | 44,723 |
| zh-Hans | 简体中文 | 44,723 |
| zh-Hant | 繁體中文 | 44,723 |

## License

Apache-2.0, see LICENSE.

## Trademarks

Product and company names in these translations (for example the file formats and programs CadCraft can exchange files with) belong to
their owners. They are used only to say which files or programs are meant. CadCraft is not affiliated with, endorsed by or derived
from them and contains none of their code.
