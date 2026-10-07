# Auto Typer (portable)

This folder runs on Windows without installing Python. The folder you unzip contains **AutoTyper.exe** and this readme. The program files live in `runtime`.

## Start

**Run AutoTyper as Administrator.** Global hotkeys do not work reliably unless the program is elevated. If it is not elevated, it shows an alert and closes.

1. Unzip the folder anywhere. Leave `runtime` next to `AutoTyper.exe`.
2. Right-click **AutoTyper.exe** and choose **Run as administrator**. Do this every time you start it.
3. If the window does not open, right-click `runtime\AutoTyper-console.bat` and choose **Run as administrator** to see the error text.

A tray icon appears. Closing the window leaves the app in the tray when **Close window to tray** is checked.

## Daily use

1. Select text and copy it (**Ctrl+C**).
2. Press **Ctrl+Shift+H** to rewrite it in a more human style (the result replaces the clipboard).
3. Click the field you want to type into.
4. Press **Ctrl+T** to type the clipboard there.

Move the mouse to a **corner of the screen** to stop typing immediately.

| Key | Action |
|-----|--------|
| Ctrl+T (or Ctrl+Alt+T) | Type the clipboard |
| Ctrl+Shift+H (also Ctrl+Alt+H, Ctrl+Alt+J, Ctrl+Alt+Shift+H) | Humanize the clipboard |
| Ctrl+Shift+Q | Quit the standalone listeners (not the tray app) |

## What each tab does

| Tab | Controls |
|-----|----------|
| Typing | Text box, delay range, hotkey wait, typo rate, human-like typing |
| Humanize | Model list, **Refresh all**, API keys |
| Prompt | Prompt text, strength, Stack Overflow style profile, **Build SO data** |
| Hotkeys | Turn the global hotkeys on or off, then **Apply hotkeys** |
| Log | What the hotkeys and actions did |

**Save settings** writes `runtime\settings.json`. **Apply hotkeys** reloads the bindings.

Hotkeys require Administrator. If a key still does nothing, confirm you used **Run as administrator**, try **Ctrl+Alt+H**, check the **Log** tab, and click **Apply hotkeys**.

## Humanize models

- **Local (no key):** install [Ollama](https://ollama.com), run `ollama pull llama3.2`, and leave it running. The app starts Ollama in CPU mode when it can.
- **Cloud:** put a key in the Humanize tab or in `runtime\.env`. See `runtime\.env.example`.

Supported providers: Ollama, OpenAI, Anthropic (Claude), Google Gemini, Groq, OpenRouter, Mistral, Together.

## Notes

- Do not delete the `runtime` folder. It holds the embedded Python, the program, and saved settings.
- Remove API keys from `runtime\settings.json` and `runtime\.env` before you share this folder.
- The window and tray use the mark icon only (no wordmark).
