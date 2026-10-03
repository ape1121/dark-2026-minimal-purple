# Development and publishing

## Development and packaging

```sh
npm ci
npm run package
```

Press F5 in this project to open an Extension Development Host and select the theme. Use a temporary profile without user color overrides to inspect the bundled colors independently.

## Upload to the Marketplace manually

The package is configured for the [ape1121 Marketplace publisher](https://marketplace.visualstudio.com/publishers/ape1121). Build the package:

```sh
npm ci
npm run package
```

Open the [Marketplace publisher management page](https://marketplace.visualstudio.com/manage/publishers/), select your publisher, choose **New extension → Visual Studio Code**, and upload `dark-2026-minimal-purple-0.1.8.vsix`. Browser upload does not require a CLI login or a personal access token. For later updates, increment the version in `package.json`, rebuild, and upload the new package to the existing extension.

For CLI publishing instead, authenticate using the [VS Code publishing guide](https://code.visualstudio.com/api/working-with-extensions/publishing-extension) and run `npm run publish:marketplace`.

## Additional personal preferences

These preferences from the original setup are independent of theme colors and can be configured separately:

```json
{
  "chat.titleBar.openInAgentsWindow.enabled": false,
  "chat.agent.enabled": false
}
```
