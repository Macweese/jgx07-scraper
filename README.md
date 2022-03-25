# OSRS Scraping Tool

Tool for scraping OldSchool RuneScape data.


#### [Download](https://github.com/Macweese/osrs-web-scrape/releases/download/v1.2.0/Crawler.rar "Download")[^1]


___


### What does this do?  
Automatically scrapes Jagex website for OldSchool RuneScape[^2], and procudes a JSON containing various data. The program will create a folder on your desktop named "Crawler Data" where the output files will be saved.


### Format
The contents of the output file are structured as; array followed by object with data points.
```
{
    "Server":
    [
        {worldObject},
        {worldObject}
    ],
    "Stats":
    {
        "abc":391
    }
}
```

See this [example](https://github.com/Macweese/osrs-web-scrape/blob/main/Example%2017-20-00%20UTC.json "Output file format") for reference on what the file contents look like.
___
### Notes
For this program to work you need to have Java 11 installed.

The output file will be named after the time of the execution in UTC time E.g. "2022-03-23 15-50-00 UTC.json".  
Each resulting file will be around 25kb in size. Trimming would only save about 1kb while making it unreadable, deemed not worth.

Only one instance of the software can run. Mistakingly or delibaretely trying to open another instance cannot occur due to mutex.  
The program will persist through failures/crashes and restart itself.  

__If you wish to close the program you will have to manually close it[^3] through task manager.__


[^1]: Bundled archive containing JRE and executable (recommended download). Otherwise, the executable alone is available for download [here](https://github.com/Macweese/osrs-web-scrape/releases/tag/v1.1.0).
[^2]: The program will automatically scrape every 10 minutes on the 10th minute mark. Which means it will execute every 0-, 10-, 20-, 30-, 40-, and 50th minute of the hour.
[^3]: Terminate the process named "Crawler.exe(32-bit)".
