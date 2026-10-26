# wow-text-en — English text of World of Warcraft (Retail 12.1.5) for fan translators

Plain-text dump of the English strings the game shows: quests, NPC dialogue and subtitles, NPC names, items, spells,
achievements, Adventure Guide, collections and UI. Collected while building **Uwow**, a Ukrainian localization addon
(https://uwow.wearebob.dev). Use it to translate WoW into any language without scraping the game yourself.

**Build:** 12.1.5.70575 (Midnight) · **Rows:** 1,222,194 · **Characters:** 63,325,861

## Files

One TSV per text type (UTF-8, header row, tab-separated). Columns:

| column | meaning |
|---|---|
| `id` | game ID (questID, itemID, spellID, achievementID…) when the text is tied to one; empty for free-text UI/dialogue |
| `field` | which field of that ID: `title`, `description`, `objectives`, `progress`, `completion`, `name`, `desc`, `aura`… |
| `text` | English text; line breaks are written as `\n`, tabs as `\t`, backslash as `\\` |
| `source` | where the string came from: `db2/<Table>` (client DB2 via wago.tools), `trinitycore`, `wowhead`, `corpus`, `game-client` (seen in the live client) |

| file | what | rows |
|---|---|---|
| `data/ach.tsv` | achievements: title, description, reward | 28,181 |
| `data/collections.tsv` | collections, toys, sets | 23,892 |
| `data/currency.tsv` | currencies | 1,896 |
| `data/dialog.tsv` | NPC dialogue, gossip, subtitles, broadcasts | 95,076 |
| `data/faction.tsv` | factions | 1,152 |
| `data/item.tsv` | item names | 209,143 |
| `data/journal.tsv` | Adventure Guide: bosses, abilities, lore | 31,113 |
| `data/mount.tsv` | mounts | 3,216 |
| `data/names.tsv` | NPC and object names | 43,789 |
| `data/pet.tsv` | battle pets | 4,247 |
| `data/quest.tsv` | quests: title, description, objectives, progress, completion | 162,755 |
| `data/questui.tsv` | quest-related UI (campaigns, story lines) | 30,066 |
| `data/sdesc.tsv` | spell and aura descriptions (templates with $-formulas) | 152,406 |
| `data/spell.tsv` | spell names | 365,941 |
| `data/ui.tsv` | interface strings, tooltips, GlobalStrings | 69,321 |

## Tokens inside text

Blizzard placeholders are kept as is: `$n`/`$N` player name, `$c` class, `$r` race, `$g male:female;` gendered word,
`$B`/`$b` line break, `$s1`/`$d`/`$a1`/`$@spellname…` spell formulas, `|cFF……|r` colours, `|H…|h[…]|h` links, `%s`/`%d` format slots.
Some rows use `$p` or `{name}` for the player name — treat them like `$n`. In Adventure Guide text `#` marks a number.

## License and attribution

The English text is © Blizzard Entertainment. World of Warcraft is a trademark of Blizzard Entertainment, Inc.
This repository is a fan resource for non-commercial translation projects, not affiliated with Blizzard.
The repository structure, scripts and this README are MIT. Data sources: client DB2 tables (wago.tools),
TrinityCore (GPL) quest data, Wowhead, strings observed in the game client.

---

## Українською

Англійські тексти World of Warcraft (патч 12.1.5) у простих TSV-файлах для фанатських перекладів будь-якою мовою.
Зібрано під час роботи над українським аддоном Uwow (uwow.wearebob.dev). Колонки: `id` — ID у грі (квест, предмет,
закляття…), `field` — поле, `text` — англійський текст, `source` — звідки взято. Тексти належать Blizzard Entertainment;
репозиторій некомерційний і з Blizzard не пов'язаний.
