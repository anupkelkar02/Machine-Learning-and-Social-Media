# Student Hands-On Activities (Browser Tools, No Install)

These two activities run entirely in the browser, need no login and no coding,
and are meant to be done *by the students themselves* on their own laptops/phones
— alongside the instructor-led Python notebooks in `notebooks/`. They're paired
so each browser activity gives a tactile, hands-on feel for the same concept the
matching notebook demonstrates more rigorously.

| Concept | Student hands-on (browser) | Instructor demo (notebook) |
|---|---|---|
| Supervised learning | Activity 1 — Teachable Machine | `1_supervised_sentiment_classification.ipynb` |
| Unsupervised learning | Activity 2 — Voyant Tools | `2_unsupervised_topic_clustering.ipynb` |
| Reinforcement learning | — (watch live, instructor-led) | `3_reinforcement_learning_bandit.ipynb` |

Reinforcement learning has no student-hands-on browser equivalent here — RL needs
an environment that reacts to actions over time, which isn't something a static
click-through tool can offer meaningfully in a few minutes. It's covered as a
live, instructor-run demo instead (see the main README).

---

## Activity 1 — Teachable Machine (Supervised Learning, tactile version)

**Link:** https://teachablemachine.withgoogle.com — no login required.

**What students do:**
1. Click "Get Started" → "Image Project" → "Standard image model."
2. Create two classes, e.g. "Thumbs Up" and "Thumbs Down" (or "Smiling" /
   "Not Smiling" — anything easy to demonstrate with a webcam).
3. For each class, click "Webcam" and hold the button to capture ~20-30 images
   showing that class (e.g., hold up a thumbs up for Class 1, thumbs down for
   Class 2).
4. Click "Train Model." Training happens live in the browser in under a minute.
5. Once trained, show the "Preview" panel live — the model now predicts, in
   real time, which class the webcam is currently seeing.

**Bridge to the concept:** *"You just did exactly what we're about to see the
Python notebook do with tweets — you gave the model labeled examples (this is a
thumbs up, this is a thumbs down), and it learned to predict the label for new,
unseen examples. Same idea, different data."*

**Time:** ~10-12 minutes including setup.

---

## Activity 2 — Voyant Tools (Unsupervised Learning, tactile version)

**Link:** https://voyant-tools.org — no login required.

**File to use:** `data/tweets_for_voyant.txt` (300 real airline tweets, one per
line — same tweets used in the unsupervised notebook, with sentiment labels
stripped out, matching the "no labels" premise).

**What students do:**
1. Open voyant-tools.org.
2. Click "Upload" beneath the search box and select `tweets_for_voyant.txt`
   (students should have this file — share it via LMS/email/USB beforehand,
   since Voyant needs a local file to upload).
3. Voyant immediately shows a multi-panel view:
   - **Cirrus (word cloud)** — largest words are most frequent across all
     tweets. Ask students: what themes jump out (delay, thanks, service,
     baggage)?
   - **Trends** — click any word in the word cloud to see how often it appears
     across the corpus.
   - **Summary** — vocabulary stats, most frequent words, distinctive terms.
4. Ask students to each pick 2-3 words that seem to represent different
   "themes" in the data — without ever being told what the themes are. That's
   the unsupervised idea: the structure comes from the data itself, before any
   human labels are applied.

**Bridge to the concept:** *"You just found themes in this data with no labels
and no coding — that's unsupervised learning by hand. The clustering notebook
does the same thing automatically, and even gives each theme a numeric
boundary instead of relying on your eyes."*

**Time:** ~12-15 minutes.

**Note:** Voyant doesn't do sentiment scoring or clustering — it's a word
frequency/theme-exploration tool, which is exactly the right scope for a
tactile "spot the themes yourself" activity. The rigorous version (actual
clustering) lives in the notebook.
