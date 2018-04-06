=========
BoilerPy
=========

About
---------------------------------------

BoilerPy is a native Python port of Christian Kohlschütter's Boilerpipe library, released under the Apache 2.0 Licence. (http://code.google.com/p/boilerpipe/
)

I created this port since I don't have access to Java on my webhost and I wanted to create a pure Python version.  Another Python version which consists of Python hooks to the original Java library can be found here : (https://github.com/misja/python-boilerpipe
)  It might be a better option if you are able to run Java.

BoilerPy was created with the help of the excellent Java2Python library :(https://github.com/natural/java2python
)


Installation
---------------------------------------

BoilerPy was packaged with distutils.  In can be installed from the command-line with the following line:

    ``>python setup.py install``

Usage
---------------------------------------

    ``import boilerpy``

    ``boilerpy.extractors.ARTICLE_EXTRACTOR.getContentFromUrl('http://www.example.com/')``

    ``boilerpy.extractors.ARTICLE_EXTRACTOR.getContentFromFile('site/example.html')``

    ``htmlText='<html><body><h1>Example</h1></body></html>'``
    ``boilerpy.extractors.ARTICLE_EXTRACTOR.getContent(htmlText)``



Extractors
---------------------------------------

ARTICLE_EXTRACTOR
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A full-text extractor which is tuned towards news articles. In this scenario it achieves higher accuracy than DefaultExtractor. Works very well for most types of Article-like HTML.


DEFAULT_EXTRACTOR
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Usually worse than ArticleExtractor, but simpler/no heuristics.  A quite generic full-text extractor. 


LARGEST_CONTENT_EXTRACTOR
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A full-text extractor which extracts the largest text component of a page.  For news articles, it may perform better than the DefaultExtractor but usually worse than ArticleExtractor


CANOLA_EXTRACTOR
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Trained on krdwrd Canola (different definition of "boilerplate"). You may give it a try.


KEEP_EVERYTHING_EXTRACTOR
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Marks everything as content. Dummy Extractor; should return the input text. Use this to double-check that your problem is within a particular Extractor or somewhere else.


NUM_WORDS_RULES_EXTRACTOR
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A quite generic full-text extractor solely based upon the number of words per block (the current, the previous and the next block).


ARTICLE_SENTENCES_EXTRACTOR
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A full-text extractor which is tuned towards extracting sentences from news articles.

Version
---------------------------------------

1.0 - Created 14 Feb 2013
