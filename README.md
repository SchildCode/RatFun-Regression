# RatFun-Regression
A spreadhseet with visual basic code for fast and accurate single-parameter symbolic regression using **rat**ional **fun**ctions. [Rational functions](https://en.wikipedia.org/wiki/Rational_function) are ideal for approximating complex analytical formulae, and for regressions to empirical data such as thermodynamic properties. They have the following form:

   *y* = (*a<sub>0</sub> + a<sub>1</sub>·x + a<sub>2</sub>·x² +...+ a<sub>n</sub>·x<sup>n</sup>*) / (*b<sub>0</sub> + b<sub>1</sub>·x + b<sub>2</sub>·x² +...+ b<sub>m</sub>·x<sup>m</sup>*)

Where either coefficient *a*<sub>0</sub> or *b*<sub>0</sub> is set to 1:
- For **[Padé approximant](https://en.wikipedia.org/wiki/Pad%C3%A9_approximant)**: *b*<sub>0</sub>=1, and *a*<sub>0</sub> can have any value (also zero). The simplest such equation is
*y* = *x*.
- For **reciprocal Padé approximant**: *a*<sub>0</sub>=1, and *b*<sub>0</sub> can have any value (also zero). This regression is only applied in cases where all *x* and *y* values are non-zero. The simplest such equation is *y* = 1/*x*.

### How to use the program
- **STEP 1**: Enter a data set (*x* and *y* values) in columns A & B of sheet ***1.Data***.  If the y-values have different weights or uncertainties, enter these in column C.
- **STEP 2**: Adjust the user-definable settings in sheet ***2.Options***.  These settings include the maximum exponent of *x* in the rational function, and the maximum number of polynomial coefficients permitted.
- **STEP 3**: Click on the tab for sheet ***3.Analyze***, and wait for results to appear in sheet ***4.Results***:
  - The solver to generates all combinations of rational functions with up to the given number of coefficients.
  - For each function, the polynomial coefficients are fitted by SVD ([Singular-Value Decomposition](https://en.wikipedia.org/wiki/Singular_value_decomposition)) that can omit outliers with a user-defined tolerance.
  - All fitted equations are tested for singularities in the denominator.
  - All fitted equations that pass the test are output in [Horner's nested form](https://en.wikipedia.org/wiki/Horner%27s_method), for fastest possible calculation. 
  - For each equation, statistics are reported including *[R²](https://en.wikipedia.org/wiki/Pearson_correlation_coefficient)*, *[X²](https://en.wikipedia.org/wiki/Chi-squared_distribution)*, [mean and maximum absolute error]((https://en.wikipedia.org/wiki/Mean_absolute_error)), and [Akaike Information Criterion](https://en.wikipedia.org/wiki/Akaike_information_criterion).
- **STEP 4**: Select your preferred equation by sorting the results in sheet ***4.Results*** by a statistic of your choice in columns B-G. The best candidate equations are flagged in column *Pareto*.

### Installation and activation
- Simply download the spreadsheet file and open it in Microsoft Excel. No installation or registration is needed.
- However, this is a Visual Basic macro-enabled spreadhseet. You must activate macros for it to function: 
  - When you open the file for the first time in Excel, you will see a yellow bar at the top of the window, with the message *"PROTECTED VIEW Be careful... [Enable Editing]"*. Click on the 'Enable Editing' button. 
  - Next, depending on the security settings on your installation of Microsoft Excel, a red bar may appear at the top of the window, with the message *"BLOCKED CONTENT Macros in this document have been disabled..."*. This can be solved by moving the file to a directory on your PC that you designate for files that you trust, then open the file in Excel. To designate a 'trusted directory', click on **File > Options > Trust Center > Trust Center Settings > Trusted Locations > Add new location**, then browse to a directory, e.g. C:\TEMP\. Finally check that **Trust Center Settings > Trusted Documents > Disable Trusted Documents**  is not ticked.
  - When macros are properly activated, **BEMS-hourly-values** shows a small square splash-screen when you open the file. This splash screen shows the licence info, and advises you if an update is available for download from GitHub. Simply press 'Close' button to close the splash-screen. 
  - If still no splash-screen appears, then you might be able to fix it by menu option **File > Options > Trust Center > Trust Center Settings > Macro Settings > Disable all macros with notification**, which is a suitable level of security.
  
### License & warranty
- Distributed under the GLP v3 lisence (https://www.gnu.org/licenses/gpl-3.0.en.html). Please acknowledge/attribute use of this software in your report/publication with an appropriate author citation and URL to this site.
- Provided without warranty of any kind.

### Author & copyright owner
© Peter.Schild@OsloMet.no
