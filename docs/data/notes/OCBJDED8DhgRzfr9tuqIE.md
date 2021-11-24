
Documentation regarding the FRED Data. Split into FREDMD and FREDQD sections.

## FREDMD

Data cleaning issues:
- ANDENOx = New Orders for Nondefense Capital Goods, starts from 1968 03
- TWEXMMTH = Trade Weighted US DOllar Index , starts from 1973-02
- UMCSNETx = Consumer Sentiment Index, starts from 1978 02
- ACOGNO = New orders for Consumer Goods, starts from 1992 02
- VXOCLSx = VXO index, starts from 1962-07

ISM series were discontinued after 2016 after a falling out between FRED and ISM. These were kept in the dataset for legacy reasons, but present a missing data problem.
The ISM series are:
- ID 19 NAPMPI
- ID 49 NAPMEI
- ID 60 NAPM
- ID 61 NAPMNOI
- ID 62 NAPMSDI
- ID 63 MAPMII
- ID 112 NAPMPRI

Some important series (perhaps keep in mind for thresholding)

Inflation related variables
- WPSFD49207 = PPI of finished goods
- CPIAUCSL = CPI of all items

Recession related variables

- RPI = real personal income
- INDPRO = Industrial Production
- UNRATE = unemployment rate
- UEMPMEAN = mean duration of unemployment
- HOUST = Housing Starts
- FEDFUNDS = effective federal funds rate
- S.P.500 = SP500 index
- VXOCLSx = VXO index
## FREDQD

Quarterly version of FRED data, much higher N dimension, much lower T dimension

Missing Data Issues:


Important Series (possible future thresholding):

- 