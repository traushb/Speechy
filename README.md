# Speechy

A text pad you open directly in your browser.

1. Download `index.html` (on GitHub, download the raw file).
2. Double-click it to open it in your browser.
3. Paste your OpenRouter API key and text, choose a voice, review the estimated cost, and click **Generate speech**.
4. Listen with the audio player or download the result.

Everything is in this one file. No installation, terminal commands, compilation, or local server. You need an internet connection and OpenRouter credits.

Your API key stays in memory and clears on reload. Requests go directly to OpenRouter; your text is sent when you generate speech. The text draft is saved locally when your browser permits it. Local-file storage behavior varies between browsers; draft saving is optional and never includes your key.

Models and voices come from OpenRouter's live speech catalog. `elevenlabs/scribe-v2` transcribes audio; choose a text-to-speech model from the list instead. If the catalog is unavailable, retry it or enter an exact supported model ID.

The estimated cost appears above **Generate speech** and updates with your text and model, using the catalog's current USD rates. Character-priced models use your input character count; Seed Audio estimates duration at 150 words per minute. Fixed per-request fees are included when published. Estimates can differ from actual charges. Token-priced models such as Gemini, missing prices, and unknown custom IDs show **Unavailable** with a link to pricing rather than an incomplete total. A custom ID matching a catalog model uses that model's pricing.

The file can also be uploaded unchanged to any static website host.

Browser checks use this unchanged HTML with mocked audio, including execution from a `null` origin with browser storage unavailable. This cloud browser blocks direct local-file navigation by administrator policy, so the other functional checks use a temporary test server. Live catalog access and local-file CORS are checked without credentials. Real paid audio generation needs your own key.
