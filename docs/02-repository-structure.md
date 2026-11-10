# Repository Structure

## 1. Official source-code repository

CyberChef's official source github repo is available in the [GCHQ CyberChef repository](https://github.com/gchq/CyberChef).

The code is organised into separate areas for the processing logic, browser interface, Node.js integration, and tests. This makes it easier to find the part of the project related to a particular feature.

## 2. Important directories

This is a simplified view of the repository, showing the main directories and selected files:

```text
CyberChef/
├── .github/
├── src/
│   ├── core/
│   │   ├── config/
│   │   ├── dishTypes/
│   │   ├── errors/
│   │   ├── lib/
│   │   ├── operations/
│   │   └── vendor/
│   ├── node/
│   └── web/
│       ├── html/
│       ├── static/
│       ├── stylesheets/
│       ├── utils/
│       ├── waiters/
│       └── workers/
├── tests/
│   ├── browser/
│   ├── lib/
│   ├── node/
│   ├── operations/
│   └── samples/
├── README.md
├── CONTRIBUTING.md
├── CHANGELOG.md
├── SECURITY.md
├── LICENSE
├── package.json
├── package-lock.json
├── Gruntfile.js
├── webpack.config.js
└── Dockerfile
```

### Main processing code: src/core/

This directory contains processing side of CyberChef.

- **operations/** contains the individual operations.
- **lib/** holds shared code used by multiple operations.
- **config/** contains operation configuration and maintenance scripts.
- **dishTypes/** defines the data types that operations can receive and return.
- **errors/** contains custom error types.
- **vendor/** holds libraries that cannot currently be imported through npm.

The folder also contains files such as `Chef.mjs`, `Recipe.mjs`, `Operation.mjs`, and `Dish.mjs`.

[Explore the core directory](https://github.com/gchq/CyberChef/tree/master/src/core)

### Browser interface: src/web/

This directory contains the web application part. Its subdirectories separate the HTML page structure, stylesheets, static assets, interface utilities, event-handling code, and web workers.

For example, changes to the appearance of the app would involve different files from changes to an operation's processing logic.

[Explore the web directory](https://github.com/gchq/CyberChef/tree/master/src/web)

### Node.js integration: src/node/

This directory provides wrappers and configuration for using CyberChef through Node.js. It allows the tool's functionality to be used programmatically.

[Explore the Node.js directory](https://github.com/gchq/CyberChef/tree/master/src/node)

### Automated tests: tests/

The tests are separated according to what they check:

- **browser/** contains browser functional tests.
- **node/** contains tests for the Node.js API.
- **operations/** contains operation test suites.
- **lib/** contains shared test helpers.
- **samples/** holds sample data used by tests.

[Explore the tests directory](https://github.com/gchq/CyberChef/tree/master/tests)

## 3. Important files

| File or directory | Purpose |
| --- | --- |
| README.md | Introduces the project and explains its features and how to run it. |
| CONTRIBUTING.md | Provides guidance for contributors. |
| CHANGELOG.md | Records changes between releases. |
| SECURITY.md | Explains the project's security policy. |
| LICENSE | Contains the Apache 2.0 licence. |
| package.json | Lists dependencies and defines npm commands. |
| package-lock.json | Records resolved dependency versions for reproducible installation. |
| Gruntfile.js | Defines build and development tasks. |
| webpack.config.js | Configures how application code and assets are bundled. |
| Dockerfile | Defines how to build a container image. |
| .github/ | Contains GitHub workflows, issue templates, and pull-request configuration. |

[View the repository root](https://github.com/gchq/CyberChef)

## 4. Where is the documentation?

The README is the starting point for understanding and running CyberChef. More detailed developer documentation is available in the project's GitHub Wiki, including repository structure, adding operations, and using the Node.js API.

- [Project README](https://github.com/gchq/CyberChef/blob/master/README.md)
- [Developer Wiki](https://github.com/gchq/CyberChef/wiki)
- [Getting started](https://github.com/gchq/CyberChef/wiki/Getting-started)

## 5. Where are the setup and build instructions?

Setup instructions are available in the README and the Getting Started wiki page. The package.json file defines commands such as:

| Command | Purpose |
| --- | --- |
| npm start | Starts the development version. |
| npm run build | Creates the production build. |
| npm test | Runs the Node.js and operation tests. |
| npm run testui | Runs browser tests. |
| npm run lint | Checks the code against linting rules. |

The production output is generated in `build/prod/`. This directory is created during the build rather than being part of the source tree shown above.

[View the npm scripts](https://github.com/gchq/CyberChef/blob/master/package.json)
