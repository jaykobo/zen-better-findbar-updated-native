# 🔍 Zen Better Find Bar (Native Update)

A highly optimized, floating, and fully customizable Find Bar for [Zen Browser](https://zen-browser.app/).

![Mod preview showing the Zen Browser with the customized findbar below.](image.png)

This repository is a customized fork of the original [Better Find Bar](https://github.com/RobotoSkunk/ff-better-findbar) by **RobotoSkunk**. It has been specifically modified to work **natively** within Zen Browser's internal theme engine, entirely bypassing the need for third-party mod managers like "Sine".

Additionally, this version includes optimized CSS animations (hardware-accelerated) for a buttery-smooth experience when toggling the find bar.

## ✨ Features

- **Floating Design:** Detaches the find bar from the bottom edge, giving it a modern floating look.

- **Native Zen Integration:** Works directly with Zen Browser's built-in "Zen Mods" settings menu.

- **Hardware-Accelerated Animations:** Uses `will-change` and optimized cubic-bezier transitions to eliminate stuttering.

- **Fully Customizable:** Adjust width, horizontal/vertical position, transparency, colors, and shadows directly via the UI.

- **Clean Interface:** Options to hide specific checkboxes (Match Case, Whole Words, etc.) or status labels.

## 🤝 Credits

This project is built upon the fantastic work of **RobotoSkunk**.

- Original Zen Port: [zen-better-findbar](https://github.com/RobotoSkunk/zen-better-findbar)

_Modifications in this fork include adapting `-moz-pref` variables to work natively with Zen's local JSON registries, applying performance tweaks to CSS transitions, and providing a direct local-install method._

## 🛠️ Installation Guide

Because Zen Browser's mod store typically forces updates from online URLs (overwriting local changes), a standard drag-and-drop installation doesn't fully work for customized local mods.

Follow these steps to manually register this mod locally in your Zen profile.

### Step 1: Locate your Zen Profile

1. Open Zen Browser and type `about:profiles` in the URL bar.

2. Look for the profile that says **"This is the profile in use and it cannot be deleted."** (Usually ends with `.Default (release)`).

3. Next to **Root Directory**, click the **Open Directory** (or Show in Finder/Explorer) button.

4. Close Zen Browser completely.

### Step 2: Download and Place the Files

1. Download this repository as a ZIP file and extract it.

2. In your Zen profile directory, navigate to `chrome/zen-themes/`.
   _(If these folders don't exist, create them)._

3. Create a new folder named exactly: `zen-better-findbar-updated-native`

4. Copy the following files from the extracted ZIP into that new folder:
   - `chrome.css`

   - `preferences.json`

   _(Path should look like: `[...]/chrome/zen-themes/zen-better-findbar-updated-native/chrome.css`)_

### Step 3: Edit the Zen Theme Registry (`zen-themes.json`)

To enable the functionality in Zen for this mod in your local files, you need to edit its registry file.

1. Go back to the **root** of your Zen profile directory (the one you opened in Step 1).

2. Find the file named `zen-themes.json` and open it with a text editor (like VS Code, Notepad, or TextEdit).

3. Add the following block to the JSON file. Ensure you place it correctly within the existing JSON structure (don't forget commas between multiple mods):

   ```
     "zen-better-findbar-updated-native": {
       "id": "zen-better-findbar-updated-native",
       "name": "Better Find Bar",
       "description": "Floating find bar, customized to work natively in Zen Browser.",
       "style": "chrome/zen-themes/zen-better-findbar-updated-native/chrome.css",
       "preferences": "chrome/zen-themes/zen-better-findbar-updated-native/preferences.json",
       "readme": "chrome/zen-themes/zen-better-findbar-updated-native/README.md",
       "author": "RobotoSkunk & jaykobo",
       "version": "1.8.0",
       "enabled": true
     }
   ```

   > **⚠️ Crucial Detail:** Notice how `"style"`, `"preferences"`, and `"readme"` use **local relative paths** instead of `https://...` links. This is the magic that makes the local mod work!

4. Save the `zen-themes.json` file.

### Step 4: Launch and Configure

1. Start Zen Browser.

2. Go to **Settings > Zen Mods** (or Themes).

3. You should now see **Better Find Bar (1.8.0)** listed and enabled.

4. Click the gear icon ⚙️ next to it to customize your colors, transparency, and positions.

5. Press `Ctrl + F` (or `Cmd + F` on Mac) on any webpage to see your new, buttery-smooth find bar!

## 🛠️ Troubleshooting

In case the mod changes doesn't get applied - try to disable and re-enable it.
