# De-identification

What differs between the study's internal files and the data published here. Read this
before interpreting `d1_age`, `d3_country`, or any absence you notice.

## Participant identifiers

Source identifiers were replaced with sequential keys `P0001`–`P0541`. The mapping was not
retained, so these rows cannot be joined back to the study's own systems. The same mapping
was applied to all five files, so joins within this release work.

## Free text removed

Forty-eight free-text columns were dropped from the participant tables, plus the coder
note column from the validation set:

- `day1_response` … `day14_response` — the daily food reports
- `day1_notes` … `day14_notes` and `day1_flags` … `day14_flags` — coder notes and flags
- `q6_expected_difficulties`, `q8_experienced_difficulties`
- `q10_anything_else`, `q11_join_reason`, `q4_motivation_other`, `d2_gender_other`

Participants were told that raw message text would not be released, and the reports name
family members, restaurants, and places.

`data/difficulty_themes.json` holds only the theme labels assigned to the free-text
difficulty responses, not the responses themselves.

## Age binned

`d1_age` is not an exact age. Each bin is represented by a fixed value:

| Source age | Released value |
|---|---|
| 18–25 / 26–30 / 31–35 | 21 / 28 / 33 |
| 36–40 / 41–45 / 46–50 / 51–55 | 38 / 43 / 48 / 53 |
| 56–60 / 61–65 / 66–70 / 71–75 / 76+ | 58 / 63 / 68 / 73 / 78 |

## Country reduced

The source field was free-form and often held a city or state. `d3_country` gives only
`United States` or `Other`.

## Follow-up identifiers and timestamps

The row identifier and the submission timestamps were removed from the follow-up file.

## Condition of use

Do not attempt to re-identify participants, and do not link these records to any other
dataset for that purpose.

Researchers who need the withheld fields should contact contact@worldalliance.org; access
would require a data-use agreement and ethics review. Note that the daily food reports are
covered by the commitment not to release raw message text.
