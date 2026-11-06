# Observability & Cost Report · <system>

| | |
|---|---|
| System | <system, version / commit> |
| Model and price | <model, provider, price per 1M tokens input / output, cache factors, date of the price list>. Migration candidate: <model, price> |
| Trace backend | <trace backend, version, model definition> |
| Date of measurements | <date> |
| Runs per condition | <N per scenario> |
| Measured with | <kit / runner and versions> |

## Slide 1 · Trace vs counter

**Session in the trace UI:** <session id, scenario, profile: number of traces, duration, Total Cost, tokens>.

![<sessions list with Total Cost>](screenshots/<file>.png)
![<one session: all steps of one dialog in one list>](screenshots/<file>.png)

**Blind-spot map:**

| Counter | What it shows | What is really true | Where the truth is |
|---|---|---|---|
| <system self-report> | | | |
| <trace UI without a model definition> | | | |
| <trace UI with only input / output prices> | | | |
| <history compression / reasoning tokens> | | | |

**Incident analysis. Scenario:** <what the user did, which entities had to survive to the end, profile, session id>.

| Step | Span | What is recorded in it | Where it diverged |
|---|---|---|---|
| | | | |

**What was in the generation input on the step where it diverged:** <what the input contained and what was missing from the output; check verdict>.

One sentence for the regulator: <on which span and what exactly was lost>.

**Price from three sources** (money per dialog):

| Scenario | Condition | System self-report | Sum of spans | Provider bill | Reconciliation |
|---|---|---|---|---|---|
| | | | | | |

**Scenario price** (<scenario, number of steps, median of N runs>; money from the trace):

| | normal | current build | ratio |
|---|---|---|---|
| Input tokens, median | | | |
| Time, median | | | |
| Price, median | | | |

<step-level check: name, threshold, median on normal and on current build; what the generation input shows>.

## Slide 2 · Forecast

| Floor | Value | Where from (measured / calculated) |
|---|---|---|
| Step | | |
| Scenario | | |
| Month | | |
| Forecast | | |

**Assumptions:**

| Assumption | Value | Source |
|---|---|---|
| Active users | | |
| Dialogs per user | | |
| Scenario mix | | |

**Month for the current number of users, current model:** <calculation, per candidate model>.

**Formula for N:** <linear part>.

**What grows faster than N:** <the line that a linear extrapolation will miss>.

## Slide 3 · Decision

| Lever | What it gives | What breaks |
|---|---|---|
| | | |
| | | |
| | | |

- **What we traded:**
- **What we don't do:**
- **When the decision changes:**

### Model migration

<model "was" → model "want"; scenarios, number of runs, profiles, price source>.

| Model | Scenario | Condition | $ dialog, median (range) | Time, median | Check 1 | Check 2 | Tokens (reference only) |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

- **What is cheaper per dialog:**
- **What stayed green:**
- **What the checks don't see:**
- **Decision (we switch / we don't switch / we switch if):**
- **Thresholds to re-take:**
- **What stays unmeasured** (goes to the judge): <list of specific answers>.

**Budgets in cases:** <file, set hash, case ids, which are daily and which are release, report files>.

| Case | Catches | normal | current build | Failed condition on current build |
|---|---|---|---|---|
| | | | | |

<why the two defects need different checks>.

<note on the runner: how its budget check counts tokens, identical calls and latency>.

**Threshold calibration** (<case>, `tokens_total`):

| `tokens_total` threshold | normal | current build | Verdict |
|---|---|---|---|
| | | | too loose |
| | | | too tight |
| | | | ours |

<medians the table was built from, number of runs, margin in %>.
