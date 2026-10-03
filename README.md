# Dark 2026 Minimal Purple

A minimal near-black theme with deep purple accents for Visual Studio Code.

## Colors

- Near-black editor, title bar, panels, terminal, and tabs.
- Purple buttons, badges, selections, focus outlines, and panel accents.
- All 38 custom workbench colors included, including the three Dark 2026-specific overrides.
- Original Dark 2026 TextMate and semantic syntax highlighting included.

The theme is self-contained and does not depend on another theme extension. Eight-digit hex colors preserve the original alpha values; these control color compositing inside VS Code and do not enable desktop-window transparency.

## Install and activate

Install the theme from a packaged `.vsix`: open **Extensions: Install from VSIX...** in the Command Palette and choose the file. You can also run:

```sh
code --install-extension dark-2026-minimal-purple-0.1.0.vsix
```

Open **Preferences: Color Theme** from the Command Palette and select **Dark 2026 Minimal Purple**.

Existing `workbench.colorCustomizations` settings take precedence over themes. To see this theme as shipped, remove the original overrides or test in a temporary profile without them.

## Recommended settings

For the original minimal layout and typography, add the following preferences to your user settings. These are optional: color themes control colors and syntax styles, while font, layout, and chat preferences are separate user settings.

Install [Fira Code](https://github.com/tonsky/FiraCode) separately to use the font and its ligatures; the extension does not distribute the font.

```json
{
  "workbench.startupEditor": "none",
  "workbench.activityBar.location": "top",
  "chat.titleBar.openInAgentsWindow.enabled": false,
  "chat.agent.enabled": false,
  "editor.fontSize": 16,
  "editor.fontFamily": "Fira Code",
  "editor.fontLigatures": true,
  "workbench.statusBar.visible": false,
  "workbench.layoutControl.enabled": false
}
```

This block reproduces all remaining original preferences: no startup editor, activity bar at the top, 16px Fira Code with ligatures, hidden status bar and layout controls, and the original chat preferences. Chat settings may depend on your VS Code version and installed features.

## Development and packaging

```sh
npm ci
npm run package
```

Press F5 in this project to open an Extension Development Host and select the theme. Use a temporary profile without user color overrides to inspect the bundled colors independently.

## Upload to the Marketplace manually

Replace `publisher-id-pending` in the `publisher` field of `package.json` with your existing Marketplace publisher ID. This must match the publisher receiving the upload. Then build the package:

```sh
npm ci
npm run package
```

Open the [Marketplace publisher management page](https://marketplace.visualstudio.com/manage/publishers/), select your publisher, choose **New extension → Visual Studio Code**, and upload `dark-2026-minimal-purple-0.1.0.vsix`. Browser upload does not require a CLI login or a personal access token. For later updates, increment the version in `package.json`, rebuild, and upload the new package to the existing extension.

For CLI publishing instead, authenticate using the [VS Code publishing guide](https://code.visualstudio.com/api/working-with-extensions/publishing-extension) and run `npm run publish:marketplace`.

## Credits and license

Based on Microsoft's built-in Dark 2026 theme, including its Dark Modern, Dark+, and Visual Studio Dark inheritance chain. The original theme definitions and these customizations are distributed under the MIT license; see LICENSE. This is an independent theme extension.
