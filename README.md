# jrib-vscode-md-style

This repository provides the source code for a VS Code extension that styles the markdown preview in VS Code.

## Why?

It is [not possible](https://code.visualstudio.com/Docs/languages/markdown#_using-your-own-css) to configure a global markdown style outside of workspaces.  Instead the [recommended workaround](https://github.com/microsoft/vscode/issues/45260#issuecomment-371438399) is to create a custom extension.

## Screenshots

### Default

![Default](/screenshots/default.png)

### Themed

![Themed](/screenshots/themed.png)

## Building

```
npm install -g vsce
npm run package
```

## Installing

Download the VISX from the [Releases](https://github.com/jrib/jrib-vscode-md-style/releases) page.

Then **Install from VSIX** using the triple dot menu in VS Code's extension panel.

## Customizing

To make your own extension:

1. Clone this repository.
2. Edit `markdown.css`.
3. Update repository information and name in `package.json` if you care.
3. Run `npm run package` to produce a `.vsix` file.
4. **Install from VSIX** using the triple dot menu in VS Code's extension panel.

## Notes

The default markdown style is found at [src/vs/workbench/contrib/markdown/browser/markdownDocumentRenderer.ts](https://github.com/microsoft/vscode/blob/3b57fde7a85d12e4583c492c29f2dcae31434ed1/src/vs/workbench/contrib/markdown/browser/markdownDocumentRenderer.ts#L14-L149).

It's also useful to use "Toggle Developer Tools" in the "Help" menu and inspect the preview to find css classes to style.

Yes, it would be nice to not have to rebuild the extension to modify the theme...