
## Macroeconomic Datasets Compilation

This document contains a compilation of various macroeconomic datasets, and notes for any details that are necessary 

This is mostly because the documentation sources for all of these is messy and all over the place, are constantly updated, and are overall hard to keep track of in one place.

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

Luke Hartigan's website provides an AUMD dataset, which though not continously updated, is quite large and available.

## UK-MD (UK)

Phillipe Coulombe

Can Machine Learning catch the COVID19 recession?


## CAN-MD (Canada)

CAN MD 
