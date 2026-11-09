# blog-webCLI-themes

The starters of [blog.webcli.app](https://blog.webcli.app). A theme is CSS in a folder of a repository; this repository holds
four, and the built-in `default` makes five. They are chosen to span what a blog's Customization can express (face, width, colour,
list layout) rather than to be five variations of one idea. Each folder is a complete theme with its own `theme.json` and `LICENSE`.

| Folder | Contract | Licence | Face, width, list |
|---|---|---|---|
| (built in) `default` | `blog-webcli-v1` | MIT | system sans, medium, list |
| [`essay`](essay) | `blog-webcli-v1` | MIT | **serif**, narrow (36rem), list; long-form reading |
| [`terminal`](terminal) | `blog-webcli-v1` | MIT | **monospace**, dark by default, list; prompt-style masthead |
| [`cards`](cards) | `blog-webcli-v1` | MIT | sans, the post list as a **grid of cards** |
| [`wide`](wide) | `blog-webcli-v1` | MIT | sans, **wide** (74rem), a two-column dated index and a reading column set in the middle |

Everything here is MIT, written for this app's own markup. **No GPL in the product path.** The 77 wordpress.org themes that used to
live in `wp/` are a regression corpus now, in [blog-webCLI-corpus](https://github.com/tejaswigowda/blog-webCLI-corpus), together
with the retired `paper` starter. A blog pinned to one of them keeps working: a pin is a tag (up to `v1.5.0`), and those tags still
contain the files.

To make a blog look like an existing site, measure it instead of picking a theme (`node cli/measure.mjs <url>` in blog-webCLI): the
result is a `customize` block (colours, one of five font stacks, width, list layout), never a stylesheet.

## Use one

In the editor open **Settings → Choose a theme**, or from the CLI:

```
node cli/blog.js theme pin tejaswigowda/blog-webCLI-themes/essay@v1.0.0
```

The address is `owner/repo/folder@ref`, where `ref` is a release tag or a commit. A branch is
refused. blog.json records `{ repo, ref, sha256 }`, so a theme can never change under a published
blog. A theme works by its address whether or not it is listed anywhere.

The release for the five starters is `v1.6.0`; `v1.0.0`-`v1.5.0` are earlier releases that also contain the corpus themes.

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
