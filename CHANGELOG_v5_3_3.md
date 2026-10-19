# v5.3.3 — Engine Completed Filter Fix

- Fixed Engine Shop Visit monitoring filter behavior when `Phase = All` and an explicit `Progress` value is selected.
- Previously `Phase = All` pre-filtered the dataset to `Status = Active`, so selecting `Progress = completed` always returned 0 records.
- Now the default view still shows Active records when no Progress filter is selected, while any explicit Progress selection searches the full Engine Shop Visit history.
- `Progress = completed` therefore correctly returns completed records.
