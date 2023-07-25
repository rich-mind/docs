
# Aztec Network Documentation

Documentation for the Aztec Network, built with docusaurus

You can view the latest successful build here: https://docs.aztec.network

## Files

- `.gitignore` - This specifies which files Git should ignore when committing and pushing to remote repositories.
- `docusaurus.config.js` - This is the configuration file for Docusaurus. You can manage the links in the header and footer, and site metadata here. A more in-depth introduction to this configuration file is available on the [Docusaurus website](https://docusaurus.io/docs/configuration) and full documentation for the API is [here](https://docusaurus.io/docs/docusaurus.config.js).
- `package.json` - This specifies the dependencies for the website and the commands that you can run with yarn.
- `sidebars.js` - This specifies the sidebars for your documentation. The full documentation for this file is available on the [Docusaurus website](https://docusaurus.io/docs/sidebar).
- `yarn.lock` - This specifies the full dependencies for the website including the dependencies of the dependencies listed in `package.json`. Do not edit this file directly. Edit `package.json` instead, then run `yarn` as described above.

The .md files in the `docs/` directory are the docs. See the [Docusaurus website](https://docusaurus.io/docs/docs-introduction) for the full documentation on how to create docs and to manage the metadata.

## Contributing

We welcome contributions from the community. Please review our [contribution guidelines](CONTRIBUTING.md) for more information.

## Docusaurus

This website is built using [Docusaurus 2](https://docusaurus.io/), a modern static website generator.

### Installation

```
$ yarn
```

### Development

#### Locally

To build; serve to `localhost:3000`; and watch for changes:

```
$ yarn start:dev:local
```

#### Remotely (on mainframe)

To build; serve to `localhost:3000`; and watch for changes:

```
$ yarn start:dev
```

This command preprocesses `#include_code` macros, then builds the html, then starts a local development server and opens up a browser window (at `localhost:3000`, by default).
Most changes are reflected live without having to restart the server.

### Build

```
$ yarn build
```

This command generates static content into the `build` directory and can be served using any static contents hosting service.


## #include_code macro

You can embed code snippets into a `.md`/`.mdx` file from code which lives elsewhere in the repo.
- In your markdown file:
    - `#include_code identifier path/from/repo/root/to/file.ts language`
    - E.g. `#include_code hello path/from/repo/root/to/file.ts typescript`
- In the corresponding code delineate the code snippet with comments:
    - ```typescript
      some code
      some code
      // docs:start:hello
      more code
      more code
      // this-will-error <-- you can use docusaurus highlighting comments.
      this code will be highlighted red
      more code
      // highlight-next-line
      this line will be highlighted
      more code
      // highlight-start
      this line will be highlighted
      this line will be highlighted
      // highlight-end
      more code
      // docs:end:hello
      more code
      ```
- Ironically, we can't show you a rendering of this, because this README.md file doesn't support the `#include_code` macro!
