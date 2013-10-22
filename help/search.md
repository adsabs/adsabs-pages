##Searching##

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

Search fields that are available for you include: 
 * **Author** -- format: lastname, firstname middleinitial
 * **First Author** -- format: lastname, firstname middleinitial
 * **Title** -- searches text within title field
 * **Year** -- format: YYYY or range YYYY-YYYY
 * **Publication** -- Use journal abbreviations from our <A HREF=
  "http://adsabs.harvard.edu/abs_doc/journal_abbr.html"> bibstem list </A>
 * **Fulltext** -- searches within the fulltext of articles
  
You can string together any of the search terms to develop a query.  The default operator is AND but can be changed by specifying OR in the query.  Similarly one can exclude a term by prepending a "-" sign to it. [**EXAMPLE**](examples.md#stringing-together-a-query)

In addition to the displayed search fields you may also use the following options to limit your search within the specified field(s).  Please note that with exception of the bibcode not all fields will be populated for all records.
 * **bibcode**: a 19 character identifier which describes the item record within the ADS (see <A HREF="http://adsabs.harvard.edu/abs_doc/help_pages/data.html#bibcodes">bibcodes </A> for further details)
 * **aff**: searches within the affiliation field 
 * **keyword**: searches keywords which were supplied by publishers or authors 
 * **DOIs**: digital object identifiers
 * **arXiv id**: see <A HREF="http://arxiv.org/help/arxiv_identifier">arXiv identifier</A> for further information
 * **abstract**: to search within the abstract of records
 * **properties**: are specific attributes of a record that can be searched.  Available properties are:  article, refereed, not_refereed, inproceedings, openaccess, nonarticle, eprint, book, proceedings, catalog, software.  The syntax for this search is property:property (e.g. property:book or property:refereed) [**EXAMPLE**](examples.md#property-strings)

The **"+ options"** button allows you to  
  * specify a publication date range to search in between (if you do not know the month you may use "00".)  
  * select a database:  astronomy, physics, general or all
  * disable fulltext (searches only article metadata and not the entire article)
  * select articles only (this excludes documents like observing proposals, catalog descriptions, meeting abstracts and communications)

  
The **search settings** option allows you to select how many results to display on one page (20 is the default; 200 is the maximum)
  
##Advanced Searches##

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
