# wp: WordPress directory themes

Each folder is a theme from [wordpress.org/themes](https://wordpress.org/themes/), ingested with
`node cli/blog.js theme import <slug>` from the directory's **most popular** list (the first 100, as of
2026-11-07). Everything here is **GPL-2.0-or-later, GPL-3.0-or-later or GPL-3.0-only**, each folder with its own
`LICENSE`, and `class_contract` `wordpress-classic`.

Only what a static page can use is taken: `style.css` **and the theme's other front-end stylesheets** (many themes keep
their real styling in `assets/css/`; right-to-left, editor, admin, customizer, plugin-specific and vendor files are left
out, and so is any file that fails the app's CSS rules, each named with its reason under `dropped.css`), their images and
fonts (within a size budget), and design tokens from a block theme's `theme.json`. The stylesheets are the ones the theme
really enqueues, in its order, and `wp-inline.css` holds the CSS its PHP generates (the Customizer's colours and fonts as
custom properties, a block theme's global styles), both read from the theme's demo page on wordpress.org. What is still
missing is the theme's own page structure: the generated pages use the `wordpress-classic` markup, so a theme built on
other class names (Astra's `.ast-container`, say) gets its colours and type but not its layout.
PHP templates, `functions.php` and scripts are **not converted**; each `theme.json` lists them under `dropped`,
with the source, the licence, the attribution and the archive's sha256.

**Not included**: 23 of the first 100 were refused by the importer's own rules, which are not relaxed:
a scripting hook or `@-moz-document`/`@view-transition`/`@-o-keyframes` in the CSS (`extendable`, `twentytwenty`,
`envo-royal`, `royal-elementor-kit`, `yith-wonder`, `twentynineteen`, `shopvane`, `newsmatic`, `total`, `ury`,
`blogus`, `ollie`, `ai-blog-plus`, `bravada`), CSS that refers to files outside the theme (`woostify`, `avantis`),
no declared licence (`oceanwp`, `go`, `spectra-one`, `tutorstarter`), a non-GPL licence (`popularfx`, LGPL), and
split-licensing language (`onepress`, `rife-free`). `twentytwentyone` was already here.

| Folder | Contract | Licence | Theme |
|---|---|---|---|
| [`ashe`](ashe) | `wordpress-classic` | GPL-3.0-or-later | Ashe 2.275 |
| [`astra`](astra) | `wordpress-classic` | GPL-2.0-or-later | Astra 4.14.2 |
| [`atelier-wp`](atelier-wp) | `wordpress-classic` | GPL-3.0-only | Atelier WP 1.0.14 |
| [`basin`](basin) | `wordpress-classic` | GPL-3.0-only | Basin 1.0.6 |
| [`blocksy`](blocksy) | `wordpress-classic` | GPL-2.0-or-later | Blocksy 2.1.61 |
| [`blogchrome`](blogchrome) | `wordpress-classic` | GPL-2.0-or-later | BlogChrome 1.0.5 |
| [`bloghash`](bloghash) | `wordpress-classic` | GPL-2.0-or-later | BlogHash 1.0.31 |
| [`blogsy`](blogsy) | `wordpress-classic` | GPL-2.0-or-later | Blogsy 1.0.21 |
| [`blogsy-news`](blogsy-news) | `wordpress-classic` | GPL-2.0-or-later | Blogsy News 1.0.2 |
| [`bluehost-blueprint`](bluehost-blueprint) | `wordpress-classic` | GPL-2.0-or-later | Bluehost Blueprint 1.0.2 |
| [`botiga`](botiga) | `wordpress-classic` | GPL-2.0-or-later | Botiga 2.5.1 |
| [`colibri-wp`](colibri-wp) | `wordpress-classic` | GPL-3.0-only | Colibri WP 1.0.171 |
| [`colormag`](colormag) | `wordpress-classic` | GPL-3.0-only | ColorMag 4.2.7 |
| [`customify`](customify) | `wordpress-classic` | GPL-2.0-or-later | Customify 0.4.27 |
| [`customizr`](customizr) | `wordpress-classic` | GPL-2.0-or-later | Customizr 4.4.24 |
| [`denovr-lite`](denovr-lite) | `wordpress-classic` | GPL-3.0-or-later | Denovr Lite 1.0.4 |
| [`elastra`](elastra) | `wordpress-classic` | GPL-2.0-or-later | Elastra 1.0.5 |
| [`envo-one`](envo-one) | `wordpress-classic` | GPL-3.0-or-later | Envo One 1.0.5 |
| [`futurio-storefront`](futurio-storefront) | `wordpress-classic` | GPL-3.0-only | Futurio Storefront 1.0.4 |
| [`generatepress`](generatepress) | `wordpress-classic` | GPL-2.0-or-later | GeneratePress 3.6.1 |
| [`hello-biz`](hello-biz) | `wordpress-classic` | GPL-3.0-or-later | Hello Biz 1.2.2 |
| [`hello-commerce`](hello-commerce) | `wordpress-classic` | GPL-3.0-or-later | Hello Commerce 1.0.3 |
| [`hello-elementor`](hello-elementor) | `wordpress-classic` | GPL-3.0-or-later | Hello Elementor 3.5.2 |
| [`hestia`](hestia) | `wordpress-classic` | GPL-2.0-or-later | Hestia 3.3.9 |
| [`hybridmag`](hybridmag) | `wordpress-classic` | GPL-2.0-or-later | HybridMag 1.1.5 |
| [`inspiro`](inspiro) | `wordpress-classic` | GPL-2.0-or-later | Inspiro 2.3.0 |
| [`kadence`](kadence) | `wordpress-classic` | GPL-3.0-only | Kadence 1.6.0 |
| [`kitchio-lite`](kitchio-lite) | `wordpress-classic` | GPL-3.0-or-later | Kitchio Lite 1.0.3 |
| [`kubio`](kubio) | `wordpress-classic` | GPL-3.0-only | Kubio 1.0.116 |
| [`lightning`](lightning) | `wordpress-classic` | GPL-2.0-or-later | Lightning 15.42.0 |
| [`miles-wp`](miles-wp) | `wordpress-classic` | GPL-3.0-only | Miles WP 1.0.9 |
| [`neve`](neve) | `wordpress-classic` | GPL-2.0-or-later | Neve 4.2.19 |
| [`neve-fse`](neve-fse) | `wordpress-classic` | GPL-2.0-or-later | Neve FSE 1.1.9 |
| [`news-magazine-x`](news-magazine-x) | `wordpress-classic` | GPL-3.0-or-later | News Magazine X 1.2.59 |
| [`newsblogger`](newsblogger) | `wordpress-classic` | GPL-2.0-or-later | NewsBlogger 0.2.6.7 |
| [`newscircuit`](newscircuit) | `wordpress-classic` | GPL-2.0-or-later | NewsCircuit 2.1.18 |
| [`newsgoal`](newsgoal) | `wordpress-classic` | GPL-3.0-or-later | NewsGoal 0.4 |
| [`newsup`](newsup) | `wordpress-classic` | GPL-3.0-or-later | Newsup 5.6.8 |
| [`oceanly-green`](oceanly-green) | `wordpress-classic` | GPL-2.0-or-later | Oceanly Green 1.0.8 |
| [`ona-architecture`](ona-architecture) | `wordpress-classic` | GPL-2.0-or-later | Ona Architecture 1.0.0 |
| [`online-toys-shop`](online-toys-shop) | `wordpress-classic` | GPL-2.0-or-later | Online Toys Shop 1.4.1 |
| [`phlox`](phlox) | `wordpress-classic` | GPL-2.0-or-later | Phlox 2.17.22 |
| [`prespa`](prespa) | `wordpress-classic` | GPL-2.0-or-later | Prespa 1.7.9 |
| [`prespa-wellness`](prespa-wellness) | `wordpress-classic` | GPL-2.0-or-later | Prespa Wellness 1.0.8 |
| [`purple`](purple) | `wordpress-classic` | GPL-2.0-or-later | Purple 1.0.3 |
| [`raft`](raft) | `wordpress-classic` | GPL-2.0-or-later | Raft 1.1.17 |
| [`rubik-news`](rubik-news) | `wordpress-classic` | GPL-2.0-or-later | Rubik News 1.0 |
| [`rufous`](rufous) | `wordpress-classic` | GPL-3.0-only | Rufous 1.0.86 |
| [`savara-lite`](savara-lite) | `wordpress-classic` | GPL-3.0-or-later | Savara Lite 1.0.1 |
| [`silverstorm`](silverstorm) | `wordpress-classic` | GPL-3.0-only | Silverstorm 1.0.38 |
| [`sinatra`](sinatra) | `wordpress-classic` | GPL-2.0-or-later | Sinatra 1.5.0 |
| [`solace`](solace) | `wordpress-classic` | GPL-2.0-or-later | Solace 2.1.26 |
| [`spacious`](spacious) | `wordpress-classic` | GPL-2.0-or-later | Spacious 1.10.0 |
| [`storefront`](storefront) | `wordpress-classic` | GPL-3.0-or-later | Storefront 4.6.2 |
| [`sydney`](sydney) | `wordpress-classic` | GPL-2.0-or-later | Sydney 2.73 |
| [`the-coffee-shop`](the-coffee-shop) | `wordpress-classic` | GPL-2.0-or-later | The Coffee Shop 1.1 |
| [`therapy-coach`](therapy-coach) | `wordpress-classic` | GPL-2.0-or-later | Therapy Coach 1.0.0 |
| [`tourze-lite`](tourze-lite) | `wordpress-classic` | GPL-3.0-or-later | Tourze Lite 1.0.5 |
| [`twentyeleven`](twentyeleven) | `wordpress-classic` | GPL-2.0-or-later | Twenty Eleven 5.2 |
| [`twentyfifteen`](twentyfifteen) | `wordpress-classic` | GPL-2.0-or-later | Twenty Fifteen 4.3 |
| [`twentyfourteen`](twentyfourteen) | `wordpress-classic` | GPL-2.0-or-later | Twenty Fourteen 4.6 |
| [`twentyseventeen`](twentyseventeen) | `wordpress-classic` | GPL-2.0-or-later | Twenty Seventeen 4.2 |
| [`twentysixteen`](twentysixteen) | `wordpress-classic` | GPL-2.0-or-later | Twenty Sixteen 3.9 |
| [`twentyten`](twentyten) | `wordpress-classic` | GPL-2.0-or-later | Twenty Ten 4.7 |
| [`twentythirteen`](twentythirteen) | `wordpress-classic` | GPL-2.0-or-later | Twenty Thirteen 4.7 |
| [`twentytwelve`](twentytwelve) | `wordpress-classic` | GPL-2.0-or-later | Twenty Twelve 4.9 |
| [`twentytwentyfive`](twentytwentyfive) | `wordpress-classic` | GPL-2.0-or-later | Twenty Twenty-Five 1.5 |
| [`twentytwentyfour`](twentytwentyfour) | `wordpress-classic` | GPL-2.0-or-later | Twenty Twenty-Four 1.6 |
| [`twentytwentyone`](twentytwentyone) | `wordpress-classic` | GPL-2.0-or-later | Twenty Twenty-One 2.9 |
| [`twentytwentythree`](twentytwentythree) | `wordpress-classic` | GPL-2.0-or-later | Twenty Twenty-Three 1.7 |
| [`twentytwentytwo`](twentytwentytwo) | `wordpress-classic` | GPL-2.0-or-later | Twenty Twenty-Two 2.2 |
| [`unibiz`](unibiz) | `wordpress-classic` | GPL-3.0-or-later | Unibiz 1.0.9 |
| [`vantage`](vantage) | `wordpress-classic` | GPL-2.0-or-later | Vantage 1.20.33 |
| [`variations`](variations) | `wordpress-classic` | GPL-2.0-or-later | Variations 4.4.1 |
| [`vertice`](vertice) | `wordpress-classic` | GPL-3.0-only | Vertice 1.0.106 |
| [`webrand-lite`](webrand-lite) | `wordpress-classic` | GPL-3.0-or-later | Webrand Lite 1.0.1 |
| [`zakra`](zakra) | `wordpress-classic` | GPL-3.0-or-later | Zakra 4.3.3 |
