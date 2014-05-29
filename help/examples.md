##Search Examples##

###Filtering within facet###

Search for author: "Huchra, John" in the Astronomy database (default search).  
Opening the author filter you will get a list that includes "Geller, M" and "Illingworth, G."  If you want the articles in which "Geller, M." is a coauthor with "Huchra, John" you would simply click on the name "Geller, M." in the list.  
If you want the articles in which either "Geller, M." or "Illingworth, G" were coauthors you would click the boxes next to both of their names and choose "or" from the dropdown "apply" box.  
If you want the articles in which both "Geller, M." and "Illingworth, G" were coauthors you would click the boxes next to both of their names and choose "and" from the dropdown "apply" box.  (There should be zero results for this query!)  

###Stringing together a query###

You can string together any number of search terms, and by default they will be ANDed together, meaning the list of results will contain documents which match all the input search terms, e.g.

    author:"Huchra, John" title:redshift

will return all papers authored by John Huchra and which contain the word "redshift" in the title. The default operator can be changed from AND to OR by simply specifying it in the query:

    author:"Huchra, John" OR "cfa redshift survey"

Similarly, one can exclude documents containing a particular term by prepending a "-" sign to it:

    author:"Huchra, John" OR "cfa redshift survey" -title:2MASS

which will exclude papers containing "2MASS" in their title from the result list. If you want to search for the phrase "weak lensing" in just the Letters section of the Astrophysical Journal, you should use the query:

    "weak lensing" bibstem:"ApJ" page:"L*"

(and if you want to exclude the Letters section, you put a NOT or a '-' in front of the 'page' modifier).

###Selecting on properties###

One can string together different fields to get a list of results that match a set of defined properties.  

    author:"Huchra, John" property:openaccess property:refereed
        
returns a list of refereed open-access papers written by John Huchra.

###Citation queries###

To find citations about "black holes" that appeared in the Astrophysical Journal between 2000 and 2013:

    citations("black holes") bibstem:ApJ year:2000-2013
        
###Reference queries###
        
To find references to books in the article 1999RvMPS..71..180H:

    references(bibcode:1999RvMPS..71..180H) property:book
