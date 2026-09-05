# wordle-cli

A terminal Wordle clone in Python. No dependencies — pure standard library.

## Features
- Colored terminal feedback (green / yellow / grey), same rules as real Wordle,
  including correct handling of duplicate letters.
- On-screen keyboard that tracks which letters you've tried.
- Persistent stats: games played, win %, current/max streak, guess distribution.
- `--daily` mode: everyone who runs it on the same date gets the same word
  (seeded by today's date).
- Shareable emoji result grid, just like the real game's copy-paste square.

## Run it

```bash
python wordle.py            # random word each time
python wordle.py --daily    # today's word (deterministic)
python wordle.py --stats    # just print your stats and exit
```

Requires Python 3.7+. No pip installs needed.

## Files

```
wordle-cli/
├── wordle.py     # game loop, scoring, rendering
├── words.py      # answer list + valid guess list
├── stats.py      # stats persistence (stats.json created on first play)
└── README.md
```

## Extending it
- Add more words to `words.py` — `ANSWERS` is the pool the game picks from,
  `EXTRA_VALID_GUESSES` are accepted guesses that aren't answers themselves.
- Want colorblind mode? Swap the ANSI codes in `wordle.py` for
  orange/blue instead of green/yellow.
- Want a bigger dictionary? Load a wordlist file instead of the hardcoded list.

## Push to GitHub

```bash
cd wordle-cli
git init
git add .
git commit -m "Initial commit: terminal wordle clone"
gh repo create wordle-cli --public --source=. --push
```
(or create the repo on github.com first and `git remote add origin <url>`)
