# Reddit Conversion API — PowerClick

Server-side Google Tag Manager tag that sends your conversions to Reddit, plus [PowerClick](https://powerclick.io) reporting:
after each send it posts Reddit's response to PowerClick with the click ID and PowerClick's spore ID, so PowerClick
can show delivery health and tie each conversion back to the ad click.

## Based on Stape's template

A modified version of [stape-io/reddit-tag](https://github.com/stape-io/reddit-tag) by [Stape](https://stape.io), licensed under the
Apache License 2.0, at commit `9e8339b` (2026-06-29). Stape's settings and behaviour are unchanged; see Stape's
documentation for the Reddit setup. Changes:

- A **PowerClick** field group: **PowerClick Tenant ID**, **PowerClick Event Name (optional)**.
- After the Reddit request, one POST of the response to `https://ingest.powerclick.io` for your account.
- Permissions: *Sends HTTP requests* adds `https://ingest.powerclick.io/*`; *Reads cookies* adds `__spore_id`.
- Name and brand: PowerClick. Stape's tests are not included (they assert Stape's exact requests).

## Setup

1. Server container: add the template from the Community Template Gallery.
2. Configure the Reddit fields exactly as with Stape's template.
3. In the **PowerClick** group, enter your **PowerClick Tenant ID**.

Problems with Reddit delivery itself: compare with Stape's template. Problems with PowerClick reporting: open an
issue here.
