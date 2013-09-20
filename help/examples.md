Examples:

##Filtering within facet##

Search for author: "Huchra, John" in the Astronomy database (default search).  
Opening the author filter you will get a list that includes "Geller, M" and "Illingworth, G."  If you want the articles in which "Geller, M." is a coauthor with "Huchra, John" you would simply click on the name "Geller, M." in the list.  
If you want the articles in which either "Geller, M." or "Illingworth, G" were coauthors you would click the boxes next to both of their names and choose "or" from the dropdown "apply" box.  
If you want the articles in which both "Geller, M." and "Illingworth, G" were coauthors you would click the boxes next to both of their names and choose "and" from the dropdown "apply" box.  (There should be zero results for this query!)  


##Stringing together a query##

You can string together any number of search terms, and by default they will be ANDed together, meaning the list of results will contain documents which match all the input search terms, e.g.

    author:"Huchra, John" title:redshift

will return all papers authored by John Huchra and which contain the word "redshift" in the title. The default operator can be changed from AND to OR by simply specifying it in the query:

    author:"Huchra, John" OR "cfa redshift survey"

Similarly, one can exclude documents containing a particular term by prepending a "-" sign to it:

    author:"Huchra, John" OR "cfa redshift survey" -title:2MASS

which will exclude papers containing "2MASS" in their title from the result list.
