# DRC Ebola confirmed-case trajectories

This repository contains the data used to compare how quickly laboratory-confirmed Ebola cases accumulated during three outbreaks in the Democratic Republic of the Congo (DRC):

- **2026:** the ongoing Bundibugyo ebolavirus outbreak
- **2018–20:** the largest recorded Ebola outbreak in DRC, caused by Zaire ebolavirus
- **2012:** the previous recorded Bundibugyo ebolavirus outbreak in DRC

The comparison uses days since officials announced each outbreak, rather than calendar dates. The 2026 series is current through **July 21, 2026**, when INSP Situation Report 68 reported **2,536 confirmed cases**.

## Files

- [`data/source-data.csv`](data/source-data.csv) is the reusable long-form dataset. Each row is one published observation and includes its source.
- [`data/datawrapper.csv`](data/datawrapper.csv) is the wide, chart-ready file used in Datawrapper. Blank cells mean no confirmed-case total was published for that day.
- [`DATA_DICTIONARY.md`](DATA_DICTIONARY.md) defines every column.
- [`METHODS.md`](METHODS.md) explains the outbreak selection, date alignment, transformations, and important limitations.

## Sources

- **2026:** [DRC National Institute of Public Health Situation Report 68](https://insp.cd/wp-content/uploads/2026/07/SitRep_MVE_RDC_N%C2%B0_68_21-07-2026.pdf); [INSP situation-report data compiled by INRB-UMIE](https://github.com/INRB-UMIE/BDBV2026-Data); and the [WHO outbreak notice](https://www.who.int/emergencies/disease-outbreak-news/item/2026-DON602)
- **2018–20:** [DRC Ministry of Health and WHO reporting distributed by HDX](https://data.humdata.org/dataset/ebola-cases-and-deaths-drc-north-kivu); and the [WHO outbreak notice](https://www.who.int/emergencies/disease-outbreak-news/item/4-august-2018-ebola-drc-en)
- **2012:** [WHO Disease Outbreak News reports](https://www.who.int/emergencies/disease-outbreak-news/item/2012_10_26-en). The long-form file links the specific WHO report used for each observation.

## What this data does — and does not — show

The files contain **confirmed cases only**. They exclude probable and suspected cases so that the three lines use the same, relatively strict measure. The true number of infections was likely higher.

The chart does not estimate values for dates without a published total. The only dotted segment is the 2012 connector between the last contemporaneous report and a later retrospective final tally; it signals that the timing of the additional confirmations is unknown.

These three outbreaks were selected for editorial comparison, not as a complete history of Ebola in DRC. Anyone reusing the data should cite the original sources as well as this compilation. Corrections are welcome through GitHub issues.
