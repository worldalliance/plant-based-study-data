# Codebook

Column definitions for every file in this repository.

Grams of animal protein use a fixed conversion throughout: 26 g per serving of meat
or seafood, 8.5 g per serving of dairy, 6.3 g per egg.

> `d1_age` is binned and `d3_country` is reduced to United States / Other.
> See DEIDENTIFICATION.md.

### `data/participants.csv`

One row per sign-up. This is the file most analyses start from.

541 rows x 32 columns.

| Column | Type | Description |
|---|---|---|
| `participant_id` | object | De-identified participant key (P0001-P0541), consistent across all files. |
| `arm` | object | Random assignment: treatment (attempt the challenge) or control (eat as usual). Blank = completed the initial survey but was not randomized. |
| `d1_age` | float64 | Age, binned (see DEIDENTIFICATION.md). Not an exact age. |
| `d2_gender` | object | Self-reported gender. |
| `d3_country` | object | United States / Other (reduced from a free-form location field). |
| `d4_diet` | object | Self-described diet at enrollment (omnivore / vegetarian / pescatarian). |
| `q1_meat` | float64 | Baseline survey: servings of meat on a typical day. |
| `q2_dairy` | float64 | Baseline survey: servings of dairy on a typical day. |
| `q3_eggs` | float64 | Baseline survey: eggs on a typical day. |
| `q4_motivation` | object | Primary motivation for joining. |
| `q5_expected_difficulty` | float64 | Expected difficulty of reducing, rated at enrollment (1-5). |
| `baseline_protein_g` | float64 | Baseline animal protein, g/day, from q1-q3 at 26 g/serving meat, 8.5 g/serving dairy, 6.3 g/egg. |
| `day1_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day2_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day3_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day4_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day5_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day6_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day7_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day8_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day9_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day10_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day11_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day12_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day13_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day14_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `q7_experienced_difficulty` | float64 | Experienced difficulty, rated at study end (1-5). |
| `q9_plan` | object | "Do you plan to incorporate more plant-based foods into your long-term diet as a result of the study?" |
| `mean_daily_protein_g` | float64 | Mean reported animal protein across valid study days, g/day. |
| `valid_days` | float64 | Number of the 14 study days with a usable log. |
| `nonresponse_days` | float64 | Number of study days with no log submitted. |
| `included_in_hypothesis` | object | True for the 274 participants who reported on enough days to meet the study's data-quality rule. |

### `data/participants_daily.csv`

Per-category, per-day detail. Only `day1_*` columns are listed below; `day2_*` through `day14_*` repeat the identical pattern.

541 rows x 245 columns.

| Column | Type | Description |
|---|---|---|
| `participant_id` | object | De-identified participant key (P0001-P0541), consistent across all files. |
| `d1_age` | float64 | Age, binned (see DEIDENTIFICATION.md). Not an exact age. |
| `d2_gender` | object | Self-reported gender. |
| `d3_country` | object | United States / Other (reduced from a free-form location field). |
| `d4_diet` | object | Self-described diet at enrollment (omnivore / vegetarian / pescatarian). |
| `q1_meat` | float64 | Baseline survey: servings of meat on a typical day. |
| `q2_dairy` | float64 | Baseline survey: servings of dairy on a typical day. |
| `q3_eggs` | float64 | Baseline survey: eggs on a typical day. |
| `q4_motivation` | object | Primary motivation for joining. |
| `q5_expected_difficulty` | float64 | Expected difficulty of reducing, rated at enrollment (1-5). |
| `arm` | object | Random assignment: treatment (attempt the challenge) or control (eat as usual). Blank = completed the initial survey but was not randomized. |
| `baseline_protein_g` | float64 | Baseline animal protein, g/day, from q1-q3 at 26 g/serving meat, 8.5 g/serving dairy, 6.3 g/egg. |
| `baseline_meat_g` | float64 | Baseline meat component, g/day. |
| `baseline_dairy_g` | float64 | Baseline dairy component, g/day. |
| `baseline_eggs_g` | float64 | Baseline egg component, g/day. |
| `day1_meat_low` | float64 | low bound of the pipeline's serving estimate for meat on day N. |
| `day1_meat_high` | float64 | high bound of the pipeline's serving estimate for meat on day N. |
| `day1_seafood_low` | float64 | low bound of the pipeline's serving estimate for seafood on day N. |
| `day1_seafood_high` | float64 | high bound of the pipeline's serving estimate for seafood on day N. |
| `day1_dairy_low` | float64 | low bound of the pipeline's serving estimate for dairy on day N. |
| `day1_dairy_high` | float64 | high bound of the pipeline's serving estimate for dairy on day N. |
| `day1_eggs_low` | float64 | low bound of the pipeline's serving estimate for eggs on day N. |
| `day1_eggs_high` | float64 | high bound of the pipeline's serving estimate for eggs on day N. |
| `day1_meat_g` | float64 | Protein from meat reported on study day N, g. |
| `day1_seafood_g` | float64 | Protein from seafood reported on study day N, g. |
| `day1_dairy_g` | float64 | Protein from dairy reported on study day N, g. |
| `day1_eggs_g` | float64 | Protein from eggs reported on study day N, g. |
| `day1_total_protein_g` | float64 | Total animal protein reported on study day N, g. |
| `day1_basis` | object | How day N was coded: logged, imputed, or missing. |
| `day1_reattributed` | object | Whether day N's entry was reassigned to a different date. |
| `day1_other` | object | Non-animal-product items noted on day N. |
| `q7_experienced_difficulty` | float64 | Experienced difficulty, rated at study end (1-5). |
| `q9_plan` | object | "Do you plan to incorporate more plant-based foods into your long-term diet as a result of the study?" |
| `mean_daily_protein_g` | float64 | Mean reported animal protein across valid study days, g/day. |
| `valid_days` | float64 | Number of the 14 study days with a usable log. |
| `nonresponse_days` | float64 | Number of study days with no log submitted. |
| `included_in_hypothesis` | object | True for the 274 participants who reported on enough days to meet the study's data-quality rule. |

### `data/followup_30day.csv`

30-day follow-up survey.

247 rows x 5 columns.

| Column | Type | Description |
|---|---|---|
| `participant_id` | object | De-identified participant key (P0001-P0541), consistent across all files. |
| `q10_meat` | float64 | Follow-up survey: servings of meat on a typical day, 30 days after the study. |
| `q11_dairy` | float64 | Follow-up survey: servings of dairy on a typical day. |
| `q12_eggs` | float64 | Follow-up survey: eggs on a typical day. |
| `q13_change` | object | Follow-up self-assessment: much_less / somewhat_less / about_the_same / somewhat_more / much_more, compared with before the study. |

### `data/validation_coding.csv`

200 daily reports coded blind by a human, paired with the pipeline output for the same report.

200 rows x 19 columns.

| Column | Type | Description |
|---|---|---|
| `id` | int64 | Row identifier within the validation set. |
| `participant` | object | Participant key of the daily report that was coded. |
| `day` | int64 | Study day (1-14) of the coded report. |
| `coder` | object | Human coder identifier. |
| `human_meat` | float64 | Human coder's serving count for meat. |
| `human_seafood` | float64 | Human coder's serving count for seafood. |
| `human_dairy` | float64 | Human coder's serving count for dairy. |
| `human_eggs` | float64 | Human coder's serving count for eggs. |
| `human_total_g` | float64 | Human coder's total animal protein for the report, g. |
| `flag` | int64 | Coder flag for ambiguous logs. |
| `llm_meat_lo` | float64 | Pipeline's lo bound for meat on the same report. |
| `llm_meat_hi` | float64 | Pipeline's hi bound for meat on the same report. |
| `llm_seafood_lo` | float64 | Pipeline's lo bound for seafood on the same report. |
| `llm_seafood_hi` | float64 | Pipeline's hi bound for seafood on the same report. |
| `llm_dairy_lo` | float64 | Pipeline's lo bound for dairy on the same report. |
| `llm_dairy_hi` | float64 | Pipeline's hi bound for dairy on the same report. |
| `llm_eggs_lo` | float64 | Pipeline's lo bound for eggs on the same report. |
| `llm_eggs_hi` | float64 | Pipeline's hi bound for eggs on the same report. |
| `llm_total_g` | float64 | Pipeline's total animal protein for the report, g. |

### `data/difficulty_themes.json`

Hand-coded difficulty themes. Keys are `<item>::<participant_id>` where item is `q6` (difficulties expected at enrollment) or `q8` (difficulties experienced at study end); values are lists of theme labels. The raw text that was coded is not released.

Example key format: `q6::P0123`.
