# PR Response Doc — CineLog Watchlist Feature

## AI Usage
<!-- Fill in at the end — how you used AI tools during this project -->

## Comment 1 — Rename
**What I did:**
- Updated the `services/watchlist_service.py` method from `save_to_watchlist()` to `add_to_watchlist()`
- Updated the `routes/watchlist.py` methods from `save_to_watchlist()` to `add_to_watchlist()`
**How I verified:**
- Verified by searching for `save_to_watchlist()` in the entire project

## Comment 2 — Deduplication
**What I did:**
- Copied the `existing` variable code from `collection_service` and modified it to work with `WatchlistEntry`
- Added the `AlreadyInCollectionError` import from `services.collection_service` at the top of the file
**How I verified:**
- The porting to `watchlist_service` was pretty straight forward and will be tested once the missing test is created.

## Comment 3 — Missing test
**What I did:**
- Created `test_watchlist.py`
- Copied/pasted the boilerplate from `test_collection.py` and edited what services is being imported
- Copied/pasted the `test_add_to_collection_nonexistent_film_raises` method
- Modified the `test_add_to_collection_nonexistent_film_raises` to `test_add_to_watchlist_nonexistent_film_raises` and edited the function name
**How I verified:**

## Comment 4 — Default visibility
**My position:**
**Reasoning:**
**Tradeoff acknowledged:**

## Comment 5 — Sort order
**My position:**
**Reasoning:**
**Engagement with reviewer's point:**

## Comment 6 — Rebase
**What conflicted:**
**How I resolved it:**
**How I verified no conflict remains:**

## PR Description
<!-- Written at the end — feature overview, design decisions, manual testing steps -->