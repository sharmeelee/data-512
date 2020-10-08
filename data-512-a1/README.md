# data-512-a1
This folder contains a tutorial for how to gather, process and analyze data from the Wikipedia API for pageviews from different access types such as desktop and mobile sites. 
## Goal: Utilize Wikipedia traffic APIs to analyze the pageviews of English Wikipedia on a monthly basis from different access types. 

## Source Data
Licensed and subject to terms of use: https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions. It is developed and maintained by WMF's Analytics and Services teams, and is implemented using Analytics' Hadoop cluster and RESTBase
- The Legacy Pagecounts API 
  - documentation: https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts
  - endpoint: https://wikimedia.org/api/rest_v1/#!/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end
  - dates: December 2007 to August 2020
- The Pageviews API 
  - documentation: https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews
  - endpoint: https://wikimedia.org/api/rest_v1/#!/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end
  - dates: July 2015 to September 2020
  
## Output: en-wikipedia_traffic_200712-202008.csv
  - Fields
    - year: Yearly timestamp in format YYYY
    - month: Monthly timestamp in format MM
    - pagecount_all_views: number of pageviews for all access types in the legacy data
    - pagecount_desktop_views: number of pageviews for desktop-site access in the legacy data
    - pagecount_mobile_views: number of pageviews for mobile-site access in the legacy data
    - pageview_all_views: number of pageviews for all access types in the pageviews data
    - pageview_desktop_views: number of pageviews for desktop access in the pageviews data
    - pageview_mobile_views: number of pageviews for mobile-web and mobile-app access in the pageviews data
  
  ## Known Facts/Issues
  - data from the Pagecount API includes automated and human traffic
  - Pagecount data was uploaded once and never updated since
  - data from the Pagecount API does not include metawiki data
  - data from the Pageview API is uploaded at the end of the timerange specified above
  - updating and processing new data into the Pageview API can take more than 24 hours
  - data from the Pageview API excludes automated data
  

