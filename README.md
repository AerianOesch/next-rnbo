# RNBO Webpage Example

This example shows you how to add dynamic audio to a webpage, using the web export feature of RNBO, part of [Max 8](https://cycling74.com/products/max) made by [Cycling '74](https://cycling74.com).

This repository uses [Node](https://nodejs.org/en/) to launch a simple web server to make your webpage available locally. For more on why this is necessary, see [Why a local server?](#why-a-local-server)

## Prerequisites

In order to run this example, you'll need `node`, `npm`, and access to the command line. The `npx` binary ships with `node`, so just download and install that from the [Node.js downloads site](https://nodejs.org/en/download/). The recommended version is their latest `LTS`, which at the time of writing this document is version 16.

If have heard about `node` and `npm` before but would like to know more about the included `npx` Package Runner please refer to the [Node.js Documentation](https://nodejs.dev/learn/the-npx-nodejs-package-runner).

## File structure

The source code of the web application is in the `js/` directory. This directory contains the file `app.js`, which does all the work of loading and connecting your RNBO patch.

Some notable files/directories:

| Location   | Explanation                                               |
| ---------- | --------------------------------------------------------- |
| export/    | The directory into which you should export your RNBO code |
| js/        | Source for the project, edit it however you like          |
| index.html | The web page itself                                       |

### Working with RNBO

Next, open the RNBO patcher you'd like to work with, and navigate to the export sidebar. Find the "Web Export" target.

Export your project, making sure to export into the `export` folder in your repository directory.

From the repository root, run the following command to start the local web server

```sh
npx http-server
```

When asked to install the `http-server` in order to proceed simply agree by using `y`. You will only have to agree on that once.
Once the server started up successfully you may see something like the following in the console:

```sh
Available on:
  http://127.0.0.1:8080
  http://192.168.88.139:8080
Hit CTRL-C to stop the server
```

Open the shown URL, fe. `http://127.0.0.1:8080` in your default browser, if everything went well, you should see and hear your RNBO patch.

### Exporting a new patch

This example looks in the `export` directory for a patch named `patch.export.json`. If you change the name of your export to something other than `patch.export.json`, you'll need to change the JavaScript as well. In `js/app.js`, the line:

```js
const patchExportURL = "export/patch.export.json";
```
