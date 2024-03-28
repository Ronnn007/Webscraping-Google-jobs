# Web Scraping-Google-jobs
Using the Selenium automation library paired with Python, this task was accomplished
### Goals & Scope
The overall goal for this project is to understand and visualise the current Job search market in Tech and AI. Which is at a rather over-saturated stage at the moment, especially for the entry-level positions. This project is only the first stage towards understanding this data and additional correlated information is certainly to be considered in the future.

The scope of this data is from Google Jobs, which obviously only represent a small portion of the Jobs advertised among several popular job boards. However, the choice for this platform is due to the fact that google allows web scrapping (to a certain degree). Previously, I tried to accomplish this task via indeed, which resulted in a temporary blockage for my access. Nevertheless, in the future, we can also consider additional popular job boards.
### Example of a Typical Job Webpage, Advertised sites, Base salary, Description Panel
Below are the areas of the webpage that we are interested in. Since this is a dynamic webpage, it requires interactions for additional information to be processed. E.g. Scrolling or clicking.
![](https://github.com/Ronnn007/Webscraping-Google-jobs/blob/main/Webpage%20Example%201.jpg)
### Description Button and Typical Pay range
![](https://github.com/Ronnn007/Webscraping-Google-jobs/blob/main/Webpage%20Example%202.jpg)

### The process or Algorithm
In order to extract the most relevant information, here is the overall walkthrough of this script:
1. As the page is scrolled, it loads new Job cards dynamically. (Area 1)
2. However, there are already 10 preloaded Job cards. First, we count the 10 preloaded Job cards and then perform additional scrolling to load new cards.
3. As we traverse through each job card, a clicking functionality is performed which loads the Job information (Area 2). Here the first advertised job board in extracted. Secondly, the base salary is checked (available at the top below the advertised job sites). If this is available, then it is extracted else a typical salary range is extracted (available at the bottom). If there isn't any salary information, then 0 is placed for this job entry. Next, Job descriptions are extracted, expanding the full description button. 
4. Until there are no new cards left to load, we continue repeating these actions. (On average, each job search query loads about 150 jobs).

### Data to be extracted
[Job Title,
Company Name,
Salary (Base Salary or Typical Salary range),
Job Advertised website (LinkedIn / Indeed),
The URL,
Description]

* Many Job titles can be searched in a session. Below are the Roles that were used in order to Scrape the data visualised. ['machine+learning','graduate+data+science','graduate+software+engineering', 'data+science']
* The roles are Formatted with the shorted version of URL required by google: ["https://www.google.com/search?q={}&ibp=htl;jobs&=#htivrt=jobs"]

## Graphs
### The most common Job Ttiles from Scrapped data
![Job Titles](https://github.com/Ronnn007/Webscraping-Google-jobs/blob/main/Most%20common%20Jobs.png)
Data Science proves to be the most often used as a job title by employers or recruiters in job adverts. Also, a varied range of Graduate positions however that reflects the Keywords that were used during the search!

### Job-Boards with most jobs advertised
![](https://github.com/Ronnn007/Webscraping-Google-jobs/blob/main/Sites%20with%20Most%20jobs%20advertised.png)
Indeed tops the list as expected with more than 40 jobs followed by LinkedIn and Jooble.

### Job-Boards with most Entry Level Jobs
![](https://github.com/Ronnn007/Webscraping-Google-jobs/blob/main/Sites%20with%20most%20entry%20level%20jobs.png)

To create this bar chart Gradute Keywords were used to search the dataframe['Graduate', 'Entry Level', 'Junior', 'Recent Graduate','Grad'].
Surprisingly, Indeed ends up at the bottom of the list with least graduate level positions advertised, at least from the job titles.

### Salary Density for popular roles
![](https://github.com/Ronnn007/Webscraping-Google-jobs/blob/main/Density%20of%20salaries%20for%20most%20common%20roles.png)

A large portion of salaries are just below 40k, representing the entry-level jobs,. Whilst the peak of the density distribution being on the higher end, likely above £80k, indicates that senior-level positions dominate the job market. Which does imply that organisations are actively seeking experienced professionals in the current economic climate.
