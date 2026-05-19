# Community data sources

This directory contains the raw text files used in notebook 07
for qualitative comparison of the K-means clusters against player perception.

All files were collected manually or via scraping in 2024–2025.
Do not re-scrape unless the data needs to be updated — the extraction
pipeline (notebook 07) is designed to be run once and cached.

---

## Reddit threads (`reddit_threads/`)

Downloaded manually as `.txt` files from the Civ 5 subreddit (r/civ5).

| File | Thread title | URL | Approx. date |
|------|-------------|-----|--------------|
| `which_ai_leaders_do_you_like_and_hate.txt` | Which AI leaders do you like and hate? | https://www.reddit.com/r/civ5/comments/1sggsu3/which_ai_leaders_do_you_like_and_hate/ | 2024 |
| `im_a_noob_can_you_describe_all_civ_personalities.txt` | I'm a noob, can you describe all civ personalities? | https://www.reddit.com/r/civ5/comments/p97slm/im_a_noob_can_you_describe_all_civ_personalities/ | 2021 |
| `who_is_the_most_warmonger_civ_leader.txt` | Who is the most warmonger civ leader? | https://www.reddit.com/r/civ5/comments/16q7cpk/who_is_the_most_warmonger_civ_leader/ | 2023 |
| `most_annoying_civ_in_the_game.txt` | Most annoying civ in the game? | https://www.reddit.com/r/civ5/comments/n1y76x/most_annoying_civ_in_the_game/ | 2021 |

**Note on Reddit data:** These files were saved as plain text (not via the Reddit API).
Upvote counts per comment are parsed by `extract_upvotes_reddit()` in notebook 07
using a positional regex strategy (upvote count appears just before the next `u/username`).

---

## CivFanatics threads (`civfanatics_threads/`)

Scraped automatically by notebook 07 via `scrape_civfanatics()` (BeautifulSoup).
CivFanatics has no upvote system — all posts are weighted equally (weight = 1.0).

| File | Thread title | URL |
|------|-------------|-----|
| `civfanatics_favorite_hated.txt` | Favorite / most hated AI personalities | https://forums.civfanatics.com/threads/favorite-most-hated-ai-personalities.513793/ |
| `civfanatics_most_annoying.txt` | Which AI personality annoys you the most? | https://forums.civfanatics.com/threads/which-ai-personality-annoys-you-the-most.452423/ |
| `civfanatics_strongest_ai.txt` | Strongest AI civ leaders | https://forums.civfanatics.com/threads/strongest-ai-civ-leaders.558216/ |

---

## Coverage

- Total mentions extracted: 398
- Leaders with community scores: 42 / 43
  (MariaI — Portugal — absent from community threads)
- Leaders flagged low confidence (< 5 mentions): see `community_scores.csv`