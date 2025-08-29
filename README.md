# ✨ Prompts for espanso

A small collection of handy espanso matches focused on AI prompts and a few starter snippets. Type short triggers like `:sdinterview` anywhere and espanso expands them into full, ready-to-use text.

## 🧠️ What Is espanso?

espanso is a cross‑platform text expander. You define matches in simple YAML: when you type a trigger (e.g., `:readmei`), espanso replaces it with the corresponding text. It works system‑wide, so expansions happen in any app (editors, browsers, terminals, chat, etc.). Learn more at https://espanso.org/

## 📦 Contents

- `prompts.yml`: AI‑oriented prompts you can type anywhere
  - `:readmei`: Generates an image‑prompt template for illustrating a concept.
  - `:sdinterview`: Kicks off a big‑tech–style system design interview.
  - `:binterview`: Starts a behavioral interview and provides a rubric.

## 🛠️ Setup

1) Install espanso

- Download/install from https://espanso.org/install/
- Recommended: espanso v2+ (forms used in `prompts.yml` are v2 features).

2) Put these files in your espanso match folder

- Windows: `%APPDATA%\espanso\match`
- macOS: `~/Library/Application Support/espanso/match`
- Linux: `~/.config/espanso/match`

Copy `prompts.yml` into that `match` directory.

3) Restart espanso

- Run `espanso restart` (or stop/start from your OS tray/menubar).

## 🚀 Usage

- Ensure espanso is running: `espanso status` or start with `espanso start`.
- In any app, type a trigger and press space/enter to expand.

Triggers in this project:

- `:readmei`
  - Prompts for a “concept” via a small form, then outputs an image‑generation prompt: 1:1 composition, transparent background, includes the written concept, with a white outline to work on dark/light backgrounds.
- `:sdinterview`
  - Starts a mock system design interview with structure (requirements, high‑level design, deep dive, wrap‑up) and guidance to keep answers short and probing.
- `:binterview`
  - Runs a behavioral interview simulation and closes with an honest hire/no‑hire style feedback rubric.
- From `base.yml` (optional examples): `:espanso`, `:date`, `:shell`.

Tip: espanso “forms” are supported in v2+. When a match uses a form (like `:readmei`), espanso will show an inline dialog to capture values before expanding.

## ✏️ Customize

- Edit `prompts.yml` to tweak wording or add new triggers.
- Follow YAML indentation strictly; mis‑indentation breaks matches.
- Duplicate an existing block to add a new trigger, then change `trigger:` and `replace:` to fit your needs. Example skeleton:

```yaml
matches:
  - trigger: ":mytrigger"
    replace: |
      Your expanded text here, multi‑line supported.
    # Optional: add vars/forms if needed
```

After changes, run `espanso restart` to reload.

## 🧰 Troubleshooting

- No expansion happens:
  - Check espanso is running: `espanso status`. If not, `espanso start`.
  - Restart after edits: `espanso restart`.
  - Conflicting triggers: ensure other matches/packages don’t use the same `trigger`.
- Windows permissions: if expansions don’t work in some apps, try running espanso with the required permissions.
