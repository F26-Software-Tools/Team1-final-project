# Team 1 — Checkpoint 2

**Team members:** Tin Vu and Jason Sauer  
**Course:** ADAN/ADEC7900 Software Tools

## 1. Research Topic

We are studying housing affordability in Massachusetts, focusing on tax-credit properties whose affordability protections may be expiring. Under the federal Low-Income Housing Tax Credit (LIHTC), properties placed in service since 1990 must stay affordable for at least 30 years. Properties placed in service between 1997 and 2001 therefore reach Year 30 between 2027 and 2031.

**Research question:** *Which Massachusetts neighborhoods have both many affordable apartments in tax-credit properties reaching 30 years in service between 2027 and 2031 and a high share of renters already spending at least 30% of their income on rent and utilities?*

**Approach:** We combine HUD property data with Census data by census tract, a small area that represents a neighborhood. We count the affordable apartments in properties approaching 30 years and compare those counts with how stretched renters already are. A chart then shows where the two overlap, so Massachusetts housing staff can see which properties to review first. Some properties have longer affordability agreements, so reaching 30 years is a reason to check the agreement, not proof that protections end.

**Follow-up analysis:** We compare each neighborhood's total number of these apartments with the number per 100 renter households. This shows whether smaller neighborhoods move up the list once the size of their rental market is taken into account.

**Decision maker (proposed):** Housing staff at the Massachusetts Executive Office of Housing and Livable Communities (EOHLC), the state's tax-credit allocating agency, who decide which properties to review and prioritize for preservation.

## 2. GitHub Repository and Collaboration

Jason created the team repository within the course GitHub organization and created the `Team_1Checkpoint_2.0` branch for this submission.

The repository is organized so the analysis can be rerun from the files.

As we collaborate on analytical files, each of us will work on a named branch, use descriptive commit messages, and merge through pull requests the other reviews. 

## 3. Merging Multiple Data Sources

We plan to merge two public datasets by census tract and cross-checked the results against a third source.

**HUD Low-Income Housing Tax Credit (LIHTC) Properties.** This dataset provides each property's location, year placed in service, and reported low-income unit count. Massachusetts has 994 LIHTC records. Of these, 136 were placed in service in 1997–2001, and together they report 10,869 low-income units. We kept the 129 records with usable coordinates and HUD's recommended geocoding quality codes. The seven excluded records include Orchard Park I, IIIA and IIIB in Roxbury.

**U.S. Census Bureau American Community Survey (ACS), 2020–2024 five-year estimates.** This dataset provides 1,620 Massachusetts tracts with renter households (B25003), median gross rent (B25064), median renter household income (B25119), and rent burden (B25070). From B25070 we calculate the share of renter households spending at least 30% of income on rent and utilities, using only households whose burden could be calculated.

**Literature review (started).** HUD's 2012 study of properties at Year 15 found that about 32% of 11,290 properties studied were no longer monitored by state agencies by 2009. A 2026 preprint linking all LIHTC properties to a tract panel found that exits are less likely where recorded affordability commitments run beyond 30 years. A 2026 University of Washington thesis found that rents at fully deregulated Washington properties averaged near the 60% of area median income ceiling but varied widely. We still need to review peer-reviewed work on LIHTC neighborhood effects.

## 4. Data Visualization

We are using **R** with Quarto. We use `tidycensus` for ACS data, `sf` and `tigris` for the spatial tract match, and `ggplot2` for charts. R let us pull Census data directly, handle geographic boundaries, and keep the whole workflow in one reproducible document.

A map of the review-first tracts is planned for Checkpoint 3.

## 5. Summary Statistics and KPIs

| Measure (tracts with properties reaching Year 30) | Mean | Median | Min | Max |
|---|---:|---:|---:|---:|
| Low-income units reaching Year 30 per tract (n = 112) | 94.3 | 51.0 | 6 | 620 |
| Units per 100 renter households (n = 112) | 10.4 | 6.6 | 0.9 | 76.0 |
| % renters spending 30%+ on rent and utilities (n = 113) | 55.4 | 55.5 | 20.9 | 84.5 |
| Median gross rent (n = 111) | $1,589 | $1,484 | $491 | $3,501 |
| Median renter household income (n = 107) | $52,953 | $44,578 | $16,303 | $139,911 |

For comparison, the median rent-burden share across all Massachusetts tracts is 51.5%. Tracts with properties approaching Year 30 are already more stretched than the typical tract.

## 6. Project Checkpoints

**Checkpoint 2 (this submission):** We defined the research question and follow-up analysis, collected and merged HUD and ACS data by census tract, ran the data-quality checks, calculated summary statistics, and cross-checked the flagged properties against the CEDAC inventory.

**Next week priorities:** Confirm the decision maker. Map the review-first tracts. Test how sensitive the list is to the review-first thresholds and to ACS margins of error. Check the affordability agreements of the top properties where records are available. Continue the literature review.

## 7. Video Presentation

The planned storyline is addressed to the decision maker EOHLC housing staff. About 10,900 low-income units in Massachusetts tax-credit properties reach Year 30 between 2027 and 2031. These properties sit in neighborhoods where renters are already more stretched than average. Sixteen neighborhoods combine many expiring units with high rent burden. Adjusting for market size lifts smaller towns such as Greenfield and Gardner. Symphony Plaza West faces two expiration clocks at once. 

## 8. Final Markdown Report

The final report has not been written yet, but its results section is drafted in `FINDINGS.md`. The final report will include an introduction, data summary, analysis and visualizations, a conclusion discussing limitations and future work, and a separate policy recommendation section.

The key limitations to discuss are already clear:

* Reaching Year 30 marks a date to check, not a confirmed expiration.
* ACS tract estimates have wide margins of error.
* Seven properties could not be located.
* The review-first thresholds are judgment calls.

## Individual Contributions

- **Tin Vu:** Participated in topic discussions, set up the team repository within the course GitHub organization, and created the checkpoint branch.
- **Jason Sauer:** Participated in topic discussions, coordinated the professor meeting, developed the research question, and prepared the data, R analysis, charts, and written findings with AI assistance.
