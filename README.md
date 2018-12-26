# search_engines  

A python library that performs queries to google, bing, yahoo, and other search engines and collects the search results.  
When using Torch, `requests[socks]` is required, which can be installed using the requirements.txt file, as described below.  
Note that web-scraping may be against the TOS of some search-engins, and may result in a temporary ban.

## Search engines  
Google  
Bing  
Yahoo  
Duckduckgo  
Startpage  
Dogpile  
Ask  
Searx  
Unbubble  
Torch  

## Features  
 - Can use one, multiple, or all the search engines listed above (as a CLI script).  
 - HTTP and SOCKS proxy support.  
 - Collects dark web links with Torch.  
 - Supports search operators - 'url:', 'title:', 'text:'.  
 - Creates report files (html, csv).  
 - Easy to add new search engines. You can add a new engine by creating a new class in `search_engines/core/engines.py`, and register it on the `search_engines` dictionary in the same file. The new class should subclass `Search`, and it should override those methods: `_selectors`, `_first_page`, `_next_page`.  
 - Python2 - Python3 compatible.  

## Requirements  
Python 2.7 - 3.7, with requests and bs4  

## Installation  
Copy searchengines to your python libraries.  
Install requirements,  `python -m pip install -r search_engines/requirements.txt --upgrade`.  
Done!  

## Usage  

As a library:  

```
from search_engines import *

engine = Google()
results = engine.search("my query")
links = results.links()

print(links)
```

As a CLI script:  

```  
python search_engines/search.py -e google,bing -q "my query" -r html,csv
```
