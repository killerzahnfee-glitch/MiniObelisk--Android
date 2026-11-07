# Android touch UI source patch (experimental, uncompiled)

Target reported: Stardew Valley Android 1.6.15.3, SMAPI 4.3.2.5, Launcher 1.1.7.

Changes:
- Teleport destination rectangles end before a separate 76-pixel-wide rename touch target.
- Rename click returns immediately, preventing further processing.
- Rename confirmation saves with one press instead of requiring two presses when the text box is selected.
- Tapping the name field selects it and reattaches the keyboard subscriber.
- Enlarged the text field; removed Windows-specific post-build commands.

NOT YET SOLVED/VERIFIED:
- Opening an obelisk with Android Click and Autoattack depends on Android's translation of a tap into `Object.checkForAction`. This source patch does not change that pathway.
- Whether Android's software keyboard opens from Stardew's TextBox cannot be confirmed without running the target Android build.
- No compiled DLL included. Requires build against compatible game/SMAPI assemblies and on-device testing.

Back up saves and original mod before replacing anything. Do not install this source ZIP directly into Mods.

ADDITIONAL EXPERIMENTAL CHANGE (2026-11-07):
- SMAPI Input.ButtonPressed handler for MouseLeft on mini-obelisk tile within two tiles of player.
- Opens the original TeleportMenu and suppresses the click.
- Depends on the Android launcher exposing taps as SMAPI MouseLeft events and accurate GrabTile.
- If taps are not emitted as MouseLeft, an Android-specific input hook is still needed.
- NOT COMPILED OR TESTED. No claim of Android compatibility.
