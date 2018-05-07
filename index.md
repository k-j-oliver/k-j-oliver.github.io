Hey there. I'm Kathleen Oliver, a candidate for the combined MA/MLIS in Humanities Computing at the University of Alberta. 

# Projects

## Stormlight Archive Scraper
This scraper collects biographical data from each character entry in this fan-made wikia page: [Stormlight Archive Wikia](http://stormlightarchive.wikia.com/wiki/Category:Characters). The data is entered into a MySQL database in multiple tables; first as single entity tables, then with another script, relationship tables between biographical data. For instance, the "gender" table holds each of the possible genders. This was the initial scrape and table build. Then, the second script is run to collect the character's name and gender, building the relationship table. From this, we can ask MySQL how many characters are female, giving us data to fill the bar chart visualization. 

[Stormlight Archive Scraper](https://k-j-oliver.github.io/StormlightArchiveScraper/) found here.
