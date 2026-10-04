# OCR configuration and engines

![OCR configuration and engines](images/user-guide/ocr-settings.png)

Configure text extraction engines, language packs, image preprocessing filters, and local or cloud AI transcription settings for your source documents. Open this panel when you need to add API keys for cloud vision services, set the file path for local OCR tools, or adjust recognition languages.

## What you see

The PDF embedded text layer card displays the built-in reader status for extracting selectable text from digital documents without an API connection.

The Tesseract OCR card shows whether the local optical character recognition engine is installed, along with fields for the binary path and plus-separated language codes.

The Gemini AI card contains options for cloud text extraction, including fields for API keys, model selection, tier choices, token allowances, batch multipliers, and per-model pricing overrides.

## Common tasks

### Add a Gemini API key

1. Enter your key in the **Gemini API Key** field.
2. Select **Save Key**.
3. See the status message confirm that the key is saved to the operating system keyring.

### Choose a Tesseract binary path

1. Enter the executable location in the **Tesseract binary path (optional override)** field or select **Browse…** to locate the file.
2. Click outside the field to save the path automatically.

### Adjust OCR recognition languages

1. Type your language codes separated by plus signs in the **OCR languages (plus-separated, e.g. eng+deu)** field.
2. Click outside the field to save the language settings automatically.

## Good to know

API keys entered here are stored securely in your operating system keychain or credential manager.
