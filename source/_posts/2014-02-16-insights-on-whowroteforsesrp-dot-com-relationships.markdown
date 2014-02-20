---
layout: post
title: "WhoWroteForSESRP.com reflection"
date: 2014-02-16 22:05
comments: true
categories: data visualization, soka education
---

![Chart: Articles vs Years](https://s3.amazonaws.com/LKBG-TG/blog/chart-articles-year.png)

#Algebra for designing layouts

I have been reading about machine learning and linear algebraic analysis. In college, I failed two calculus courses. In high school, I repeatedly failed higher-level algebra courses. In an academic setting, pumping away at math worksheets was never a convincing use of my time. I much rather play video games at the time. I didn’t realize at the time, but I was using complex equations to calculate the optimal strategy to win.

Although I never caught on to academic mathematics, I find myself regularly using algebraic equations at work. I use complex algebraic equations everyday while design. While visual design is driven by aesthetic choices, the execution of interactive layouts requires thought out calculations. To get a navigation item to “stick” on a webpage when scrolling, or “unstick” after scrolling a certain distance, calculations are necessary.

After recognizing how something pleasantly interactive requires mathematically complex planning, I decided to explore other pursuits. I love math when its applied to something practical. I thrive in solving animation related math problems. Through reading about machine learning, I found a new topic that seemed interesting. 

I attended the Soka Education Student Research Project conference this weekend. In preparation, I compiled the past 10 years of published articles. The compilation was made for WhoWroteForSESRP.[^1] The process resulted in a simple JavaScript table for users to search published authors, titles, and issues.


#Presenting data

The context in which you view Data (with a capital D) determines what you can understand. Edward Tufte emphasizes this point. I tried to understand the past 10 years of SESRP published papers. First, I organized the information in a flat context with simple attributes. Second, I viewed the relations between the attributes in aggregate. Lastly, I created charts and tables to make the results clear. This process shows that there are still many interesting relationships among SESRP papers that have not been clearly identified.

The first step required me to review the past 10 years of published journals. I selected the individual published paper titles, associated authors, and published issue year. The attributes chosen could have been expanded to full article texts, human-defined tags or categories, and article bibliography. Initially, I wanted to create a basic repository for easily browsing the past-published articles. [^2]

Second, I isolated the individual attributes to view them in relative increasing or decreasing order. Through collecting the data, I saw a distinct increase in published papers during the year 2011. Similarly, viewing the authors in aggregate clearly displayed the writers who published the large number of articles over the past 10 years. [^3]

Lastly, I charted the data to further understand the relationships between the authors, years published, and quantity of articles. In the future, I will add attributes to compare against. Mainly, I am interested in charting network relationships between cited articles, cited authors, and unrecognized topic driven clusters. [^4]


#Insights from analysis

Filtering the quantity of articles published by year showed a unusual spike of submissions and a potentially changing overall trend. In 2011, the number of articles submitted more than doubled from previous year. In 2010 nine (9) articles were submitted, followed by 22 articles submitted in 2011. In the years following 2011, the average number of articles submitted increased by over 20%.

The quantity of articles published by author shows a familiar trend in participatory communities. Out of 85 total authors published in the yearly booklets, 64 authors had one paper published, 13 authors had two papers published, 3 authors had three papers published, 3 authors had four papers published, and 2 authors had five papers published. These numbers show that in the past 10 years from 2005 to 2014, approximately 75% of writers only publish one article.

The two authors who published the most are Gonzalo Obelleiro and Ryan Hayashi. Obelleiro’s first article appeared in 2006 and Hayashi’s first article appeared in 2011. While Hayashi and Obelleiro have the same number of articles published, Obelleiro has presented articles that have not been published, therefore technically he has written more than any other author. Regardless, Hayashi has been writing for less than half the number of years, so his rate of appearance is impressive.

![Chart: Authors vs Articles](https://s3.amazonaws.com/LKBG-TG/blog/chart-authors-articles.png)

#Suggestions

The past 10 years of conference organization has been completely led by students. The proposal request process for SESRP papers is distributed through current student body, the alumni network, and individual requests. In the interest of revitalizing previously interested attendees, past SESRP paper submitters should be personally requested to submit new papers. Future student tasked with organizing the SESRP conference should seek to mobilize the 75% of one-time publishing authors to propose a new paper topic. Most past authors are alumni of Soka University of America, so the alumni network may be useful in gathering contact information.

As the 10-year anniversary booklet is being prepared, organizers should seriously consider the 25% of authors who published more than one paper. The eight authors who published more than 3 articles each should be consulted for advice. While quantity of published papers does not reflect a priori for understanding Soka Education, their insight should be considered. These authors have shown personal interest through their multi-year commitment. These authors, from most published to least, are:

Gonzalo Obelleiro (5)
Ryan Hayashi (5)
Maria Sanchez (4)
Jean Marcus Silva (4)
Michael Strand (4)
Masahiro Kaleo Louis (3)
Menelik Tafari (3)
Nozomi Inukai (3)

#Future expectations

The three attributes listing of the SESRP papers from 2005 to 2014 have raised positive results. This method of organizing information and finding relationships will be further applied to understand the relationships between sources cited in submitted papers. The goal will be to find the unseen relationships between the submitted papers. The cited resource’s author and publications will help create rich network maps displaying relationships between SESRP authors. Similarly, this relational mapping may display under recognized clusters or categories. This will prove to be useful in the 10-year anniversary booklet’s drafting.

[^1]: Website mentioned above is located here: [WhoWroteForSESRP.com](http://whowroteforsesrp.com)

[^2]: [Raw excel 2005-2014 title-author-issue data](http://a.lkb.cc/raw-SESRP-10-year-data)

[^3]: ![Chart: Articles vs Years](https://s3.amazonaws.com/LKBG-TG/blog/chart-articles-year.png)

[^4]: ![Chart: Authors vs Articles](https://s3.amazonaws.com/LKBG-TG/blog/chart-authors-articles.png)
