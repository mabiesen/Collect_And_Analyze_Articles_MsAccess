# Fetch and Scrape Articles for Corrections


#### About This Project

I began this project with the hypothesis that American news agencies are more than willing to offer corrections because the American people at large have a short memory for events, and the correction of an article usually does not incite enough emotion to give news companies pause.  There is also a strong incentive within the industry for personnel to reveal stories in advance of their competitors.

With that in mind I set out to catalog news articles by category and analyze the data to determine whether corrections issued by an organization were indicative of political bias or if the mistakes were made in ernest.  I obtained a New York Times API key and a News API key.  I then created my Access database, wrote some VBA code to automate data collection, and set out to find out how companies display their corrections.

What I found was shocking.  Most news companies do not post their corrections in a transparent manner such that you can find both the correction AND the article.  Whats more, many companies italicize their corrections and place them at the bottom of articles such that they are not well visible and a reader may never know the article was corrected.  Additionally, many companies place their correction text inside of "normal" html elements with no tag to indicate that a correction exists.

As of 7/31/2017 (approx. 4 days into the project) I have yet to find a company that meets the standard of the New York Times, providing 1) an API, 2) html identifications of corrections through class assignment, 3) emboldened headings on corrections, and 4) a corrections page.  Because the New York Times is the only company for which I am able to find solid corrections information, I am going to discontinue the project for the time being; I would need at least 5 companies with easily accessible corrections to make this project worth further consideration.

#### How it works

The action is two part:

1.  Run the "getNytArticles" macro in the "GetNewYorkTimes" module to obtain all New York Times articles for the last week.  The default is set to Trump.  Articles are inserted into the "ArticleRepo" table.  You can also run the NewsAPI macro, though correction identification and keyword searches are not applicable.

2.  Run the "checkForCorrections" macro in the "ArticleScrapers" module to check for corrections.  This will load all articles from the database and one-by-one obtain the html for the article and search for the correction class.  If corrections are found, they should be logged in the error table and the article should be updated with a reference to the correction.  NOT YET COMPLETED; error handling required.

NOTE: If you intend to test these macros, you need the New York Times and News API keys respectively.  These can be obtained online for free.
