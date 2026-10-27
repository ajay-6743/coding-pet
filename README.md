# Byte, your coding pet

A tiny habit tracker for developers. Byte is a pet that grows as you build good coding habits: deep focus, tests, small commits, tidy code and learning new things. Nothing is ever taken away. Miss a few days and Byte just gets sleepy.

The whole app is a single HTML file with no build step and no dependencies.

## Getting started

1. Open `Byte__your_coding_pet.html` in any modern browser.
2. Give your pet a name (up to 16 characters) by editing the name field.
3. Do a check-in, then press **Feed Byte**.

To try it without waiting a week, open **Playground** and press **Add a sample week**.

## Daily check-in

Each day you can log:

- **Deep focus block:** None, 25 min, 50 min or 90+ min.
- **What you did:** wrote or ran tests, kept commits small, tidied up code, learned something new.

Press **Feed Byte** to save the day, or **Take a rest day** to keep your streak alive without logging work. Checking in again on the same day replaces that day's entry.

## How Byte grows

**XP**

| Source | XP |
| --- | --- |
| Check-in | 10, plus up to 7 bonus XP as your streak grows |
| Rest day | 6 (streak is kept) |
| Focus: 25 / 50 / 90+ min | 6 / 12 / 20 |
| Tests | 8 |
| Small commits | 8 |
| Tidying up | 6 |
| Learning something new | 12 |

**Stages**

| Stage | XP needed |
| --- | --- |
| Egg | 0 |
| Hatchling | 25 |
| Critter | 100 |
| Coder | 250 |
| Legend | 500 |

**Habit levels.** Four habits each level up at 20, 60 and 120 points and change how Byte looks:

| Habit | What counts | Look |
| --- | --- | --- |
| 🔥 Spark | Showing up, streaks | Flames and a glow |
| 🎯 Focus | Deep focus time | Glasses and a halo |
| 🛠️ Craft | Tests, small commits, tidy-ups | Side plates and a badge |
| 📚 Curiosity | Learning new things | Antennae and orbiting dots |

With the Classic skin, Byte's color follows your strongest habit.

## Coins and skins

You earn 1 coin for every 2 XP, plus 15 bonus coins each time your streak reaches a multiple of 7 days. Spend coins on skins, which only change how Byte looks.

| Skin | Price |
| --- | --- |
| Classic | Free |
| Sunset | 30 |
| Ocean | 30 |
| Moss | 45 |
| Terminal | 60 |
| Cosmic | 80 |
| Golden | 120 |

Skins you own can be re-equipped for free at any time.

## Import from git

Byte can read your commit history and fill in past days for you. In a repo, run:

```sh
git log --since="90 days ago" --author="$(git config user.email)" --pretty=format:"%ad|%s" --date=short
```

Paste the output into the **Import from git** box and press **Import commits**. Each line has the form `YYYY-MM-DD|commit message`.

Byte guesses your habits from the commits on each day:

- **Tests:** a message mentions `test` or `spec`.
- **Small commits:** three or more commits that day.
- **Tidying up:** a message mentions `refactor`, `clean`, `tidy` or `rename`.
- **Learning:** a message mentions `learn`, `try`, `experiment`, `spike`, `prototype` or `explor…`.

Import only adds to your existing days; it never lowers anything. Only dates, commit counts and the flags above are stored. Commit messages are not saved.

## Your data

- Progress is saved automatically in your browser's `localStorage` under the key `bytepet`. It stays on your device and is not sent anywhere.
- If the page is opened somewhere that provides Claude's per-user storage, Byte saves there too and loads from it first.
- Clearing site data or using another browser or device starts you fresh.
- **Start over** (in Playground) erases all check-ins, skins and coins. It asks you to click twice to confirm.

## Notes

- Dates use your local time zone.
- The page follows your system light or dark mode and respects reduced-motion settings.
- The Bricolage Grotesque font loads from Google Fonts; without a connection it falls back to the system font.
