
---
# ![](./img/hkbu.png) COMP7940 Cloud Computing (2019-20 Semester 2)

Lecturer: Dr. Kevin Wang ([kevinw](mailto:kevinw@comp.hkbu.edu.hk))

TA: LEI, Zijian ([cszjlei](mailto:cszjlei@comp.hkbu.edu.hk))


> Before starting the assignment, you should have applied the following accounts 
> 
> 1.  GitHub students (not just PRO account)
> 2.  Heroku account
>
>     2.1 Optionally, acquire [Heroku for GitHub Students](https://www.heroku.com/github-students) to upgrade your Heroku account to Hobby. But that requires you to input your credit card to redeem the offer. 
> 3.  Install Line into your phone and register an account with it.


## Assignment 1 - Consuming web service with Python

* Due date: 2/2/2020 (Sunday, WK3)
* Submission method: [on Moodle](https://buelearning.hkbu.edu.hk), submit one single py file.
* This is an individual assignment.
* Total Mark: 6% 

Quick Summary: With a given skeleton Python code, you are required complete the code to connect to a given [redis server](https://redislabs.com/lp/python-redis/) and perform certain I/O. 

## Assignment 2 - Deploying your app on Cloud

* Due date: ~~16/2/2020 (Sunday, WK5)~~   **postponed to 23/2/2020 (Sunday, WK6)**
* Submission method: [on Moodle](https://buelearning.hkbu.edu.hk), one single PDF with your findings and [the QR code of your bot (**for Line version**)  or ONE screenshot of cloud console (**for web version**)].
* This is an individual assignment.
* Total Mark: 12%


Quick Summary:
> --- 
> **Updated** 
> ---
> There are two options given to students to finish the assignments due to the fact that some students are unable to connect to LINE server in their home. The difficulty and requirements of the these two options are similar. All students are free to choice any of these version for Assignment 2.

Line Version: You are required to deploy the Python Line chatbot given to you on this repository to Heroku platform. By inspecting the code and with some trial-and-error, you need to tell us what is the behavior of the bot.

Web Version: You are required to deploy the Python Web chatbot given to you on [another repository](https://github.com/khwang0/1920S2-COMP7940v2) to any cloud platform (preferably Heroku). By inspecting the code in both `test.html` and `newassignment.py` and with some trial-and-error, you need to **explain** the code line by line to explain the behavior of the bot.

## Project - a Python chatbot

* Due date: 15/4/2020 (Wednesday, in class, WK14)
* Submission method: [on Moodle](https://buelearning.hkbu.edu.hk), one single PDF report plus a presentation less than 5 minutes. Program code should be placed on GitHub for inspection.
* This is a group project (size <= 3).
* Total Mark: >=22%

Quick Summary: You are required to continue work on the chatbot that you have built in Assignment 2. The chatbot is to provide health care advise to users. The details of the project will be announced later.


>---
>[Project Details](./project.md) - under construction
>
>---

---


# Detail Instructions

## Working with the GitHub

You should begins with [fork this repo](https://guides.github.com/activities/forking/) and clone it into your machine. Alternatively you can download the code as a zip by clicking the download button on this page. But we would suggest you to fork the project instead since you will be able to patch any update if we are going to release any new stuffs to you.


## Assignment 1

You can find the skeleton code of Assignment 1 inside the folder `assignment1`. To begin with, you have to install Python3 with version >=3.6. We are using the [redis](https://redis.io) package and therefore you need to install redis. It is recommended to install it using `pip`. Type the following in your command prompt or terminal.

```
pip install redis
```

> Noted: you should not build your own redis server, totally not necessary and it is not what we want.

If you have setup things properly, you can try running the code by

```
python assignment1.py
```

You will be allowed to have some interaction with program. You should see, probably:
```
Please enter your query (type 'quit' or 'exit' to end):Hi
You have entered Hi for X times
Please enter your query (type 'quit' or 'exit' to end):Hello
You have entered Hello for X times
Please enter your query (type 'quit' or 'exit' to end):HKBU
You have entered HKBU for X times
Please enter your query (type 'quit' or 'exit' to end):Kevin
You have entered Kevin for X times
Please enter your query (type 'quit' or 'exit' to end):quit
(Program ends)
```

## Task 1

Adding a few lines of code you shall be able to communicate with the given redis server. The redis server should:
* Return how many times of a keyword/query is typed; and
* Increment the counter of the keyword when it is typed; and

---
### --Update : 23/1/2020

The redis server (the one coded in the `assignment1.py`) now contains many [keys-value pairs](https://www.tutorialspoint.com/redis/redis_keys.htm), like:

| Keys | Value |
|---|---|
| haha  | 1  |
| hi  | 5  |
|  Hello | 2  |
| hkbu  | 1  |
| bye  | 2  |
|...   | ...  |

Using the [tutorial here](https://redislabs.com/lp/python-redis/) to learn how to get the keys-value pair!

> The tutorial does not provide complete answer (**of course it doesn't**). You might need to do some search on Google or refer to the [docs](https://redis-py.readthedocs.io/en/latest/#). Our Piazza page is a good friend for you too!
 
---



The expecting result is:
```
Please enter your query (type 'quit' or 'exit' to end):Hi
You have entered Hi 14 times
Please enter your query (type 'quit' or 'exit' to end):Hello
You have entered Hello 1 times
Please enter your query (type 'quit' or 'exit' to end):Lo
You have entered Lo 1 times
Please enter your query (type 'quit' or 'exit' to end):Bye
You have entered Bye 1 times
Please enter your query (type 'quit' or 'exit' to end):HKBU
You have entered HKBU 1 times
Please enter your query (type 'quit' or 'exit' to end):Hi 
You have entered Hi 15 times
Please enter your query (type 'quit' or 'exit' to end):quit
(Program ends)
```

## Task 2

Then, apply a redis service from redislabs.com for free. Replace the redis server setting with your redis service. 

After this step, the counter of all keywords should be reset to 1. 

Submit your python code to Moodle before due day.

**Again, we expect that you can complete the code and consume the redis service from the account that you have applied**

---

## Assignment 2 - Line Version

> ---
> Important Update:
> ---
> As suggested by student that the line 57-74 needs to be commented first before you can verify the webhook. After the verification you can enable that and deploy it again.
> https://piazza.com/class/k56apf6o1n7398?cid=20
> 
> ---

In this assignment you are required to deploy the assignment2.py **WITHOUT CHANGING** any code to Heroku. The task is complicated and easy to make mistakes. But, you should be able to do it if you follow the step properly.


1. Install Line massager in your mobile phone and create a user account.
2. Go to developers.line.biz to setup a chatbot. You should setup `Messaging API`.
3. Next, you are going to setup a Line channel. Pay attention the following parameters:
     1. Channel secret, which should be on the tab `Basic settings`
     2. Channel access token, which should be on the tab `Messaging API`
     3. Set `Use webhook` to enable. This should be on the tab `Messaging API`
4. Create an app on Heroku.com. Free Dyno is good enough. Unless stated otherwise, you should not register your credit card until you are fully aware what are you doing.
     1. In the `Settings` tab of Heroku dashboard, fill in the following variables in `Config Vars` > `Reveal Config Vars`
         * `LINE_CHANNEL_ACCESS_TOKEN` with the  channel access token
         * `LINE_CHANNEL_SECRET` with the channel secret
     1. Look for the phrase "Your app can be found at https://yourappname.herokuapp.com" under the section `Settings` > `Domains`. Copy the url https://yourappname.herokuapp.com and add `/callback` after it and put them in Line channel console > `setting` > `Webhook settings` > `Webhook URL`.
1. Deploy your code to heroku by using Heroku Git. (Will expand this part later, for now follow the instruction given on Heroku dashboard > `Deploy`)
1. If everything setup properly, the service is up and you can go to Line developer console > `Settings` > `Webhook settings` > click `Verify` and sending message with your bot.

By inspecting the code and with some trial-and-error, state the behavior of the chatbot (what it does; no need to explain it line-by-line) on a PDF file together with the Bot ID and Bot QR code.

> **Note**:  The behavior of the code is **NOT** the same as the code that was [video demo](./LineProjectDemo.mov).

<video src="./LineProjectDemo.mov" width="80%
" controls preload></video>

---

## Assignment 2 - Web Version

>---
>Code: https://github.com/khwang0/1920S2-COMP7940v2
>---

You don't need to change any part of the code here. It works similar to the Line version where you are deploying the code to a cloud server. We use Heroku as an example. For students who have connection issue in using Heroku, you are allowed to use other cloud service. However, please carefully choice your cloud so that: 1) we would be able to access it at HKBU; 2) it would not expire by May (possibly the project submission date); 3) it does not incur any unnecessary cost in particular there is no any authentication mechanism in place, it could, technically speaking, drain up all your quota.

Perform the following steps to finish this assignment. You might make some mistake in doing the following steps, be careful. As usual as on Piazza if you have any problem.

1. Checkout the code from the repo of assignment 2 - web version. 
1. Run the code in debug mode locally by
```sh
python newassignment.py
```
1. Open `test.html` on a browser and have a try. Type `http://127.0.0.1:5000/` under the field `Server Address (Heroku):`. Look at the console of your server and study that.
1. Apply an account from Heroku
1. Create an app on Heroku.com. Free Dyno is good enough. Unless stated otherwise, you should not register your credit card until you are fully aware what are you doing.
1. Deploy your code `newassignment.py`, `Profile`, `requirement.txt` to heroku by using Heroku Git. (Will expand this part later, for now follow the instruction given on Heroku dashboard > `Deploy`)
1. Look for the phrase "Your app can be found at https://yourappname.herokuapp.com" under the section `Settings` > `Domains`. Copy the url https://yourappname.herokuapp.com and add `/callback` after it.
1. Open the log console at Heroku and inspect the output.
1. Open `test.html` stored in your **local** folder, paste the address that you copied above to `Server Address (Heroku):` again. 
1. Try to open another instance of `test.html` and see if there is any difference.


By inspect the code inside `newassignment.py` and `test.html`, explain the code line by line and try to identify the technologies that we have covered in Lecture 3 (12/2/2020). Also, take a screenshot of the Heroku console tab. Prepare these into a 2 to 4 pages PDF file and submit it on moodle.

