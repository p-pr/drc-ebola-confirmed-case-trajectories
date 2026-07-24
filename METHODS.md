# Methods and processing notes

## Why these three outbreaks

The chart is a focused editorial comparison, not a census of all Ebola outbreaks in DRC.

- **2018–20** gives readers the most important domestic benchmark: it was the largest Ebola outbreak recorded in DRC.
- **2012** is the closest virological comparison in the country: like the current outbreak, it was caused by Bundibugyo ebolavirus.
- **2026** is the ongoing outbreak the chart is designed to explain.

The different virus species matter. The chart compares the pace of confirmed cases; it does not imply that the outbreaks had the same biology, geography, surveillance, or response conditions.

## Measure

The dataset uses cumulative **laboratory-confirmed cases**. Probable and suspected cases are excluded. This gives the three series a clearer common definition, but it understates the likely number of infections and can still be affected by testing access, reporting delays, and retrospective corrections.

## Day zero

Each observation date was converted into the number of calendar days since officials announced the outbreak:

| Outbreak | Day-zero date | Basis |
|---|---:|---|
| DRC 2026 | 2026-05-15 | DRC declared the outbreak; WHO reports that eight samples had tested positive. |
| DRC 2018–20 | 2018-08-01 | DRC notified WHO of the outbreak. |
| DRC 2012 | 2012-08-17 | DRC Ministry of Health notified WHO of the outbreak. |

`days_elapsed` is the integer difference between `observation_date` and `announcement_date`.

The INRB-UMIE processed 2026 file dates the first eight confirmations to May 14, when the samples were analyzed. For chart alignment, those eight cases are placed on May 15, the official outbreak-declaration date. All later 2026 observations retain their source dates.

## Transformations

1. Extract cumulative confirmed-case observations from the three source series.
2. Standardize outbreak labels and dates.
3. Calculate `days_elapsed` from the day-zero date above.
4. Keep one row per published observation in `source-data.csv`.
5. Pivot the observations into one outbreak column per series for `datawrapper.csv`.
6. Preserve missing dates as blank cells. No daily case values are interpolated.

The 2026 series includes 2,905 confirmed cases on July 22 from INSP Situation Report 69. The report says the large cumulative increase mainly reflects the integration of harmonized provincial databases and does not represent only cases reported in the preceding 24 hours. The 2018–20 chart is limited to the first 100 elapsed days. The processed file extends to day 101 only to place the retrospective 2012 endpoint.

## The 2012 dotted line

The last contemporaneous WHO report with a confirmed/probable breakdown was on day 68 and listed **35 confirmed cases**. A later WHO retrospective summary gives a final total of **38 confirmed cases** when the outbreak ended on day 101.

The entire 2012 line is dotted because only a few confirmed-case totals were published. Through day 68, it connects dated official observations and does not estimate daily case counts.

WHO does not publish the dates on which the final three cases were confirmed. The chart therefore places only two values in the separate `DRC 2012 — timing unknown` column: 35 on day 68 and 38 on day 101. Both 2012 columns are styled as dotted blue lines in Datawrapper so they appear as one series. The post-day-68 segment connects two known totals; it does not show when the additional confirmations occurred.

Contemporaneous end-of-outbreak reporting and the later WHO retrospective summary differ on the overall case count, and the contemporaneous report does not provide a final confirmed/probable split. For consistency with the chart's confirmed-only measure, the dataset uses the retrospective total of 38 and labels it separately.

## Source-specific limitations

- **2026:** The INRB-UMIE file compiles official INSP situation reports. The July 21 and July 22 totals were added directly from INSP Situation Reports 68 and 69, respectively.
- **2018–20:** The HDX dataset includes a second header row containing Humanitarian Exchange Language tags. That row was excluded. The chart begins with 13 confirmed cases on day 2; the initial WHO notice described four GeneXpert-positive samples as presumptive, so they are not treated as confirmed in this series.
- **2012:** The values were manually transcribed from official WHO Disease Outbreak News reports. Sparse reporting means the solid line contains only published observation dates.
