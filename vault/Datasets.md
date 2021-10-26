---
id: jtZSk246bVVDfJy6cdpS1
title: Datasets
desc: ''
updated: 1635213707030
created: 1635213694758
---

# Macroeconomic Datasets Compilation

This document contains a compilation of various macroeconomic datasets, and notes for any details that are necessary 

This is mostly because the documentation sources for all of these is messy and all over the place, are constantly updated, and are overall hard to keep track of in one place.

Specific details about missing data (important!) etc are documented.

## Stock and Watson

Stock and Watson pioneered the collection of macroeconomic datasets, and this is a pre-cursor/inspiration for the FRED databases later on. 

## FRED-MD (US)

The most well known dataset, and the focus of many papers. 

The implementation of this is in FREDMD.R. This currently uses the fbi package as a pseudo-wrapper for applying the transformations, but this is not strictly necessary.

### Missing Data

ANDENOx = New Orders for Nondefense Capital Goods, starts from 1968 03
TWEXMMTH = Trade Weighted US DOllar Index , starts from 1973 02
UMCSNETx = Consumer Sentiment Index, starts from 1978 02
ACOGNO = New orders for Consumer Goods, starts from 1992 02
VXOCLSx = VXO index, starts from 1962 07



## FRED-QD (US)



## AU-MD (Australia)



## UK-MD (UK)

## CAN-MD (Canada)