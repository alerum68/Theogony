# Date format settings

![Date format settings](images/user-guide/date-settings.png)

The Date Format Settings panel configures tree-wide rules for date parsing and display formatting across all data entry forms. Open this screen when you want to configure how ambiguous numeric dates are interpreted, customize standard display formats, or manage calendar conversion settings.

## What you see

- **Ambiguous Numeric Date Order:**
  - **Day / Month / Year (DMY)**: Standard European, British, Commonwealth, and military format (e.g., interpreting `03/04/1850` as *3 April 1850*).
  - **Month / Day / Year (MDY)**: Standard United States conventional format (interpreting `03/04/1850` as *March 4, 1850*).
  - **Year / Month / Day (YMD)**: ISO standard format (interpreting `1850/03/04` as *March 4, 1850*).
- **Default Display Format:** 
  - Standard Genealogical: `14 Oct 1882` (Day Month Year, 3-letter month).
  - Formal Long: `14 October 1882` or `October 14, 1882`.
  - ISO Numeric: `1882-10-14`.
- **Date Qualifiers and Range Formatting:**
  - Standard abbreviations for estimated dates: `abt` (about), `bef` (before), `aft` (after), `bet ... and ...` (between), `cal` (calculated), `est` (estimated).
- **Calendar Support:** Gregorian and Julian calendar changeover defaults (e.g., handling the British Empire's September 1752 changeover and double-dating notation like `1732/3`).

## Common tasks

### Configure ambiguous date interpretation

1. If your research primarily involves records from the United Kingdom, Europe, or Australia where dates were recorded as `DD/MM/YYYY`:
2. In the Ambiguous Date Order section, select **Day / Month / Year (DMY)**.
3. Select **Save Settings**.

Whenever you enter a numeric date like `05/06/1875` into any event form, Theogony automatically resolves it as *5 June 1875* rather than *May 6, 1875*.

### Set standard genealogical date display

1. Select **Standard Genealogical (`DD Mon YYYY`)** as the default display format.
2. Select **Save Settings**.

All dates throughout the Individuals Index, Person timeline, charts, and reports display consistently (for example, `12 May 1845`), avoiding ambiguous all-numeric formats that confuse researchers.

## Practical use cases

- **Working with American vs British record collections:** When transitioning from a British parish project to a United States federal census project, adjust your date interpretation setting so typed numeric dates match the convention used by the historical documents you are actively reading.
- **Handling dual dating (Old Style / New Style):** Enter dates using historical slash notation (such as `14 Feb 1745/6`). Theogony preserves the historical double-date notation while correctly calculating the ancestor's chronological age.

## Good to know

- Setting an interpretation rule does not alter already recorded dates; it governs how newly entered ambiguous dates are parsed upon input.
- You can always type three-letter month names explicitly (e.g., `3 Apr 1850` or `Apr 3 1850`) to bypass any numeric ambiguity completely.
- Date rules apply consistently across the entire tree and are preserved in the `.theo` database settings.
