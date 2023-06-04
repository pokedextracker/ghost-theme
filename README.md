# PokédexTracker Ghost Theme

[Ghost](https://ghost.org/) Theme for the [PokédexTracker
Blog](https://pokedextracker.com/blog/)

## Development

### First-time Setup

When you clone this repo for the first time, and you intend of making changes,
there are a few things you need to do before you get started (you only have to
do this the very first time):

1. Make sure you are using the correct Node version. If you have
   [`nodenv`](https://github.com/nodenv/nodenv), this means running `nodenv
   install` in the current directory which will use the `.node-version` file.
2. Install dependencies with `yarn`.
3. Get everything setup correctly by running `yarn setup`.
4. Run `yarn start` to start Ghost, navigate to
   [`http://localhost:2368/ghost/`](http://localhost:2368/ghost/), and setup
   your blog (e.g. create an account, name your blog, etc).
5. Go to
   [`http://localhost:2368/ghost/#/settings/design`](http://localhost:2368/ghost/#/settings/design),
   scroll to the bottom, and activate the `pokedextracker` theme.

### Running

To test the theme as you make changes, just run `yarn start` to start the Ghost
in development mode. This will allow you to make changes and refresh to see
them. Some caveats to keep in mind as you're developing:

- Ghost caches styles pretty aggressively from what I can tell, so if you aren't
  seeing your style changes, you'll need to do a hard refresh
  (<kbd>Shift</kbd>+<kbd>Cmd</kbd>+<kbd>R</kbd> on Chrome on Mac).
- Ghost only watches files that existed at startup, so if you add a new file or
  directory, you'll have to restart the server.

## Deployment

This theme is meant to be deployed as a bundled zip file. Before creating the
bundle, you should cut a new version first. Then, after the tag has been
created, you can run the bundle script to create the zip file which can then be
uploaded directly to any Ghost blog.

```bash
yarn
yarn release:patch # or release:minor or release:major
yarn bundle
```
