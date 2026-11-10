# Project Documentation for CyberChef

**Author:** Arunangshu Dasgupta

**Official repository:** [GCHQ CyberChef](https://github.com/gchq/CyberChef)

**Documentation repository:** [cyberchef-Documentations](https://github.com/Arun-D-Algo/cyberchef-Documentations)

## 1. Project Overview

### What does CyberChef do?

CyberChef is an open-source tool developed by GCHQ for working with digital data through a browser. It supports tasks such as encoding and decoding, encryption and decryption, hashing, compression, and parsing different formats.

Its main feature is the **recipe** system. You arrange operations in order, and the input passes through them to produce the output. This makes it possible to combine transformations without writing a separate script.

The interface has four main areas: **Operations, Recipe, Input, and Output**.

[Project introduction](https://github.com/gchq/CyberChef#readme)

### What problem does it solve?

Digital data is not always readable straight away. It might be encoded, compressed, or stored in an unfamiliar format.

CyberChef brings tools for handling these situations into one place. Recipes also make the steps easier to repeat and share.

### Who would typically use it?

CyberChef is useful for security analysts, developers, students, researchers, and puzzle solvers. Possible uses include examining encoded strings, understanding file formats, and working through CTF challenges.

[Official application](https://gchq.github.io/CyberChef/)

## 2. Repository Structure

CyberChef separates its processing code, browser interface, Node.js integration, and tests.

| Location | Purpose |
| --- | --- |
| src/core/ | Core processing code. |
| src/core/operations/ | Individual operations. |
| src/core/lib/ | Shared processing libraries. |
| src/core/config/ | Operation configuration and supporting scripts. |
| src/core/dishTypes/ | Supported operation data types. |
| src/web/ | Browser interface code, styling, and assets. |
| src/node/ | Node.js integration. |
| tests/operations/ | Operation tests. |
| tests/node/ | Node.js API tests. |
| tests/browser/ | Browser functional tests. |
| tests/samples/ | Sample data used in tests. |

This separation makes it easier to locate the code related to a particular change. An operation's processing logic and the appearance of the browser interface belong in different areas.

[Source directory](https://github.com/gchq/CyberChef/tree/master/src)

[Tests directory](https://github.com/gchq/CyberChef/tree/master/tests)

### Important files and documentation

The README introduces the project and explains how to run it. The developer wiki provides more detailed guides.

`package.json` defines dependencies and npm scripts. `Gruntfile.js` organises build tasks, while `webpack.config.js` controls bundling. The repository also includes contribution guidance, a security policy, a changelog, and an Apache 2.0 licence.

Setup and build instructions are available in the README and Getting Started wiki. Commands include `npm start` for development, `npm run build` for production output, and `npm test` for the Node.js and operation tests.

[Getting Started guide](https://github.com/gchq/CyberChef/wiki/Getting-started)

[Project scripts](https://github.com/gchq/CyberChef/blob/master/package.json)

## 3. Technologies Used

CyberChef mainly uses JavaScript, with HTML and CSS for its browser interface.

| Technology | Role |
| --- | --- |
| Node.js | Development tooling and programmatic API. |
| npm | Dependency management and project commands. |
| Grunt | Build-task organisation. |
| Webpack | Bundling code and assets. |
| Babel | JavaScript transformations. |
| PostCSS | CSS processing. |
| Bootstrap and jQuery | Interface functionality. |
| CodeMirror | Text editor components. |
| CryptoJS and node-forge | Cryptographic functionality. |
| Nightwatch | Browser testing. |
| ESLint | JavaScript code checks. |

[Dependencies](https://github.com/gchq/CyberChef/blob/master/package.json)

[Build configuration](https://github.com/gchq/CyberChef/blob/master/webpack.config.js)

CyberChef itself is available as a browser application. Ordinary processing happens locally, although some operations intentionally contact external services.

It also has a Node.js API for programmatic use. Its Dockerfile builds the static application with Node.js and serves the output through Nginx.

[Browser application](https://gchq.github.io/CyberChef/)

[Node.js API](https://github.com/gchq/CyberChef/wiki/Node-API)

[Dockerfile](https://github.com/gchq/CyberChef/blob/master/Dockerfile)

## 4. Contribution Workflow

### Issues and pull requests

Issues are used to discuss bugs and feature requests. Pull requests propose changes for review.

The PR template asks contributors to explain the change, link related issues, and provide test coverage. It also requires disclosure of AI tools used while creating the code.

[Issues](https://github.com/gchq/CyberChef/issues)

[PR template](https://github.com/gchq/CyberChef/blob/master/.github/pull_request_template.md)

### Recent example: PR #2925

Dependabot opened PR #2925 to update 13 dependencies in `package.json` and `package-lock.json`.

Examples include `node-forge` from 1.4.1 to 1.4.2, `moment-timezone` from 0.6.4 to 0.6.6, and `@codemirror/view` from 6.43.13 to 6.43.15.

It was **merged on 4 November 2026**, with its status verified on **10 November 2026**.

My takeaway is that dependency maintenance is an important part of open-source work. These changes keep the project's dependency definitions current, although their individual effects need to be checked against the libraries' release notes.

[PR #2925](https://github.com/gchq/CyberChef/pull/2925)

[Changed files](https://github.com/gchq/CyberChef/pull/2925/files)

### Possible future contribution

I would like to investigate clearer decoding errors or add regression tests for a confirmed bug.

To contribute, I would fork the project, create a separate branch, make and test the change, and submit a pull request. I would also complete the required Contributor Licence Agreement.

[Contribution guide](https://github.com/gchq/CyberChef/blob/master/CONTRIBUTING.md)

## 5. Something Interesting I Noticed

### Magic gives a useful starting point

Magic stands out because it looks for possible decoding paths using patterns and candidate transformations. It can explore several layers of encoding.

I see this as a useful lead when the input format is unclear, while still checking the result myself.

[Magic documentation](https://github.com/gchq/CyberChef/wiki/Automatic-detection-of-encoded-data-using-CyberChef-Magic)

### Recipes make the steps visible

The recipe system appeals to me because I can follow the order of transformations.

A possible cybersecurity use case is examining an encoded string from a CTF challenge or suspicious text file. I could decode it, inspect the result, and add another operation if needed. The recipe would preserve that sequence.

I would also like to explore whether more guidance around invalid input could make operations easier for beginners to understand.

These are observations and possible directions for further exploration, rather than contributions I have already completed.
