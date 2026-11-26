# Connect — クリスチャン交流会 (joinconnect.jp)

Static one-page website hosted on Netlify. Every merge to `main` deploys automatically.
The main editor is Masa (Masayuki Ohno), who writes in Japanese or English and is
not a developer. Reply in the language he writes in, keep explanations short and
non-technical, and show him what changed in plain words.

The site is entirely in Japanese and is meant to be found on Google, so keep the
`<title>`, `meta description`, headings and text natural Japanese.

## Where things live

- `index.html` — the whole site: content, styles and code.
- Upcoming meetups are the elements with `data-ev` (city, `.ev-date`, `.ev-time`,
  `.ev-theme`). The sign-up form's 「参加する回」 dropdown is built from them
  automatically, so adding or editing a meetup there is enough.
- `robots.txt`, `sitemap.xml` — for search engines. If you add a new page, add it
  to `sitemap.xml`.

## Forms (Netlify Forms)

Three forms post to Netlify, which emails each submission to the address set in
the Netlify dashboard:

| form | Netlify form name | purpose |
|---|---|---|
| `#f` | `connect-signup` | 参加申込 |
| `#f2` | `connect-question` | ご質問 / ファシリテーター応募 (`kind` = `question` or `facilitator`) |
| `#fv` | `connect-feedback` | 感想・ご意見 |

Each form has `data-netlify="true"`, a hidden `form-name` input and a hidden
`bot-field` honeypot. Field names are the `name` attributes. Keep those when
editing forms. A form added later needs the same three things to work.

If sending fails, the page falls back to opening an email to `CONNECT_ORG`
(`info@twomiles.net`).

## Rules

- Work on a branch and open a pull request; Netlify posts a preview link on the PR.
  Masa checks the preview and merges. Don't push straight to `main`.
- This site no longer runs inside Claude: don't add `window.claude` / `claude.use`
  code or Claude artifact links. Links: this site https://joinconnect.jp,
  Paddleout (運営) https://paddleout.life.
- The meetup is for Christians and warmly welcomes non-Christians; no preaching or
  recruiting. Keep that tone in anything you draft.
