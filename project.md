

# Cloud Computing Project 


In assignment 2 you have deployed a chatbot on a cloud platform, either with a LINE front end or a web front end. In this project we would want you to continue working on the chatbot as a team. You and your team should work together and submit documents before each of the project milestone. Fail to do so will incur penalty on your project.

For team with students all currently live outside mainland are required to do the LINE chatbot. For team with at least one student currently (as at 13/2/2020) live in mainland can opt to do the LINE chatbot or the web chatbot. This differentiation is due to the fact that LINE is inaccessible in mainland China.


## Chatbot Required Features

The chatbot should be with the context of public health care (instead of personal health care). It can be understood as things like the measurement against coronavirus, finding face mask/cleaning substance, summarize of news, etc. Your team can decide on what exact context that your bot can do. But technically, there are some constraints:

1. The bot should be able to differentiate at least X different types of queries and give X different types of responses, where X is the number of students in your group.
1. The bot should use a redis server to store some persistent information.
1. The bot should use consume another service other than redis.
1. The bot should be running on Heroku, or an equivalent cloud.
1. The design concept of the bot should be applicable to our society while the content (e.g. answer of questions, reported data) need not to be accurate, most updated, nor comprehensive. 
1. The bot should use git for version controls. 
1. The LINE bot should be written only with Python and its library. 
1. The web bot should be written only with Python and its library at back-end, while using Javascript + HTML5 at frontend. The frontend code (i.e. the html and js) should **NOT** be placed on the server.

## Milestone 1 - Chatbot Design and Setup

* Due date: 26th Feb, 2020 (Wednesday)
* Submit: 
    * A Github link of your team project repo, the repo should
        * Contain all members of your team
        * Contain a `readme.md` that states all students name and id
        * Contain a `spec.md` that states which bot (LINE/web) your team is doing and the design of your chatbot (100 - 1000 words)
        * If web bot is chosen, an evident of at least one student is staying in China needs to be presented by emailing it to your lecturer Kevin Wang directly.
* Marking Criteria: 2% if contains all of them. 1% if missing any of them. 0% if late severely. All-or-nothing.
* Submission method: write down the github link on moodle.

## Milestone 2 - A runnable chatbot prototype

* Due date: 18th March, 2020 (Wednesday)
* Submit:
    * Update your Github to contain your current code and add a file called `milestone2.pdf` that contains:
        * For Line bot: A QR code of your Line bot, 4 screenshots of what your bot can do at the moment, and revision of your design (if any).
        * For web bot: A URL of your web bot, 4 screenshots of what your bot can do at the moment, revision of your design (if any).
    * For web bot: if you have revise your front-end html, put it on Github for download as well.
* Marking Criteria: 2% if contains all of them. 1% if there are less than four screenshots of your bot. 0% if late severely, or if the app is not running, or code is missing. All-or-nothing.

## Milestone 3 - Information about the "another service"

* Due date: 1st Apr, 2020 (Wednesday)
* Submit:
    * Add a file called `milestone3.pdf` to your Github that contains information about which external service other than redis that you want to use such as: some links of tutorial/video that teaches you how to use that service; some sample code. You should also explain how would you want to use that service in your bot with 100-400 words.
* Marking Criteria: 1% if information and explanation of how it is used are presented. 0% if missing either of these or late severely. All-or-nothing.


## Milestone 4 - Project Presentation and Documentation

* Due date: 15th Apr, 2020 (Wednesday)
* Submit:
    * Update all your code on Github.
    * Deploy your code on cloud and run it.
    * Add a file called `milestone4.pdf` to your Github that answer the following questions:
        * How is your project architecture related to the theory taught in the lecture?
        * Can you demonstrate, with some screen cap, how to increase capacity of your chat bot service?
        * Can you identify if you bot is one of the example of PaaS, IaaS, SaaS? Explain your answer.
    * If on campus presentation is available at that time:
        * Present your work on stage for not more than 5 minutes.

* Marking Criteria: 10% for `milestone4.pdf`. 0% if the document is severely late. 17% for the project implementation and presentation, break down as follows:

| Item | Mark |
|---|---|
| Ability to handle X different types of queries | 1%^ |
| Usage of redis server | 1%^ |
| Consumption of other service other than redis | 2%^ |
| Compliance of other constrains | 1%^ |
| Usefulness of the bot to the real world | 7% |
| Appropriate usage of technologies | 2% |
| Attractiveness and completeness | 2% |
| Presentation | 1% |
| sub-total | **17%** |
| `milestone4.pdf` | **10%** |
| Total for Milestone 4 | **27%** |

^Marks are given in all-or-nothing style.

## Anti free-riding mechanism

At each due day of the milestones you can send me an email to report a potential case of free-riding. I will conduct some investigation. And give advise to students who are laid back. Severe case will incur penalty or even  "quarantine" a student and regroup.



## Note:

* If Github is not reachable to you, you might use other alternative git repository but make sure it is accessible from HKBU without pre-registration.
* **Plagiarism warning**: there is many chatbot solution available online and you can actually take a reference of those. However, directly copy these example without proper citation is definitely a violation of academic integrity. You should also avoid sharing your code to students outside your team.






