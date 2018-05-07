Hey there. I'm Kathleen Oliver, a candidate for the combined MA/MLIS in Humanities Computing at the University of Alberta. 

# Projects

## Stormlight Archive Scraper
This scraper collects biographical data from each character entry in this fan-made wikia page: [Stormlight Archive Wikia](http://stormlightarchive.wikia.com/wiki/Category:Characters). The data is entered into multiple MySQL tables; first as single entity tables, then with another script, relationship tables between biographical data.  
For instance, the "gender" table holds each of the possible genders. This was the initial scrape and table build. Examples of Gender and Name tables below.  
```
+-----------+----------------+  
| gender_id | gender         |  
+-----------+----------------+  
|         1 | Male           |  
|         2 | Female         |  
|         3 | NULL           |  
|         4 | Male (assumed) |  
|         5 | Unknown        |  
+-----------+----------------+  

+---------+------------------------------+  
| name_id | name                         |  
+---------+------------------------------+  
|       1 | Abrial                       |  
|       2 | Abrobadar                    |  
|       3 | Abronai                      |  
|       4 | Adis                         |  
|       5 | Adolin Kholin                |  
|       6 | Adrotagia                    |  
|       7 | Aesudan Kholin               |  
|       8 | Alabet                       |  
|       9 | Aladar                       |  
|      10 | Alakavish                    |  
```

Then, the second script is run using the character ID from initial scrape to build the various relationship tables. Here is the `characters_gender` table.
```
+---------------------+--------------+----------------+
| character_gender_id | character_id | gender         |
+---------------------+--------------+----------------+
|                   1 |            1 | Male           |
|                   2 |            2 | Male           |
|                   3 |            3 | Male           |
|                   4 |            4 | Male           |
|                   5 |            5 | Male           |
|                   6 |            6 | Female         |
|                   7 |            7 | Female         |
|                   8 |            8 | Male           |
|                   9 |            9 | Male           |
|                  10 |           10 | Male           |
```

From this, we can ask MySQL how many characters are female, giving us data to fill the bar chart visualization. 
```
SELECT COUNT(character_id) AS NumberOfCharacters, gender FROM characters_gender WHERE gender = 'Female';
+--------------------+--------+
| NumberOfCharacters | gender |
+--------------------+--------+
|                106 | Female |
+--------------------+--------+
```

Here is the JSON encoded result, used for the bar chart visualizations:
`[{"NumberOfCharacters":"316","gender":"Male"},{"NumberOfCharacters":"106","gender":"Female"},{"NumberOfCharacters":"2","gender":"NULL"},{"NumberOfCharacters":"1","gender":"Male (assumed)"},{"NumberOfCharacters":"1","gender":"Unknown"}]`

You can find the entire GitHub page here: [Stormlight Archive Scraper](https://k-j-oliver.github.io/StormlightArchiveScraper/) found here.
