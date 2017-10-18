# data-512-a1
Sean Miller (<millsea0@u.washington.edu>) 10-16-2017

#### Overview

This repository outlines using the Wikipedia **Pagecounts** and **Pageviews APIs** to analyze data about the amount of traffic both the desktop and mobile English Wikipedia sites saw per month from January 2008 through September 2017. If possible, we wish to limit the views to ones initiated by a user and not a spider/crawler. 

**TO NOTE**

While the **Pageviews APIs** is able to do filter by user/spider/crawler, the legacy **Pagecounts API** does not provide a filter to limit results to only users.

#### License

Data for English Wikipedia Pagecounts retrieved from [Wikimedia API](https://wikimediafoundation.org/wiki/Terms_of_Use/en) is licensed under [CC BY SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/).

#### Libraries

All of the following code was written and tested against the default packages present in **Anaconda3 v4.4.0**. You can find a download for Anaconda and its latest versions at <https://repo.continuum.io/archive/>.

#### APIs

To retrieve data about the number of views the English Wikipedia site saw per month, we used both the **Pagecounts** and **Pageviews APIs**. As part of the [Wikimedia Foundation Terms of Use](https://www.mediawiki.org/wiki/REST_API) you are asked to limit requests to this API to fewer than 200/sec and to set a User-Agent field in the header.

For example, setting the header value in Python looks like the following. This headers variable is passed into your get request.
```python
headers = {"User-Agent" : "https://github.com/awfuldynne", "From" : "millsea0@uw.edu"}
```

###### Links to API Documentation

| API | Documentation | Endpoint | Date Range |
|------ | ---------- | -------- | --------|
|Pagecounts | [Pagecounts Documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts) | [RESTBase Reference](https://wikimedia.org/api/rest_v1/)| Jan 2008 - July 2016 |
|Pageviews | [Pageview Documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews) | [RESTBase Reference](https://wikimedia.org/api/rest_v1/#!/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)| July 2015 - Present Day |

###### Structure of Repo

- **clean_data:** Contains any processed data outputs
- **raw_data:** Contains any raw data such as responses from the Wikimedia APIs
- **outputs:** Contains final outputs of the analysis

###### Structure of clean_data/en-wikipedia_traffic_200801-201709.csv

| Column | Description | Value |
|------- | -------- | -------- |
| year | Four digit representation of year | YYYY |
| month | Two digit representation of month | MM |
| pagecount_all_views | Total count of all views from Pagecount API | num_views |
| pagecount_desktop_views | Total count of desktop views from Pagecount API | num_views |
| pagecount_mobile_views | Total count of mobile views from Pagecount API | num_views |
| pageview_all_views | Total count of all views from Pageviews API | num_views |
| pageview_desktop_views | Total count of desktop views from Pageviews API | num_views |
| pageview_mobile_views | Total count of mobile views from Pageviews API | num_views |