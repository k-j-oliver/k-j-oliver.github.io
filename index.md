Hey there. I'm Kathleen Oliver, a candidate for the combined MA/MLIS in Humanities Computing at the University of Alberta. 

# Projects

## Stormlight Archive Scraper
This scraper collects biographical data from each character entry in this fan-made wikia page: [Stormlight Archive Wikia](http://stormlightarchive.wikia.com/wiki/Category:Characters). The data is entered into multiple MySQL tables; first as single entity tables, then with another script, relationship tables between biographical data. 
For instance, the "gender" table holds each of the possible genders. This was the initial scrape and table build. Examples of Gender and Name tables below.  
![GenderTable screenshot](https://github.com/k-j-oliver/k-j-oliver.github.io/blob/master/GenderTable.png) ![NameTable screenshot](https://github.com/k-j-oliver/k-j-oliver.github.io/blob/master/NameTable.png)

Then, the second script is run using the character ID from initial scrape to build the various relationship tables. Here is the `characters_gender` table.
 ![CharacterGenderTable screenshot](https://github.com/k-j-oliver/k-j-oliver.github.io/blob/master/CharactersGenderTable.png)

From this, we can ask MySQL how many characters are female, giving us data to fill the bar chart visualization. 
![NumberOfCharactersGender screenshot](https://github.com/k-j-oliver/k-j-oliver.github.io/blob/master/NumberOfCharactersGender.png)

Here is the JSON encoded result, used for the bar chart visualizations:
`[{"NumberOfCharacters":"316","gender":"Male"},{"NumberOfCharacters":"106","gender":"Female"},{"NumberOfCharacters":"2","gender":"NULL"},{"NumberOfCharacters":"1","gender":"Male (assumed)"},{"NumberOfCharacters":"1","gender":"Unknown"}]`

You can find the entire GitHub page here: [Stormlight Archive Scraper](https://k-j-oliver.github.io/StormlightArchiveScraper/) found here.
