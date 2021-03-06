## GitHub Writer - Developer Documentation

### Getting the source code

The GitHub Writer source code is available on GitHub: https://github.com/ckeditor/github-writer

To get the source code:

1.  On terminal, move to the folder you want to have the source code in.
2.  Clone the repository:

```plaintext
git clone https://github.com/ckeditor/github-writer.git
cd github-writer
yarn
```

The above will not only clone the repository but also execute `yarn` so all code dependencies are downloaded.

### Building from source

The source code must be built, so it can be used in the browser as an extension:

1.  Be sure code dependencies have been downloaded (`yarn`). Run it as many times as you wish - no harm.
2.  Execute the build script:

```plaintext
yarn run build
```

or

```plaintext
yarn run build-dev
```

The `build-dev` option produces a development friendly build, while `build` make it optimized for production distribution.

You'll find the build files in the newly created `build/` directory. Note that this directory is silently deleted and recreated when executing the build script.

### Loading the built extension in the browser

Having successfully built from source, do the following to load the extension in the browser:

* In Chrome:
  1.  In the menu, select **Window** > **Extensions**. Or navigate to [chrome://extensions/](chrome://extensions/).
  2.  Enable **Developer mode**, at the top right of the page.
  3.  Click the **Load unpacked** button.
  4.  Select the `build/github-writer-chrome` directory from the build directory.

* In Firefox:
  1. Navigate to [about:debugging#/runtime/this-firefox](about:debugging#/runtime/this-firefox).
  2. Click **Load Temporary Add-on...**.
  3. Select the `build/github-writer-firefox/manifest.json` file from the build directory.

It's all set. Now visit [https://github.com/](https://github.com/) and start using GitHub Writer inside issues, pull request and wiki pages.

Note that Chrome will keep the extension enabled, while Firefox will remove it once the browser is closed, and the above steps must be done again.

### Changing the source code

To test changes to the source code, the following steps must always be done:

1.  Re-build by executing `yarn run build-dev`.
2.  Refresh the extension in the browser:
    * In Chrome:
      1.  In the menu, select **Window** > **Extensions**. Or navigate to [chrome://extensions/](chrome://extensions/).
      2.  Click the reload button (⟳).
    * In Firefox:
      1. Navigate to [about:debugging#/runtime/this-firefox](about:debugging#/runtime/this-firefox).
      2. Click **Reload**.

Now just reload pages on GitHub and the updated extension will be executed.

### Additional developer information

*   [Tests](../tests/README.md) (architecture, configuration, run).
*   [Architecture](../src/README.md) (source code, API).

On the web:

*   [CKEditor 5 documentation](https://ckeditor.com/docs/ckeditor5/latest/index.html)
*   [Chrome extension development guide](https://developer.chrome.com/extensions)
