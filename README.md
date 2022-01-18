# BADI-bot.github.io
BADI Bot's Github Pages

## To Install Hugo:
Follow the instructions on the [Hugo Website](https://gohugo.io/getting-started/installing/). You will need the "Extended" version if an option exists.

## To Clone with Theme:
`git clone --recurse-submodules https://github.com/BADI-bot/BADI-bot.github.io.git`

## Note About `hugo` commands
All `hugo` commands should be run from within the `badi-bot` folder

## To Start Development Server:
+ Without drafts: `hugo server --disableFastRender`
+ With drafts (drafts are not rendered on production): `hugo server --disableFastRender -D`

Follow the link in the terminal output. This is a live server, so making changes to the site will rebuild it in real time.

## To add content:
`hugo new path/to/title.md`

Hugo will try and figure out the content type based on the path. It will generate a markdown file for you to edit. 

For your convenience, here are some sample commands:

+ Posts: `hugo new posts/title.md`
+ Documentation: `hugo new docs/manual-pages/plugin-name.md`
+ Changelog: `hugo new changelog/year/mm-dd.md`
+ Redirect Links: `hugo new links/title.md`

## Notes About Building

+ Do **not** build the site. It's not necessary. Github Actions will build it fresh from the source code.
+ Pull Requests must build against the latest Hugo version to be able to be merged.
+ The default build directory, `badi-bot/public`, is `.gitignore`d