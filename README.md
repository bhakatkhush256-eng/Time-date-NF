# Employee Timesheet & Payroll Analysis

A small Excel exercise using **time functions** (`Time In`, `Time Out`, `(D-C)*24`) and payroll
formulas (`ROUND`, subtraction) to calculate hours worked, gross pay, deductions, and take-home
pay for 10 employees.

**Tools used:** Excel — Time functions, ROUND formula, conditional formatting-ready structure
**Source file:** `Time_date_NF.xlsx`

---

## Dataset

| Column | Description |
|---|---|
| Employee | Employee name |
| Wage | Hourly wage rate ($) |
| Time In / Time Out | Shift start and end time |
| Hours Worked | `=(Time Out - Time In)*24` |
| Gross Pay | `=ROUND(Hours Worked * Wage, 2)` |
| Deduction | Tax/benefit deduction ($) |
| Day's Pay | `=Gross Pay - Deduction` (take-home pay) |
| Tax Rate | 7.65% (only shown for row 1 as a reference rate) |

---

## Visualizations

**Hours Worked by Employee**
Amber Rios worked the longest shift (9.5 hrs); Sherman Moss the shortest (5.0 hrs).

![ image alt](https://github.com/bhakatkhush256-eng/Time-date-NF/blob/b04d21572b6dfe67abef439995ae096fd1ea02ac/hours_worked.png)

**Gross Pay vs Take-Home Pay**
Deductions scale with gross pay, so higher earners lose more in absolute dollars — but the
relative gap stays fairly consistent across employees.

![image alt](https://github.com/bhakatkhush256-eng/Time-date-NF/blob/da67735a728e68ead7ebbc20ba58332e1efbc32f/gross_vs_daypay.png)

**Wage Rate vs Hours Worked**
![image alt](https://github.com/bhakatkhush256-eng/Time-date-NF/blob/1ac3508e5f0bfeb8e134bc496afcf473f6744f99/wage_vs_hours.png)



---

## Insights

- **I found** Edna Hansen has the highest gross pay ($199.94) despite not having the highest
  wage rate — driven by her 8.75-hour shift, the second-longest in the dataset.
  **This means** total pay in this dataset is driven more by hours worked than by wage rate.
  **I recommend** tracking hours-worked trends alongside wage rate when analyzing payroll cost,
  rather than wage rate alone.

- **I found** Sherman Moss has both the lowest wage ($17.71) and the shortest shift (5.0 hrs),
  resulting in the lowest take-home pay ($81.78) — less than half of the highest earner's.
  **This means** the combination of low wage and short hours compounds into the biggest pay gap
  in the team.
  **I recommend** flagging employees who fall low on *both* metrics for a closer look (are short
  shifts scheduled or requested?).

- **I found** deductions average ~7.65% of gross pay across the dataset, consistent with the
  tax rate listed for the first employee.
  **This means** the same deduction rate is likely applied uniformly, even though it's only
  explicitly written in one cell.
  **I recommend** adding a `Tax Rate` value to every row (or a single formula referencing one
  rate cell) so the deduction logic is transparent and auditable.

---
