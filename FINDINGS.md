# Massachusetts Findings: Tax-Credit Properties Reaching Year 30 (2027–2031) and Renter Cost Burden

**Research question.** Which Massachusetts neighborhoods have both many affordable apartments in tax-credit properties reaching 30 years in service between 2027 and 2031 and a high share of renters already spending at least 30% of their income on rent and utilities?

## Data and processing

HUD's LIHTC property file lists 136 Massachusetts records placed in service in 1997–2001. Together they report 10,869 low-income units. Seven records lack usable coordinates (six have no coordinates and one has a low-quality geocode). They are listed in `output/records_without_usable_coordinates.csv` and include Orchard Park I, IIIA and IIIB in Roxbury and Neighborhood Homes in Springfield.

The remaining 129 records fall in 113 census tracts. Every tract matched the 2020–2024 ACS file. The data checks found one missing unit count, no negative counts, no repeated HUD IDs, and no two records sharing a street address. One tract has no unit count, which leaves 112 tracts for the chart.

## Main result: where the two conditions overlap

![Rent burden vs expiring units](figures/fig1_burden_vs_expiring_units.png)

Tracts with properties approaching Year 30 are already more stretched than the typical Massachusetts tract. Their median renter cost-burden share is 55.5%, compared with a statewide tract median of 51.5%. Within this group, however, the number of expiring units and the burden share are essentially unrelated (r = 0.05). The tracts with the most expiring units are therefore not automatically the most burdened, and both measures are needed to set priorities.

Sixteen tracts are at or above the statewide burden median and in the top quarter for expiring units (118 or more). Together they hold 3,919 low-income units, about 37% of the units in the matched tracts. The largest are:

| Tract | City | Property | Units reaching Year 30 | % renters burdened |
|---|---|---|---:|---:|
| 25025081001 | Boston (Mission Hill) | Mission Park | 620 | 66.0 |
| 25013801101 | Springfield | Chestnut Park Apts | 412 | 63.5 |
| 25017310102 | Lowell | River Place Towers | 362 | 61.0 |
| 25025080401 | Boston/Roxbury | Grant Manor; Orchard Park Off Site I; Ruggles Assisted Living | 258 | 63.0 |
| 25025081302 | Roxbury | Academy Homes I; Wardman Apts | 238 | 67.3 |
| 25027731002 | Worcester | Coes Pond Village | 227 | 61.2 |
| 25021400900 | Brookline | Village at Brookline | 217 | 61.7 |
| 25025010405 | Boston | Symphony Plaza West | 216 | 54.9 |

The full list of 16 is in `output/priority_tracts.csv`. The rest are in Springfield, North Adams, Gardner, Boston (Symphony Plaza East), Lynn, Greenfield, Lowell and Fall River.

## Follow-up: total units versus units per 100 renter households

![Rank shift](figures/fig2_followup_rank_shift.png)

Overall, the two rankings are similar (Spearman ρ = 0.89), but the top of the list changes. Once the size of the rental market is taken into account, smaller markets in central and western Massachusetts move up. Greenfield (Leyden Woods) moves from 23rd to 2nd with 49 expiring units per 100 renter households and 60% burden. Gardner (Olde English Village) moves from 17th to 4th with 41 per 100 and 69% burden. Both are in the review-first group, and the per-100 view shows how much of each town's rental market they represent.

Brockton (Davis Commons) jumps from 15th to 1st, but its 76 units per 100 renters comes from a small renter base of 263 households (margin of error ±103) and low measured burden (21%). It reflects a small denominator more than a high-need neighborhood. The larger Boston and Worcester tracts move down: Mission Park drops from 1st to 10th, and both Worcester tracts leave the top 10.

## Cross-check: CEDAC Expiring Use Inventory (February 2025)

Every flagged property we checked appears in CEDAC's inventory. CEDAC tracks Section 8 project-based rental assistance contracts, so its dates are a second clock alongside LIHTC Year 30:

* **Symphony Plaza West (Boston):** its Section 8 contract is listed to expire December 31, 2027, inside the Year-30 window. It faces both clocks at once and is the clearest property to review first.
* **Mission Park (Boston):** the inventory lists a contract date of March 31, 2025, which has already passed, so its renewal status should be confirmed.
* **Later contract dates:** Academy Homes (2033), Lafayette Place (2034), Leyden Woods and Olde English Village (both 2035) all have contracts running beyond Year 30.
* **No Section 8 date listed:** River Place Towers, Coes Pond Village, Mission Main and Holyoke Farms. Their affordability depends more heavily on the tax-credit agreement itself.

The rows were transcribed from the PDF in `data/cedac_crosscheck.csv` and should be spot-checked against the original.

## Limitations

Reaching Year 30 marks a date to check the affordability agreement, not a confirmed expiration. Many Massachusetts properties have longer agreements, and several flagged sites (Mission Main, Orchard Park, Academy Homes) are redevelopments with additional public restrictions.

ACS tract estimates carry wide margins of error, which matters most for small tracts like Brockton's.

Seven records could not be located and are excluded.

The "review first" thresholds (statewide median burden and top-quarter units) are judgment calls; other cutoffs would change the edges of the list.
