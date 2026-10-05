# Belmont News

The Belmont News site. Published hourly to https://belmont-news.bolt.host/

The Bolt project moved off `belmont-county-news-b68j.bolt.host`, which now serves only
Bolt's "Website not found" page. The current host is `belmont-news.bolt.host`.

## How publishing works

1. The newsroom lead assigns a story each hour.
2. A reporter researches and drafts it in Notion.
3. The QA editor fact-checks and either approves or returns it. Nothing is published without that approval.
4. The publishing engineer merges the approved draft into `data/stories.json` here and pushes to `main`.
5. GitHub Pages rebuilds the site. The story also goes to the Belmont News backend so it appears on the live blog.

## Local preview

```
python3 -m http.server 8000
```

Open http://localhost:8000.
