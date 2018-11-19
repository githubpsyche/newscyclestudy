
# News Cycle Study

## Purpose

The "news cycle" is not necessarily a well-defined concept. Traditionally, a news cycle has been defined as "the amount of time that passes between the release of one edition of a news outlet and the follow up edition", a notion almost rendered moot by the advent of the 24-hour news cycle where newsworthy events are reported almost immediately after they occur, no matter the day or time [[Wisegeek](http://www.wisegeek.com/what-is-a-news-cycle.htm)]. Conscious of this, some modern sources conceive of a news cycle not in terms of time, but rather in terms of how news is 'processed' by the media. Slate.com's Jack Shafer describes the news cycle as consisting of three phases: 

> To him, “24 hour news cycle” refers to three phases of news. “Overnight, newspapers launch the news,” Shafer wrote. “They publish stories clarifying the events of yesterday; they break their own investigative stories; they print zeitgeist-defining feature articles and op-eds." The morning brings phase two, when “Web media critics [like bloggers and commenters] react to the news." Phrase three, Shafer said, is “the buildup, [which] comes in the afternoon, as the events of the day unfold … Opinion makers try to shape how the day's events will play on the night's cable shows and in tomorrow's newspapers. The next morning, it all starts over again." [[PR Daily](https://www.prdaily.com/Main/Articles/What_does_24_hour_news_cycle_actually_mean_222.aspx)]

[Oxford's Living Dictionary's](https://en.oxforddictionaries.com/definition/news_cycle) definition seems to capture these subtly distinct meanings best: a news cycle is simply "a round of media coverage". It's media activity surrounding a story from the moment it becomes "news" and begins getting media coverage, to the moment it stops. 

Having embraced this conception of the news cycle, we wondered just how long a news cycle is - how long does it take for the media to start and stop talking about an event? - and how the length of this period has changed over the years. The question is important because widespread media coverage of events like earthquakes or political events is thought to both reflect and play a key part in defining what the broader public is aware and attentive to. Shifts over the years in the duration of coverage of various types of events can potentially help explain concomitant changes in a broad variety of social phenomena. 

With this project, **we sought to quantify and understand how the length of time it takes for this sort of media activity surrounding a story to start and stop has changed over the years**. We examined this question by sampling events from various databases and searching newspaper archives for coverage related to those events, counting articles and tracking the date upon which they were published. Intuitively, coverage of an event will tend to peak around when the event first happens, and then drop quickly as time goes by. But the pace of the drop and other aspects of this pattern can have broad variability depending on countless factors. For now we focus on just one of these - an event's date. Our methods and results are detailed below.

## Methodology (Needs Updating)

The data components of a project like ours are twofold. First, we take a database of many similar events that have occurred over several decades. Second, for each event in the database, we search a database of news archives to measure media coverage of the event succeeding its happening. In this section, we describe the data sets used to drive our project as well as the steps we took to utilitize them systematically.

#### Database Details:
- The Global Terrorism Database (GTD) - https://www.start.umd.edu/gtd/about/
- The International Disasters Database (EM-DAT) - http://www.emdat.be/explanatory-notes
- The ProQuest Historical Newspapers™ Archive - http://proquest.libguides.com/hnp

Notes: GTD is missing 1993 data. EM-DAT goes back further than 1970.

#### Event Inclusion Criteria
- the event happened in the USA
- the event happened between 1970 and 2015 inclusive
- have an event location in the database more specific than nation (**GTD events always met this criteria; EM-DAT less reliable**)
- news article search for the event had to return at least one result (**note: should i count 0-article events?**)
- if a terrorist attack, the event had to meet all three GTD criteria for terrorism (**note: may soon alter to 1**)
- if a terrorist attack, it had to be successful (**note: may soon not require a successful attack**)

#### Search Strategy
GTD event search term:
> (attack_location) AND ((shooting) OR (bombing) OR (bomb) OR (violence) OR (murder) OR (terrorism)) AND (date_range)

Where attack_location specifies where the attack occurred and date_range specifies the first 50 days after the attack, including the day of the attack.

EM-DAT search term:
> (disaster_location) AND (one_of_these_labels) AND (date_range)

Where disaster_location specifies where the disaster occurred, and date_range specifies the first 50 days after the attack, including the day of the attack, and one_of_these_labels denotes the set of event labels pulled from the event's disaster type, disaster subtype and related associated entries within the EM-DAT.

Results were sorted oldest first, required to be in english and available in full text from the databse, and had duplicates removed before being returned. 
