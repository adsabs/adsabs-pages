##Searching the ADS##

Our new one box search allows for you to search for a combination of author, title, year, or keywords.  By default the query terms will be searched for in the article metadata as well as the full-text contents.  To restrict the search to a particular field, simply prepend the field name to the term being searched for. Identifiers such as bibcodes, arXiv IDs and DOIs are recognized as well. 
Some example searches:

 * "weak lensing"
 * author:"huchra, j"
 * "dark matter" -LHC
 * title:"QSO" year:1995-2000
 * arXiv:1012.5859
 * doi:10.1086/345794
 * bibcode:2003AJ....125..525J
 
Unfielded searches may give more results than one would like since one would be searching the whole body of ADS records.  A fielded query will result in a better result list.  

Fielded searches can be made by prepending the search terms with the appropriate field keyword.  A list of the most common fields is displayed above the search box and clicking on each one of them will pre-generate the proper search syntax for you.  Here is the list as currently implemented:

Field Name   | Search Field Syntax         | Example                 | Notes                                      |
------------ | --------------------------- | ----------------------- | ------------------------------------------ |
Author       | author:"Last, F"            | author:"huchra, j"      | using author initial works fine            |
             | author:"Last, First [...]"  | author:"huchra, john p" | stricter author search (recommended)       |
First Author | author:"^Last, F"           | author:"^huchra, j"     | limit the search to first-author papers    |    
Abstract     | abs:"phrase"                | abs:"dark energy"       | search for word or phrase in abstract      |
Year         | year:YYYY                   | year:2000               | require specific publication year          |
             | year:XXXX-YYYY              | year:2000-2005          | require publication date range             |
Publication  | bibstem:"abbrev"            | bibstem:ApJ             | limit search to a <a href="http://adsabs.harvard.edu/abs_doc/journal_abbr.html">specific publication</a> |
Fulltext     | full:"phrase"               | full:"gravitational waves" | search for word or phrase in fulltext   |

You can string together any of the search terms to develop a query.  By default search terms will be combined using AND as the default boolean operator, but this can be changed by explicitly specifying OR beween them.  Similarly one can exclude a term by prepending a "-" sign to it.  Multiple search words or phrases may be grouped in a fielded query by enclosing them in parenthesis.  Some examples:

    abs:(QSO "dark energy")                 # _finds papers containing both "QSO" and "dark energy" in their abstract_
    abs:(QSO OR "dark energy")              # _finds papers containing either "QSO" or "dark energy in their abstract_
    author:"huchra, j" -title:2mass         # _finds papers by "J. Huchra" but excludes ones with "2mass" in their title_
    
[See more examples.](examples.md#stringing-together-a-query)

In addition to the search fields listed above, you may also use the following options to limit your search.  Please note that with exception of the bibcode not all fields are necessarily populated for all records.

Field Name   | Search Field Syntax         | Example                 | Notes                                      |
------------ | --------------------------- | ----------------------- | ------------------------------------------ |
Bibcode      | bibcode:adsbib              | bibcode:2003AJ....125..525J | finds a specific record using the <A HREF="http://adsabs.harvard.edu/abs_doc/help_pages/data.html#bibcodes">ADS bibcode</A> |
arXiv ID     | arXiv:arxivid               | arXiv:1108.0669         | finds a specific record using its arXiv id
DOI          | doi:DOI                     | doi:10.1086/345794      | finds a specific record using its digital object id |
Affiliation  | aff:"phrase"                | aff:"harvard"           | search for word or phrase in affiliation field |
Title        | title:"phrase"              | title:"weak lensing"    | search for word or phrase in title field   |
Keywords     | keyword:"phrase"            | keyword:sun             | search publisher- or author-supplied keywords |
Database     | database:DB                 | database:astronomy      | limit search to either astronomy or physics | Properties   | property:type               | property:openaccess     | limit search to article with specific attributes (see below) |

The "properties" search field allows one to restrict the search results to papers which possess a particular property.  The allowed properties currently include:

Property flag  | Selection                |
-------------- | ------------------------ |
refereed       | refereed papers only     |
eprint         | arXiv eprints            |
catalog        | astronomical catalogs (e.g. Vizier)          |
openaccess     | open access records      |
software       | ASCL software packages   |


 * **properties**: are specific attributes of a record that can be searched.  Available properties are:  article, refereed, not_refereed, inproceedings, openaccess, nonarticle, eprint, book, proceedings, catalog, software.  The syntax for this search is property:property (e.g. property:book or property:refereed) [**EXAMPLE**](examples.md#property-strings)
 * **classic_relevance (or cr)**:  allows you to search ADS2.0 with the default ranking paramters of ADS classic
 * **topn**: allows you to limit your results to the topn (n=number) returned
 * **citations**:  allows one to search for the citations of topics, authors, bibcode. Syntax for this is:  citations(bibcode:1999RvMPS..71..180H)[**EXAMPLE**](examples.md#citation-strings)
 * **references**: allows one to search for the references in topics, authors, bibcode.  Syntax for this type of search is: references("black holes") [**EXAMPLE**](examples.md#reference-strings)

The **"+ options"** button allows you to  
  * specify a publication date range to search in between (if you do not know the month you may use "00".)  
  * disable fulltext (searches only article metadata and not the entire article)
  * select articles only (this excludes documents like observing proposals, catalog descriptions, meeting abstracts and communications)
  * specify which databases to be searched.  The default is set to search both the astronomy and physics databases but you can specify to search only the astronomy database or to search only the physics database or to search all databases (by selecting all you will include articles which have not been categorized as physics or astronomy, e.g. arXiv preprints in computer science or general science articles in journals.)  
  * specify how many results to display on one page (20 is the default; 3000 is the maximum.)
  
##Advanced Searches##

Our search engine supports a list of operators which can take any query and manipulate the list of results to accomplish additional functionality.

###Second-order Queries###

We provide three operators which modify the query results by performing second-order operations on the original query. To use them, simply click on one of the three options below the search box or wrap your query with the corresponding operator in the search box.

**Trending** -- returns the list of documents most read by users who read recent papers on the topic being researched; these are papers currently being read by people interested in this field.  For example:

    trending(exoplanets)
    
will return a ranked list of papers which are currently popular among the readers interested in exoplanets.

**Useful** -- returns the list of documents frequently cited by the most relevant papers on the topic being researched; these are studies which discuss methods and techniques useful to conduct research in this field.  For example:

    useful("galaxy surveys")

will return a ranked list of papers spanning a variety of topics useful to researchers interested in analyzing surveys of galaxies.

**Instructive** -- returns the list of documents citing the most relevant papers on the topic being researched; these are papers containing the most extensive reviews of the field.  For example:

    instructive("weak lensing")

will return a ranked list of papers featuring reviews of weak gravitational lensing and its cosmological implications. 

###Citation and Reference queries###


###Truncation of result list###

You can limit the number of results returned by your search by using the topn() operator:

    topn(20,"galaxy clusters")
    
This will limit the list of results to be the 20 most relevant papers on "galaxy clusters"


###Positional Field Searches###

One operator 
 * **pos**: allows you to search for an item within a list result by specifying the position in the list e.g. pos(author:"Oort, J",2)


