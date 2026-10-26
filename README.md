# -econ5200-lab08-hypothesis-testing
# Diagnosing Underpowered Studies and P-Hacking

## Objective
I used statistical tests and simulations to study low statistical power, p-hacking, multiple testing, and the reliability of experimental results.

## Methodology
- Evaluated the statistical power of a pilot study with 15 people per group and calculated the sample size needed to reach 80% power.
- Applied the Benjamini-Hochberg correction to 20 subgroup tests to check whether significant results remained after adjusting for multiple comparisons.
- Simulated 20 tests under true null hypotheses across 1,000 replications and compared the observed false-positive rate with its theoretical expectation.
- Implemented my own Benjamini-Hochberg function and checked its results against `statsmodels` using data with two planted real effects.
- Compared four statistical tests on heavy-tailed earnings data to examine how the choice of test statistic and testing method affected the results.
- (Challenge) Simulated Brodeur's "camel" to examine how p-hacking changed the share of statistically significant results.

## Key Findings
- The pilot study had only 10.9% power with 15 people per group. Reaching 80% power required 216 people per group, at which sample size the test produced a p-value of 0.0014.
- After the Benjamini-Hochberg correction, 0 of the 20 subgroups remained statistically significant.
- In the null simulation, 65.8% of 1,000 replications had at least one p-value below 0.05, close to the theoretical rate of 64.2%.
- My Benjamini-Hochberg function agreed with `statsmodels` and identified 2 subgroups when two real effects were planted.
- The four tests on heavy-tailed earnings data differed mainly according to the statistic being tested, rather than whether the test was parametric or permutation-based.
- (Challenge) P-hacking increased the share of significant results from 0.242 to 0.313.
