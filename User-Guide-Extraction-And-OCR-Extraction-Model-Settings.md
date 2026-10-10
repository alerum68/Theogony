# Extraction model settings

![Extraction model settings](images/user-guide/extraction-settings.png)

The Extraction Model Settings panel configures the generative AI provider, model selection, prompt strictness, and security credentials used by Theogony's evidence extraction pipeline. Open this screen to connect your AI API key, switch between models, or adjust extraction constraints.

## What you see

- **Provider and Security Credentials:**
  - **Provider**: Google Gemini AI.
  - **API Key Status**: Shows whether a valid API key is installed. Keys are stored securely in your operating system's native keychain (such as Windows Credential Manager), never in the database or plain-text config files.
  - **Set / Update API Key**: Button to enter or replace your API key securely.
- **Model Selection:**
  - Dropdown to choose the active model (such as `gemini-3.5-flash-lite` for high-speed, cost-effective processing, or `gemini-2.5-flash`).
- **Extraction Behavior and Constraints:**
  - **Temperature / Strictness Slider**: Controls model determinism. Set low (e.g., `0.1` or `0.0`) to enforce strict literal adherence to document text and prevent speculation.
  - **Hallucination Safeguards**: Toggles requiring the model to cite exact word and line references for every extracted assertion.
- **Terms of Service Protections:**
  - Displays the active repository protection rules, confirming that sources linked to restricted third-party archives are gated against external cloud calls.

## Common tasks

### Connect your Gemini API key

1. Select **Set API Key**.
2. Paste your Google AI Studio Gemini API key into the secure input dialog.
3. Select **Save Key**.

Theogony stores the secret in your system keychain. The key is never committed to your tree database or shared across exports.

### Choose a cost-effective extraction model

1. Open the **Active Model** dropdown.
2. Select `gemini-3.5-flash-lite`.
3. Select **Save Settings**.

This model provides high extraction speed and accurate structured JSON output at minimal token cost, ideal for processing large batches of census and vital records.

### Enforce strict extraction accuracy

1. Ensure the **Temperature** slider is set to its minimum value (`0.0`).
2. Verify that **Strict Evidence Grounding** is enabled.
3. Select **Save Settings**.

This ensures that the model only extracts facts explicitly written on the page, forbidding it from guessing middle names, calculating unstated birth years, or inferring undocumented relationships.

## Practical use cases

- **Balancing cost and complex document interpretation:** Use `gemini-3.5-flash-lite` for straightforward standardized records (like printed marriage certificates and vital ledgers), and switch to larger models when interpreting multi-page narrative estate disputes with complex legal syntax.
- **Ensuring research reproducibility:** Setting the model temperature to zero ensures that re-running extraction on the same transcribed text produces consistent, identical structured assertions every time.

## Good to know

- You do not need a paid API tier to use AI extraction; Google's free-tier Gemini API keys can be used within standard rate limits.
- Theogony never makes background AI calls automatically. Every cloud request requires explicit user confirmation via the **Extraction Estimate Dialog**.
- If no API key is configured, all manual transcription and local Tesseract OCR features continue to operate normally with zero limitations.
