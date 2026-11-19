# Data provenance

`loan_data.csv` is the bundled **synthetic** 400-application teaching fixture, not observed lending data. Its labels were generated from income and credit-history inputs. Do not use its scores to infer real approval, default or fairness performance.

`loan_preprocessed.csv` is an **archived output from the older notebook**. Its preprocessing used the full sample, so it must not be split afterward to claim independent test performance. It is retained for historical comparison and is not read by the corrected notebook.

Run the corrected notebook to create `loan_preprocessed_train.csv` and `loan_preprocessed_test.csv`. It splits applications first, fits preprocessing on training rows, and transforms the holdout with those fitted parameters. If you replace the input CSV, verify its provenance and the notebook's currency, income-frequency and principal-unit assumptions.
