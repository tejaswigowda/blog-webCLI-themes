# blog-webCLI-themes

The built-in themes for [blog.webcli.app](https://blog.webcli.app). A theme is CSS in a folder of a
repository; this repository holds several. Each folder is a complete theme with its own
`theme.json` and `LICENSE`.

| Folder | Contract | Licence | |
|---|---|---|---|
| [`essay`](essay) | `blog-webcli-v1` | MIT | Long-form reading: serif, narrow measure, generous leading |
| [`terminal`](terminal) | `blog-webcli-v1` | MIT | Monospace, dark by default, prompt-style masthead |
| [`paper`](paper) | `blog-webcli-v1` | MIT | High-contrast and minimal, with a print stylesheet |
| [`cards`](cards) | `blog-webcli-v1` | MIT | The post list as a grid of cards |
| [`wp/*`](wp) | `wordpress-classic` | **GPL-2.0-or-later / GPL-3.0** | 77 of wordpress.org's most popular themes (Twenty Twenty-One, Astra, Kadence, GeneratePress, …), CSS and tokens only: [the list](wp/README.md) |

**Licences are per folder.** Everything is MIT *except* `wp/`, whose themes are GPL (2.0-or-later, 3.0-or-later or 3.0-only), each
folder with its own `LICENSE`. The licences stay in their own folders and neither infects the other. The
`wp/` themes are ingested with `node cli/blog.js theme import <slug>`, directory themes only;
their `theme.json` records the source, the licence, the attribution and what was dropped (PHP
templates, `functions.php`, scripts).

## Use one

In the editor open **Settings → Choose a theme**, or from the CLI:

```
node cli/blog.js theme pin tejaswigowda/blog-webCLI-themes/essay@v1.0.0
```

The address is `owner/repo/folder@ref`, where `ref` is a release tag or a commit. A branch is
refused. blog.json records `{ repo, ref, sha256 }`, so a theme can never change under a published
blog. A theme works by its address whether or not it is listed anywhere.

## Releases

Tags apply to the whole repository (`v1.0.0`), but each folder is pinned by the hash of *its own*
files. Releasing a new version of `essay` therefore does not invalidate a blog pinned to
`terminal@v1.0.0`. **Never move a tag**; cut a new one. A moved tag fails every blog pinned to it
with `pin-mismatch`, which is the point.

## Add a theme

1. A folder with `theme.json`, `style.css` and a `LICENSE`.
2. `class_contract` is `blog-webcli-v1` (this app's markup) or `wordpress-classic`.
3. CSS may reference only files listed under `assets`, or small `data:` images. No `@import`, no
   foreign URLs.
4. Define colours, fonts and width as custom properties (`--fg --bg --link --muted --rule --code
   --font --heading-font --width --size`) so a blog's Customization settings still apply.
5. A pull request adding the folder and an entry in
   [blog-webCLI `themes.json`](https://github.com/tejaswigowda/blog-webCLI/blob/main/themes.json).
