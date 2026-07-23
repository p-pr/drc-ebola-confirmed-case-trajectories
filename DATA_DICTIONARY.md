# Data dictionary

## `data/source-data.csv`

This is the canonical, long-form dataset. Each row represents one published cumulative confirmed-case total.

| Column | Type | Meaning |
|---|---|---|
| `outbreak` | text | Chart label for the outbreak: `DRC 2026`, `DRC 2018-20`, or `DRC 2012`. |
| `virus_species` | text | Ebola virus species associated with the outbreak. |
| `announcement_date` | date | Date used as day zero, in `YYYY-MM-DD` format. |
| `observation_date` | date | Date associated with the published case total, in `YYYY-MM-DD` format. |
| `days_elapsed` | integer | Calendar days between `announcement_date` and `observation_date`. |
| `confirmed_cases` | integer | Cumulative laboratory-confirmed cases reported as of the observation date. Unit: people. |
| `observation_type` | text | `contemporaneous_report` for a total published during the outbreak; `retrospective_final` for a later final tally. |
| `source_name` | text | Organization or dataset that published or compiled the observation. |
| `source_url` | URL | Direct link to the relevant source or underlying bulletin. |
| `notes` | text | Row-specific clarification. Blank when no additional note is needed. |

## `data/datawrapper.csv`

This is the processed file used to make the chart.

| Column | Type | Meaning |
|---|---|---|
| `days_elapsed` | integer | Days since officials announced the outbreak. |
| `DRC 2018-20` | integer or blank | Published cumulative confirmed-case total for the 2018–20 outbreak. |
| `DRC 2026` | integer or blank | Published cumulative confirmed-case total for the 2026 outbreak. |
| `DRC 2012` | integer or blank | Contemporaneously published cumulative confirmed-case total for the 2012 outbreak. |
| `DRC 2012 — timing unknown` | integer or blank | Two endpoints used for the dotted connector from the last contemporaneous 2012 total to the retrospective final tally. |

A blank cell means no confirmed-case observation is available for that outbreak and day. It does not mean zero cases.
