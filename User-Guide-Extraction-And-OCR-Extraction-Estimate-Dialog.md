# Extraction estimate dialog

![Extraction estimate dialog](images/user-guide/extraction-estimate.png)

The Extraction Estimate Dialog provides full transparency before any cloud AI request is dispatched. It calculates anticipated LLM token usage, estimated costs in USD, and projected processing times. You see this dialog whenever you trigger an AI extraction pass from the Extraction Panel or Promoted Media.

## What you see

- **Model Details:** Displays the active AI provider (Google Gemini) and the specific model selected (such as `gemini-3.5-flash-lite`).
- **Token Usage Breakdown:**
  - **Input Tokens**: The size of the prompt, including the document transcription text and the extraction template instructions.
  - **Estimated Output Tokens**: The anticipated size of the generated structured JSON payload containing personas and assertions.
  - **Total Tokens**: The sum of prompt and completion tokens.
- **Estimated Cost:** The projected cost in USD calculated from current provider pricing rates (often less than $0.001 per document on standard flash models).
- **Execution Action Buttons:** **Proceed with Extraction** on the left to authorize the call, and **Cancel** on the right to abort without sending any data.

## Common tasks

### Review and approve extraction cost

1. Trigger an extraction run by selecting **Run Extraction** in the Extraction Panel.
2. The **Extraction Estimate Dialog** opens immediately.
3. Review the token count and estimated cost.
4. Select **Proceed with Extraction** to dispatch the request.

The dialog closes, a progress indicator appears in the status bar, and the extracted candidate claims populate the results panel once completed.

### Abort an extraction run

1. If you notice that an accidentally selected multi-page book text contains 50,000 tokens and you only intended to process a single page:
2. Select **Cancel** (or press the `Escape` key).

The dialog closes immediately. No external API call is made, and no tokens or costs are incurred.

## Practical use cases

- **Budget management for high-volume document projects:** When processing hundreds of family records, the estimate dialog ensures you always know the exact cost before dispatching an extraction pass.
- **Catching accidental large prompt dispatches:** If you accidentally pasted an entire 200-page book index into the transcription editor instead of a single page, the token counter will show an unusually large number, alerting you to cancel before sending an unintended request.

## Good to know

- If you are using a Gemini API key within Google's free-tier quota, the estimated cost reflects standard commercial rates for informational purposes, but your account is not billed.
- The dialog calculates token counts locally using standard sub-word tokenization algorithms before opening a network connection.
- Theogony will **never dispatch a cloud AI call silently in the background**. Every single cloud request requires explicit manual confirmation through this dialog.
