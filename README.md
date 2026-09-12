# ML & Social Media Analytics — 90-Minute Session Kit

Built for a 1.5-hour session on "Machine Learning and Social Media Analytics" for
totally non-technical PGDBM/MBA students. One consistent story — an airline's
social media team — runs through all three ML types and both browser hands-on
activities, using the same real dataset throughout.

## What's in this repo

```
ml-social-media-demo/
├── .devcontainer/devcontainer.json     — auto-installs everything in Codespaces
├── requirements.txt
├── README.md                           — this file
├── STUDENT_BROWSER_ACTIVITIES.md       — Teachable Machine + Voyant activities
├── data/
│   ├── Tweets.csv                      — 300 real, public airline tweets (balanced across
│   │                                       positive/negative/neutral), from the well-known
│   │                                       Twitter US Airline Sentiment dataset
│   ├── tweets_for_voyant.txt           — same tweets, plain text, for the Voyant activity
│   └── synthetic_brand_tweets.csv      — backup dataset (fictional "SkyNova" airline) in
│                                          case of any connectivity issue on the day
└── notebooks/
    ├── 1_supervised_sentiment_classification.ipynb
    ├── 2_unsupervised_topic_clustering.ipynb
    └── 3_reinforcement_learning_bandit.ipynb
```

All three notebooks are plain Python (`pandas`, `scikit-learn`, `matplotlib`,
`numpy`) — no external APIs, no JS, nothing that can silently break during a
live session. Every notebook has been executed end-to-end and verified error-free
before being handed over; outputs are cleared so students/instructor see a clean
run.

## The one-story structure

| # | ML type | Real data used | What students see |
|---|---|---|---|
| 1 | Supervised | Labeled tweets (sentiment given) | A model predicts sentiment on new tweets, live |
| 2 | Unsupervised | Same tweets, labels hidden | A model discovers theme clusters with no answer key |
| 3 | Reinforcement | No dataset — self-generated experience | An algorithm learns which post type to show, purely from simulated trial and reward |

Same airline brand, same social-media framing, three fundamentally different
learning setups. This contrast *is* the teaching point — see each notebook's
final markdown cell for ready-made talking points.

## Deploying on GitHub + Codespaces

1. Push this whole folder to a new GitHub repo, keeping the structure intact.
2. On the repo page: **Code → Codespaces → Create codespace on main**.
3. The `.devcontainer/devcontainer.json` auto-runs
   `pip install -r requirements.txt` on creation — no manual setup.
4. Open each notebook in order and **Run All**. Notebooks 1 and 2 read from
   `../data/Tweets.csv`, so keep the folder structure as-is.

## Suggested session flow (90 minutes)

1. **Hook (10 min)** — open with the idea that a manager doesn't need to code to
   use ML output, just to know what questions to ask.
2. **Activity 1 — Teachable Machine (10-12 min)** — students train a live
   image classifier on their own laptops. See `STUDENT_BROWSER_ACTIVITIES.md`.
3. **Notebook 1 — Supervised (12-15 min, instructor-led)** — run
   `1_supervised_sentiment_classification.ipynb` live, invite the class to
   suggest tweets for the "try it live" cell.
4. **Activity 2 — Voyant Tools (12-15 min)** — students upload
   `tweets_for_voyant.txt` themselves and spot themes by eye. See
   `STUDENT_BROWSER_ACTIVITIES.md`.
5. **Notebook 2 — Unsupervised (10-12 min, instructor-led)** — run
   `2_unsupervised_topic_clustering.ipynb`, comparing the algorithm's clusters
   to what students spotted manually in Voyant.
6. **Notebook 3 — Reinforcement (10-12 min, instructor-led)** — run
   `3_reinforcement_learning_bandit.ipynb`; this one is instructor-run only
   (no student browser equivalent — see `STUDENT_BROWSER_ACTIVITIES.md` for why).
7. **Wrap-up / manager's checklist (5-8 min)** — tie the three notebooks and two
   activities back to what a manager should ask a data team.

Adjust timings as needed — this adds up to roughly 75-85 minutes, leaving a
buffer for questions and transitions between browser tabs and Codespace.

## Troubleshooting

- Kernel not found in Codespace → `Ctrl+Shift+P` → "Python: Select Interpreter"
  → choose the Codespace's Python, not local.
- `FileNotFoundError` on `../data/Tweets.csv` → make sure you're running the
  notebook from inside the `notebooks/` folder structure as cloned — don't move
  notebooks out of that folder.
- If GitHub/Codespaces access is unavailable on the day, everything in
  `notebooks/` runs identically on a local Jupyter install with
  `pip install -r requirements.txt`; swap `Tweets.csv` for
  `synthetic_brand_tweets.csv` (same column structure) if the real dataset
  needs replacing for any reason.
