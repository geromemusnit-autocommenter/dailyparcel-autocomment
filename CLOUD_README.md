# The Daily Parcel — auto "Get it here" comment

Every ~5 minutes GitHub Actions checks the Facebook Page for posts that just went live and
comments `Get it here 👉 <that product's amzn.to link>` **on that post's own ID**.

- `autocomment.py` / `fbpage.py`: the commenter (stdlib Python, Graph API)
- `catalog.json`: products + affiliate links (synced from the Mac)
- `autocomment_settings.json`: Preview/Auto + holds (set from the Mac)
- `autocomment_state.json`: results, written by the workflow

Facebook access lives only in the repo secrets `FB_PAGE_ID` / `FB_PAGE_TOKEN`.
A post is commented only when it's matched to exactly one product, its link resolves to the
Associates tag and that product's ASIN, and the Page hasn't already commented a link on it.
