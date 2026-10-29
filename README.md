# Caption delay field log

An offline observation tool for a real caption rehearsal. Press **Hear** when a chosen spoken phrase ends; press **See** when its corresponding completed caption appears. Record the same cue consistently, review raw observations, and export CSV or exact JSON.

Open `index.html` in a modern browser. No build, account, installation, network service, microphone or audio recording is required. The interface follows the established PewTranslate caption display rehearsal tool; this project adds a distinct paired timing workflow rather than text-layout inspection.

## What the numbers mean

The interval uses `performance.now()`. It is **observer-estimated phrase-end to completed-caption delay**, contaminated by human reaction time and matching errors. It is not measured ASR/network latency, a translation-quality score, an accessibility certificate or a service-level guarantee. Captions visible before the spoken phrase ends cannot be measured by this method.

The summary shows sample count, median, and nearest-rank p95 (`ceil(0.95 * n)`). For fewer than 20 observations p95 is the maximum; a small sample is not a stable percentile estimate. Keep raw rows and record setup differences in the notes.

## Controls and preservation

- A cue label is required, up to 200 characters; each note allows 1,000 characters.
- **See** before **Hear** records nothing. Repeated Hear cannot overwrite a pending start.
- **Cancel pending** creates no completed row. Hiding the tab discards the pending observation, preserving completed rows.
- H/S shortcuts ignore typing fields, modifier keys and auto-repeat.
- The log holds at most 200 observations. Downloading and clearing are unavailable during a pending observation.
- Data lives only in memory. Refreshing or closing loses the log; download first.

CSV correctly quotes delimiters and newlines. Formula-like labels/notes beginning with `=`, `+`, `-`, or `@`, including after whitespace/control characters, receive a leading apostrophe. Exact JSON preserves the accepted text without that spreadsheet-safety transformation. Treat exports as potentially sensitive.

## Context and ownership

Created as a practical companion to [PewTranslate's caption planning guide](https://pewtranslate.com/en/guides/live-captions-for-church). This standalone resource works independently of the planned translation service; PewTranslate accounts are not open yet. No audience testing or adoption is claimed.

No external dependencies, requests, analytics, cookies, storage or media collection. A restrictive CSP blocks connections. Optional reference links are ordinary navigation.

MIT licensed; see `LICENSE`.
