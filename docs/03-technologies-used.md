# Technologies Used

## 1. Main programming languages

CyberChef mainly uses **JavaScript** for its processing and application behaviour.

The browser interface uses **HTML** for page structure and **CSS** for styling. The web application's entry point connects the interface with the operation configuration.

[Browser application source](https://github.com/gchq/CyberChef/blob/master/src/web/index.js)

## 2. Frameworks and libraries

CyberChef combines several libraries to support its interface and data-processing operations. Some examples listed in its dependencies are:

| Technology | Role |
| --- | --- |
| Bootstrap and Bootstrap Material Design | Interface components and styling. |
| jQuery | Working with page elements and browser events. |
| CodeMirror | Text editor components. |
| CryptoJS and node-forge | Cryptographic functionality. |
| OpenPGP.js | OpenPGP functionality. |
| Moment Timezone | Working with dates and time zones. |
| Tesseract.js | Recognising text in images through OCR. |

These are selected examples rather than the complete dependency list.

## 3. Runtime and package management

**Node.js** is used for development tooling and the programmatic API. The API lets developers call most CyberChef operations from JavaScript code and run saved recipes.

This means CyberChef can be used through both its visual browser interface and a Node.js program.

[Node.js API documentation](https://github.com/gchq/CyberChef/wiki/Node-API)

**npm** manages dependencies and provides commands such as `npm start`, `npm run build`, and `npm test`.

[Project scripts](https://github.com/gchq/CyberChef/blob/master/package.json)

## 4. Build tools

CyberChef uses **Grunt** to organise development and production tasks. These include generating configuration, running lint checks, and preparing the application for distribution.

**Webpack** bundles application code and assets. Its configuration also uses **Babel** for JavaScript transformations and **PostCSS** for CSS processing.

These tools work together to turn the source files and dependencies into the browser application.

- [Grunt configuration](https://github.com/gchq/CyberChef/blob/master/Gruntfile.js)
- [Webpack configuration](https://github.com/gchq/CyberChef/blob/master/webpack.config.js)

## 5. Testing and code quality

CyberChef uses **Nightwatch** for browser testing and **ESLint** to check JavaScript code against the project's rules. Its npm test command runs the Node.js and operation test suites.

[Testing tools and commands](https://github.com/gchq/CyberChef/blob/master/package.json)

## 6. Browser-based application

CyberChef itself is available as a browser-based application:

[Open the official CyberChef application](https://gchq.github.io/CyberChef/)

Users can build recipes and process data through the interface without installing the development tools. A standalone copy can also be downloaded for local use.

Most processing happens inside the browser, although operations that explicitly contact external services need network access.

[Official application and download information](https://gchq.github.io/CyberChef/)

## 7. Container support

The repository includes a **Dockerfile** for containerised deployment. It uses Node.js to build the application, then copies the generated static files into an **Nginx** image for serving.

This separates the tools needed to build CyberChef from the web server used to serve the finished application.

[Official Dockerfile](https://github.com/gchq/CyberChef/blob/master/Dockerfile)
