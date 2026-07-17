# AI-Recommendation-Engine
Preference Match Engine

A content-based recommendation system that suggests titles from a catalog based on user-selected interests, built to demonstrate logic building, pattern matching, and recommendation concepts.

Overview

The user selects one or more interest tags (genres). The engine compares those preferences against every title in the catalog, scores each one by similarity, and returns the closest matches ranked from highest to lowest score.

Goal

Create a simple recommendation system based on user preferences.

How It Works


Take user input — the user clicks tag chips (e.g. sci-fi, thriller, romance) to build a preference set. No typing required; selections are tracked as a Set in JavaScript.
Match preferences using logic/similarity — for every title in the catalog, the app computes the Jaccard similarity index between the user's preference set and that title's tag set:


   similarity(A, B) = |A ∩ B| / |A ∪ B|


A ∩ B — tags the user picked and the title has
A ∪ B — all distinct tags across both sets


This produces a score between 0 (no overlap) and 1 (identical tag sets), so it naturally handles partial matches instead of requiring an exact match.
3. Display recommended items — titles with a score above 0 are sorted descending and the top 6 are shown as cards, each with:


Rank and match percentage
A score bar (visual similarity strength)
The title's tags, with overlapping ones highlighted
A short synopsis


A live logic trace panel also prints out each step of the pipeline (input → scan → score → filter → output) so the matching process isn't a black box.

Tech Stack


Plain HTML, CSS, and JavaScript — no frameworks, no build step, no dependencies beyond Google Fonts
Runs entirely in the browser (recommendation-engine.html) — open it directly, nothing to install


Project Structure

recommendation-engine.html   # entire app: markup, styles, and logic in one file
README.md                    # this file

Key Skills Demonstrated


Logic building — Jaccard similarity implemented from scratch (set intersection/union, no external libraries)
Pattern matching — comparing tag sets to surface overlap between user intent and catalog items
Recommendation concepts — content-based filtering, ranking by score, filtering out zero-similarity results


Possible Extensions


Swap the dataset (movies → books, courses, songs) by editing the CATALOG array
Add a second scoring method (e.g. weighted cosine similarity) to compare against Jaccard
Persist user preferences across sessions
Add a "why this was recommended" explanation per card using the overlap array already computed


Running It

Open recommendation-engine.html in any modern browser. No server or build tools required.
