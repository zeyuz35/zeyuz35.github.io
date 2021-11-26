---
id: jtZSk246bVVDfJy6cdpS1
title: Macroeconomic Datasets
desc: ''
updated: 1637882341092
created: 1635213694758
bibliography: [references.bib]
reference-section-title: References
---

This document contains a compilation of various macroeconomic datasets, and notes for any details that are necessary.

Specific details about missing data (important!) etc are documented.

## Checklist

[x] FREDMD
[] FREDQD
[x] LCDMA
[x] LCMMAQ
[x] UKMD
[] AUMD

## US Data

A note on transformation codes (from Ben).

The SW and FREDMD tcodes are completely consistent with one another, despite what Ben suspected.

However, some of these codes are controversial(?) in the literature. E.g. Unemployment should be kept level, FEDFUND should be kept level.
### Stock and Watson

Stock and Watson pioneered the collection of macroeconomic datasets, and this is a pre-cursor/inspiration for the FRED databases later on. 

Although considered to be outdated, they remain popular even among newer papers, in order for authors to reconcile/compare their results to what has been previously done.

The following two are the most revelant ones that appear in the literature.

SW2005
SW2009

### FRED-MD (US)

[@mccracken_fred-md_nodate]

The most well known dataset, and the focus of many papers. 

The implementation of this is in FREDMD.R. This currently uses the fbi package as a pseudo-wrapper for applying the transformations, but this is not strictly necessary.

### Missing Data

- ANDENOx = New Orders for Nondefense Capital Goods, starts from 1968 03
- TWEXMMTH = Trade Weighted US DOllar Index , starts from 1973 02
- UMCSNETx = Consumer Sentiment Index, starts from 1978 02
- ACOGNO = New orders for Consumer Goods, starts from 1992 02
- VXOCLSx = VXO index, starts from 1962 07

ISM series were discontinued after 2016 after a falling out between FRED and ISM. These were kept in the dataset for legacy reasons, but present a missing data problem.
The ISM series are:
- ID 19 NAPMPI
- ID 49 NAPMEI
- ID 60 NAPM
- ID 61 NAPMNOI
- ID 62 NAPMSDI
- ID 63 MAPMII
- ID 112 NAPMPRI
## FRED-QD (US)



## AU-MD (Australia)

[@hartigan_factor_2020]

Luke Hartigan's website provides an AUMD dataset, which though not continously updated, is quite large and available.

## UK-MD (UK)

Can Machine Learning catch the COVID19 recession?


## CAN-MD (Canada)

CAN MD 

[@fortin-gagnon_large_nodate].

## Wharton Data Research Services (WRDS)

## Thomson Reuters DataStream

## Ludvigson

There is an old macro + financial dataset; however, this is consdiered to be very outdated.

The most up to date dataset is macro + financial, as described in the dat appendix. Unexcitingly, the macro dataset is just FREDMD. 

However, the financial dataset is a mish mash of Kenneth French and CRSP data. This unfortunately does not seem to be provided at all, though there are instructions for how one would be able to construct it themselves.

Presumably, this is because CRSP has some strict rules on sharing the data.

https://www.sydneyludvigson.com/data-and-appendixes

For more details, see [[Datasets.JLN_financial]].

## Fama French

Fama French factors and portfolios are available from Kenneth French's website:

https://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html

However, these are all offered in the form of excel files which are notorious to work with. 

See [[Datasets.Fama_French]] for more info.

## Notes on Transformations

Transformations do matter a lot for macroeconomic analysis, though this is arguably less pronounced for large dimensional methods, such as PCA, which are inherently robust.

Some potentially unreasonable decisions are:

- keeping unemployment or interest rates in levels rather
than applying first differences, or vice versa
