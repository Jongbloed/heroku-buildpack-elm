## Heroku Elm 19.0 Buildpack

A simple buildpack that uses [npm's elm package](https://www.npmjs.com/package/elm) for binaries, and executes your 'elm_compile.sh'

### Configuration

Use these buildpacks:

```
    { "url": "heroku/nodejs" },
    { "url": "https://github.com/Jongbloed/heroku-buildpack-elm" }
```

Put your `elm make` command in elm_compile.sh

I disabled trying to cache the elm-stuff and /app/.elm folders, because that doesn't work.
It seem like elm doesn't see the ~/.elm folder, and then reports it as CORRUPT instead of missing.
See alse https://github.com/elm/compiler/issues/1845

So basically this buildpack does nothing except execute ./elm_compile.sh