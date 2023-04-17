+++
title = "Excel - Identify Cell With Highest Value"
date = "2023-03-06"
author = "JB"
tags = ["Excel"]
categories = ["Spreadsheets"]
+++

### Finding Cell/Element With Highest Value In Multiple Columns Among Repeated Values

I know: That's a lot of words!  

Say you have some data with:

- zip code
- house district
- the percentage of the zip code *within* the house district

and you'd like to figure out which house district has the *most* of each zip code.

![sample zip code mess](/excel_zip_hd_sample_screenshot.png)

If all the zip codes only perfectly intersected just two HDs, you could handle that with an easy enough formula. But zip codes are messier than Boston subway cars. I could go on and on about zip codes being terrible for data work, and if you know me I already have, but Frank does it better at his excellent [gis blog](https://atcoordinates.info/2020/05/11/the-trouble-with-zip-codes-solutions-for-data-analysis-and-mapping/). With actual data, like this long list of NY zip codes, you'll often find many more than two candidates. 

In the image below, we would only want to keep the 78.7% row of the 10510 series and the 89.3% row from the 10514 series.

![sample rows to keep](/excel_rows_to_keep.png)

Usually, I'd reach for python here but many people are already comfortable with spreadsheets and this certainly can be accomplished in Excel, Google Sheets, or the criminally underrated [LibreOffice Calc](https://www.libreoffice.org/discover/calc/). The formula below in cell D2 will do just what we need.

```
=(C2=MAX(IF(A$2:A$3000=A2,C$2:C$3000)))*(SUM(IF(A$2:A2=A2,IF(C$2:C2=C2,1)))=1)
```

You can easily adapt this to your data **or** adapt your column order to fit the formula. 

>:bulb: Note that to the left of the ```*``` you will need to adjust the absolute row counts in ```A$3000``` and ```C$3000``` to match your own row count. For example, if your spreadsheet's data went down to row 5,000 instead of row 3,000, your formula would instead look like this:

 ```
=(C2=MAX(IF(A$2:A$5000=A2,C$2:C$5000)))*(SUM(IF(A$2:A2=A2,IF(C$2:C2=C2,1)))=1)
```

The formula will put a '1' next to the maximum column C value for each unique set of values in column A and a '0' next to values that are lower. 

![excel max](/excel_max.png)

Now you can simply filter column D to the rows with '1' and volia!