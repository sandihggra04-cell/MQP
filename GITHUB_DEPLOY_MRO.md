# GitHub / Streamlit deployment — MRO Performance fix

This is the full flat-root project. Keep `app.py` and `engine_shop_visit_page.py`
**at the repository root**, not in an extra nested directory.

1. Replace the existing repository files with the contents of this ZIP; preserve your
   existing Streamlit Cloud secrets/settings. Select the branch Streamlit Cloud is deploying.
2. Commit the changed files (the functional app change is in
   `engine_shop_visit_page.py`; the Engine Shop Visit Drive URL in `fixed_sources.py`
   is already updated to `DATA ENGINE SHOP VISIT.xlsx`).
3. In Streamlit Cloud, verify the main file path is `app.py`; reboot the app.
4. Visit **Engine Shop Visit** -> select **MRO Performance**. The MRO selector is
   immediately below the MRO performance heading/description, above Engine type.
5. Select a specific MRO. A table with **ESN**, **Scope of Work**, and **TAT** appears
   directly under the selector, without choosing Engine type/Year/Scope first.

### Quick deployment check
Open the GitHub copy of `engine_shop_visit_page.py` and search for
`mro_performance_direct_detail_v535`. If missing, that branch hasn't been updated.
If it exists but does not appear in the running app, check the Streamlit Cloud
repository, branch, app entrypoint, and deployed commit. The app only shows files
that Streamlit Cloud actually deploys.

### Data handling
The selector uses all MRO records (including active and completed), while the
existing comparisons still use their original eligible completed records and
scope-controlled logic. TAT is the application's preexisting normalized TAT;
invalid/missing values show `Check data` or `—` as in other tables.

No unrelated application modules, KPI formulas, filters, or visuals have been modified.
