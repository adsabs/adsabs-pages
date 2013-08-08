## ADS 2.0 Preview

Our 
[ADS 2.0 Preview page](http://labs.adsabs.harvard.edu/adsabs/)
provides a sneak peek at the search engine and underlying database
that we are putting together to upgrade the ADS infrastructure to new 
technologies.  Please keep in mind that this new system makes use
of a separate database than ADS classic, so while we will do our best
to keep the two in sync, at any point in time
it may be a few days to a few weeks behind in terms of updates.

We expect things to change fairly rapidly, with more features added
on a regular basis based on our continuing development and the 
feedback received from users.  

Here is a brief introduction to help get people started
on the new interface.

### Search

We think that searching should be straightforward, and one input box
plus a few knobs should be plenty to get you started.  If you just type
in a few words, we'll return all documents that contain all of the terms
you typed in, whether they appear in the author list, title, abstract, or 
full-text of the documents we have.  Need to be more specific?  You can 
easily limit your search by requiring that the input terms appear in 
a particular field such as title or author list.  We provide a few
shortcuts to help the user memorize the syntax that our search engine
uses for fielded searches.  

Looking for a person? Click on the "Author" link on top of the search box and enter his or her name
in the form "Lastname, Firstname".  So if you are looking for John Huchra's papers
you would type:

    author:"Huchra, John"

which will return all papers where "Huchra, John" (or any proper abbreviation of the name)
is listed as an author.  To search for a phrase (a sequence of words) simply enclose the words in double quotes.
For example:

    "cfa redshift survey"

will return all papers which mention the CfA redshift survey in their text.

You can string together any number of search terms, and by default
they will be ANDed together, meaning the list of results will contain documents which match
all the input search terms, e.g.

    author:"Huchra, John" title:redshift

will return all papers authored by John Huchra and which contain the word "redshift" in the title.
The default operator can be changed from AND to OR by simply specifying it in the query:

    author:"Huchra, John" OR "cfa redshift survey"

Similarly, one can exclude documents containing a particular term by prepending a "-" sign 
to it:

    author:"Huchra, John" OR "cfa redshift survey" -title:2MASS

which will exclude papers containing "2MASS" in their title from the result list.

### Filtering your results

The list of results from a query includes a list of filters which allow the user to further narrow 
down and explore the set of papers.  Narrowing results is straightforward: find an item on the
list of filters which you want to use as a selection criterion and click on it to 
add the corresponding term to the query.  Adding and removing filters is simple, has
immediate effect, and is reflected in the list of parameters displayed under the search box.

Some of the filters may include a hierarchy.  For instance, author names are grouped under their
canonical form ("Lastname, F").  Clicking on the plus sign next to them will display a
list of author name variations which have been conflated into the single top-level entry.
This allows one to refine the search further at a higher granularity level.



