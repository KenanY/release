# release

Personal fork of [ForbesLindesay/component-release][] which:

  - Doesn't `npm publish` until after release is tagged
  - GPG-signs tags

## Installation

``` bash
$ npm install -g KenanY/release
```

## Usage

``` bash
$ release 1.0.0
```

## Features

  - Forces versions to be of the form `/^(\d+)\.(\d+)\.(\d+)$/` and won't let you publish with a version number that isn't of that form.
  - Won't let you publish with a version that doesn't match the version in `package.json` and `component.json` if those files are present.
  - Will automatically update the other of those files if you have updated one of them.
  - Will update both for you if you say yes when it asks you.
  - Will never 'update' to an older version
  - Won't let you publish an older version if a newer one exists (and is tagged)
  - won't let you publish if `component.json` or `package.json` exists but is not valid json.

Provided you meet the requirements it will:

  - `git commit -am "Release 0.0.0"`
  - `git tag -s 0.0.0 -m "0.0.0"`
  - `git push --follow-tags`
  - if a package.json is present and not marked private: `npm publish`


   [ForbesLindesay/component-release]: https://github.com/ForbesLindesay/component-release