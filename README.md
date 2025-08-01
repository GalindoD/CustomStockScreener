# Overview
The purpose of this repo is to build a Stock Screener for Good Companies that have good fundamentals, with a value investing approach. Then Valuating these companies and finding underpriced ones. Finally, using simple trading indicators to singnal when to enter a position. 

## Valuation ipynb
This notebook calculates key metrics of a particular stock. It fetches information online and creates custom Datafrems to aid in the investing decisions. The four main information tables fetches are the Income Statement, Balance Sheet, Cash Flow Statement and the historic valuation metrics.
Then, two tables are calculated and a suggested purchase price. 

### Examples of Dataframes:
![Example of online fetched Dataframe](https://github.com/GalindoD/CustomStockScreener/blob/7228543598ada60c7fa7abbe0f5c68ce22148e8b/Fetched%20DF2.png)

![Example of calculated Dataframe](https://github.com/GalindoD/CustomStockScreener/blob/7228543598ada60c7fa7abbe0f5c68ce22148e8b/ROIC%20DF.png)

![Example of another calculated Dataframe](https://github.com/GalindoD/CustomStockScreener/blob/7228543598ada60c7fa7abbe0f5c68ce22148e8b/GrowthDF.png)

### Example of calculated Purchase Price
![Example of Output Suggeted Buy Price](https://github.com/GalindoD/CustomStockScreener/blob/7228543598ada60c7fa7abbe0f5c68ce22148e8b/BuyPrice.png)


## The following serves as a guide and notes for the project:
First: Get a list of good companies: (all the info for 10 years ideally, parameters from Rule 1 Investing and One up on Wall Street)
The code should screen through all US stocks, and get a list of good companies based on key financial metrics:
· ROIC > 10%
· Revenue Growth > 10%
· EPS Growth > 10%
· Equity Book Value Growth > 10%
· FCF Growth > 10%
· Total Long Term Debt / FCF < 3
Then: With the list of good companies, a calculation for a quick and simple valuation must be made:
· ManPrice = (  (EPSr1*(1+(  GR  /100))**(10) *  PE      )/(1.15**10) ) / 2
This is only an estimate of future price, based on current valuation and estimated growth rate. Then it is divided by two, just to have a Margin of Safety
Finally: With the now hopefully small list, a simple technical analysis:
· MA: The stock must be trading above the 10 day MA and 40 MA
· MACD: The MACD indicator should be set to 8, 19 and signal 9
· Trading must be done on a weekly or 5d basis

On the previous implementation a resulting DataFrame for analysis was like this:
```
			10yr Compound	10yr YOYavg	5yr YOYavg	1 yr YOY
ROIC 			X		X		X		X
Equity growth		X		X		X		X
EPS Growth 		X		X		X		X
Revenue Growth		X		X		X		X
FCF Growth		X		X		X		X
Operating Cash Growth	X		X		X		X
Shares (number)		X		X		X		X
```

Also the list for step 1 on the previous implementation is:
'ADBE',
 'AEIS',
 'ALRM',
 'AMAT',
 'AMD',
 'AMZN',
 'APPF',
 'ASML',
 'ATVI',
 'BFC',
 'BLDR',
 'CBNK',
 'CRMT',
 'CRUS',
 'ENTG',
 'ETSY',
 'EXPD',
 'FB',
 'FCNCA',
 'FFIN',
 'FMNB',
 'GGAL',
 'GMAB',
 'GOOG',
 'GOOGL',
 'HEAR',
 'HIBB',
 'IDXX',
 'IMXI',
 'INTU',
 'INVA',
 'IRBT',
 'IRCP',
 'JYNT',
 'KNSL',
 'LGIH',
 'LMAT',
 'MASI',
 'MKSI',
 'MKTX',
 'MORN',
 'MPWR',
 'MSFT',
 'MVBF',
 'NBN',
 'NFLX',
 'NVDA',
 'NVMI',
 'OBCI',
 'OLLI',
 'ORLY',
 'PCTY',
 'PDEX',
 'POOL',
 'QDEL',
 'QLYS',
 'SNFCA',
 'SPSC'
