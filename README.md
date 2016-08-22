# Python-Search-Engine

A search engine is a software system that is designed to search for information on the World Wide Web. The search results are generally presented in a line of results often referred to as search engine results pages (SERPs). 
The information may be a mix of web pages, images, and other types of files.

A search engine maintains the following processes in near real time:
 Web crawling
 Indexing
 Searching

PARALLEL CRAWLER
The parallel crawler.py file has many functions –
 Logging() - Error in red is displayed by it. Real time program is shown in output by it.
 Get_text() – Url and soup files come from scan_page. All nonsense characters are removed. Encoding in UTF-8 is done. Words are written in index.
 Scan_page() – for url it calls all the pages one by one
 Soup – Library for parsing html
 Get_all _links() – All the links on the page are picked up and those links are returned. And time means how much time it took to scan the page. Scan_page is called here.
 Scrape() – We have to parallel crawl on a page 5 URLs are there for a page. Then we go to the page to put urls in a queue. Then we take the first url in it and see the time out. If it is getting visited then we will call all the above functions and if not happening then we will put it in visited queue. If it comes in the next page again then it would not be called again. It is already parsed. All new links are put in inqueue.
 Root() – We have to do the same process parallel. Python’s parallel queue is there in which if we put then it is sent to different course every time. Threading is the technique to run all processes parallel. Queue made into 4 queues. Main_queue is the queue in which all data comes and is divided into threads. 1 to 4 threads are there and in all we put url_queue and visited- 2 queues are passed to all. With th.start all the threads start and the threads are joined.
We have scraped all the data and stored it somewhere in index file. Actually we can store it in a proper database but for fast query and simulation it is stored here.


INDEX BUILDER
The index builder file has the following functions –
 Build_index() – It opens the index file then all lines are read in rows. Line’s separator is there to know the site and its words. Then it initializes a dictionary and takes all the links and it separates its words and then it stores the words. Words of the link are appended.
 Query() – It is used to query. The result = sorted is the page_rank algorithm. Page_rank understands the importance of a link. If there are many links pointing to that link it is important. So it will be ranked first. Query function is called then it goes and finds in all those links and sorts these links according to the priority.
