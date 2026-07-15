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
The default value should be `False` instead of `True`.
**Reasoning:**
The reasoning is that you usually have an opt-in instead of opt-out feature. If someone wants the film to be public they should be required to click a checkbox instead of have it default set to `True`.
**Tradeoff acknowledged:**
If we keep it with the default being `True` it will potentially make it have more viralability to it, but at the potential expense of privacy.

## Comment 5 — Sort order
**My position:**
It would be beneficial to allow the user to select the sort order. Whether that is on the users client or on the server.
**Reasoning:**
If we allow the user to select their sort preference they may be able to find more films that interest them based on their selection.
**Engagement with reviewer's point:**
The maintainer states that they would prefer the 'date added' as the preferred method instead of 'alphabetical'. The above position of allowing the users to select their preference would allow the maintainers choice along with what the user may want to do as well. 

## Comment 6 — Rebase
**What conflicted:**
**How I resolved it:**
**How I verified no conflict remains:**

## PR Description
<!-- Written at the end — feature overview, design decisions, manual testing steps -->