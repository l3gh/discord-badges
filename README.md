# Discord badge helper

A small script for submitting game activity to Discord. One 50-game run at 2.5 hours per game was followed by a badge increase on the original account. Results can take around a day and are not guaranteed.

## Before you start

- Use a desktop browser signed in to Discord. This was tested in a browser session; Discord updates may break it.
- Check that **Use data to personalize my Discord experience** is enabled in Discord's Data & Privacy settings, and note your current badge totals.
- The script reads your Discord session token in memory and sends activity claims to Discord. Never share your token or paste code you do not trust. This unofficial method may violate Discord's rules and put your account at risk.

## Run it

1. Open Discord in your browser and sign in.
2. Open `badge-helper.js` in a text editor and copy the entire file.
3. Open the browser developer tools (usually **F12** or **Ctrl+Shift+J**) and select **Console**. Paste the script and press Enter. Wait for the message saying games loaded.
4. Start the run by entering:

   ```js
   window.__multiGamePresence.claim()
   ```

5. Keep the tab open until the console says the run finished. Then stop the helper with:

   ```js
   window.__multiGamePresence.stop()
   ```

The run submits 50 games at 2.5 hours each, in batches. A successful request means Discord accepted the submission, not that the badge was credited. Check your badge totals later; the original result took roughly a day. Do not repeatedly rerun it while waiting.

The helper stores its generated machine identifier and submitted game IDs in this browser's local storage to avoid repeating games. It changes the displayed game activity while running and restores it when stopped. A reload also stops it. It does not ask you to enter or share a token.

## Troubleshooting

- **Paste is blocked:** Follow your browser's console instructions only if you have reviewed and trust the script.
- **Game list or Discord modules unavailable:** Reload Discord and try again. Discord may have changed its client.
- **A batch fails:** The script stops; do not assume the failed batch was credited. Check the console and wait before deciding whether to retry.
- **No badge change:** Discord may take time to process activity, ignore the claims, or change the feature. A successful submission is not proof of credit.

Based on [discord-game-badge-presence](https://github.com/everyoneexe/discord-game-badge-presence). Adapted by l3gh.
