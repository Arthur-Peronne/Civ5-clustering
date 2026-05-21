# Community data sources

This directory contains the raw text files used in notebook 07
for qualitative comparison of the K-means clusters against player perception.

All files were collected manually or via scraping in 2024–2025.
Do not re-scrape unless the data needs to be updated — the extraction
pipeline (notebook 07) is designed to be run once and cached.

## Reddit threads (r/civ5)

Collected as JSON via Reddit's public `.json` API endpoint (no authentication required).
Files stored in `data/raw_community/reddit_json/`.

| File | Title | URL | Comments | Post score |
|------|-------|-----|----------|------------|
| `which_ai_leaders_do_you_like_and_hate.json` | Which AI Leaders do you like and hate? | https://www.reddit.com/r/civ5/comments/1sggsu3/which_ai_leaders_do_you_like_and_hate/ | 31 | 30 |
| `im_a_noob_can_you_describe_all_civ_personalities.json` | I'm a noob, can you describe all civ personalities? | https://www.reddit.com/r/civ5/comments/p97slm/im_a_noob_can_you_describe_all_civ_personalities/ | 18 | 79 |
| `who_is_the_most_warmonger_civ_leader.json` | Who is the most warmonger civ leader? | https://www.reddit.com/r/civ5/comments/16q7cpk/who_is_the_most_warmonger_civ_leader/ | 70 | 36 |
| `most_annoying_civ_in_the_game.json` | Most Annoying Civ in the Game? | https://www.reddit.com/r/civ5/comments/n1y76x/most_annoying_civ_in_the_game/ | 64 | 21 |

**Note:** deleted/removed comments and comments under 20 characters are filtered out.
Upvote scores are clipped at a minimum of 1, then log-smoothed and normalized per source
so that each source contributes equally on average (mean weight per message = 1).

## CivFanatics threads

Scraped via BeautifulSoup. Files stored in `data/raw_community/civfanatics_threads/`.
CivFanatics has no upvote system — all posts are assigned a raw upvote of 1.

| File | Title | URL |
|------|-------|-----|
| `civfanatics_favorite_hated.txt` | Favorite / Most Hated AI Personalities | https://forums.civfanatics.com/threads/favorite-most-hated-ai-personalities.513793/ |
| `civfanatics_most_annoying.txt` | Which AI Personality Annoys You the Most? | https://forums.civfanatics.com/threads/which-ai-personality-annoys-you-the-most.452423/ |
| `civfanatics_strongest_ai.txt` | Strongest AI Civ Leaders | https://forums.civfanatics.com/threads/strongest-ai-civ-leaders.558216/ |
