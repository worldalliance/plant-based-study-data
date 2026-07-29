# A two-week plant-based challenge: study data

De-identified data from a randomized evaluation of a two-week plant-based challenge,
conducted by the Alliance Foundation in May–June 2026.

Of 541 sign-ups, the 458 who completed an enrolment survey were randomly assigned to
attempt the challenge (treatment) or to eat as usual (control). Both arms reported the
animal products they ate every day for two weeks; a language-model pipeline converted
those free-text reports to grams of animal protein, and 200 of them were also coded by
hand for validation. Thirty days after the study ended, all participants received a
follow-up survey.

## Files

| File | Description |
|---|---|
| `data/participants.csv` | 541 rows, one per sign-up: demographics, enrolment survey, arm, daily protein totals, analysis flags. Most uses start here. |
| `data/participants_daily.csv` | The same 541 participants with per-category, per-day detail (meat / seafood / dairy / eggs, low–high ranges, coding basis) |
| `data/followup_30day.csv` | 247 responses to the 30-day follow-up survey |
| `data/validation_coding.csv` | 200 daily reports coded blind by a human, paired with the pipeline's output for the same report |
| `data/difficulty_themes.json` | 458 sets of difficulty themes, hand-coded from the free-text survey items |

Every column is defined in [CODEBOOK.md](CODEBOOK.md).

## Using the data

`participant_id` (`P0001`–`P0541`) is consistent across all five files, so they join on it.

Grams of animal protein use a fixed conversion throughout: 26 g per serving of meat or
seafood, 8.5 g per serving of dairy, 6.3 g per egg.

`d1_age` is binned and `d3_country` is reduced to United States / Other. All free text has
been removed. [DEIDENTIFICATION.md](DEIDENTIFICATION.md) lists what changed.

## Citation

<!-- TODO: paper title, authors, year, DOI / preprint URL -->

## Contact

Study team: contact@worldalliance.org

Data protection requests: support@plantbasedstudy.org

The participant information and consent sheet is at plantbasedstudy.org/information.

## Licence and conditions of use

Released under CC BY 4.0 — see [LICENSE.txt](LICENSE.txt).

Do not attempt to re-identify participants, and do not link these records to any other
dataset for that purpose.
