# Debt Fraction Calculator
This code utilizes the processing code of the `lcoe_calculator` module with the [PySAM](https://nrel-pysam.readthedocs.io/en/main/)
package to compute new debt fractions given the cost and tax credit assumptions in the ATB data workbook `xlsx` document.

For more on the financial assumptions used for these calculations see the [ATB documentation](https://atb.nlr.gov/electricity/2025/financial_cases_&_methods)
and the [SAM documentation](https://sam.nrel.gov/financial-models/utility-scale-ppa.html).

To run:
- Open the data workbook Excel file and make your desired adjustments to the data (With tax credits vs without tax credits cases)
- From the root repository folder run `python -m debt_fraction_calculator.debt_fraction_calc` as
described in the main repository README
- Copy values to the WACC Calc tab of the data workbook as appropriate. Typically this means taking the debt fractions from the output spreadsheet, and copying the same row three times for the with tax credits case. For the without tax credits case, only the value from the base year should be copied into the base year for all three rows.
- Note that Utility Scale PV plus Battery requires two runs: one for ITC only and one for PTC + ITC. These need to be copied into the lower debt fraction lines (the main debt fraction line is an if statement controlled by a drop down)