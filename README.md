# OSRS Scraping Tool

Tool for scraping OldSchool RuneScape data.


#### [Download](https://github.com/Macweese/jgx07-scraper/releases/tag/v2.0.1 "Download")


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

### Information

<details>
  <summary>What do the elements/stats in the output mean?</summary><br>


  #### Servers (JSONObject)     
  These represent each game world (server) and their attributes at the time of data collection.  

  #### • Stats
   1. <b>Servers</b>   
      In this field 'servers' refers to total number of public servers, these may not always be accessible E.g. Offline, Closed Beta etc. 
   2. <b>Servers Online</b>  
      These are servers which players may connect to.
   3. <b>'Free-To-Play' & 'Members'</b>  
      Total number of players playing on respective world types.
   4. <b>US, EU, UK, AU</b>  
      Total number of players playing on respective world regoins.
   5. <b>What do the remaining elements mean?</b>  
      The number of players playing on worlds with respective activity, and region if applicable.
   4. <b>Why are the numbers for DMM Seasonal & DMM Tournament 0? And why are they included?</b>  
      First Q: Temporary game mode which is not always availalble. Second Q: Why not.  
  <br>
</details>

Currently stats do not support other activities such as Beta worlds, Leagues (Twisted League, Trailblazers Leagues, Shattered Relics),  
special world events (Battle Royale) or other.  
However, all public worlds will be visible as elements in `Servers[]`.  

Linux, MacOS and other OS may experience general issues or inability to run the application.


___
### Notes
For this program to work you need to have Java 11 installed.

The output file will be named after the time of the execution in UTC time E.g. "2022-03-23 15-50-00 UTC.json".  
Each resulting file will be around 25kb in size.

Only one instance of the application can run due to mutex. 

__If you wish to close the program you will have to manually close it[^3] through task manager.__


[^2]: The program will automatically scrape every 10 minutes on the 10th minute mark. Which means it will execute every 0-, 10-, 20-, 30-, 40-, and 50th minute of the hour.
[^3]: Terminate the process named "Crawler.exe(32-bit)".
