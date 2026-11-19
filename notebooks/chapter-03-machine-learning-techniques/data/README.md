# Data provenance

`gdp_per_capita_full.csv` is an archived **synthetic** dataset with 190 invented economies. It is not a World Bank download and cannot reproduce or verify empirical country results in the manuscript.

The corrected notebook writes separate files: `gdp_per_capita_synthetic.csv` for its default simulation and `gdp_per_capita_world_bank_2020.csv` for the optional live WDI download. Regional and income aggregates are excluded from the live country sample. Live revisions and missing indicators can change the sample size and model results.
