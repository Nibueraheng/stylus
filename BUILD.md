# Build this project

## Preparation

1. Install [Node.js](https://nodejs.org/en/).
2. Go to the project root, run `npm install`. This will install all required dependencies.

Extra preparations are needed if you want to pull locale files from Transifex:

1. Install Transifex client. Follow the instructions on [this page](https://docs.transifex.com/client/installing-the-client).
2. You need a `.transifexrc` file in the root folder. Contact another admin if you need one. It includes the API key to use Transifex's API.

## Generate the ZIP release

Use the following command to generate a ZIP file that can be submitted to AMO or CWS:

```
npm run zip
```

The zip file includes all the files from the repository **except**:

* All dot files (e.g. `.eslintrc` & `.gitignore`).
* `node_modules` folder.
* `tools` folder.
* `package.json` file.
* `package-lock.json` and/or `yarn.lock` file(s).

## Tag a release/Bump the version

Use the `npm version (major | minor | patch)` command to tag a release.

There are some scripts that will run automatically before/after tagging a version. Includes:

1. Test.
2. Update version number in `manifest.json`.
3. Generate the ZIP file.
4. Push the tag to github.

## Translation

We host locale files (`message.json`) on Transifex. All the files exist in our GitHub repository, but if you need to update the locale files, you will need to install the [Transifex client](https://docs.transifex.com/client/installing-the-client)

To pull files from Transifex, run

```
npm run update-locales
```

To push files to Transifex:

```
npm run update-transifex
```
