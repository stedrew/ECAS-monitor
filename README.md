ECAS-monitor
============

Checking the Electronic Client Application Status (ECAS) from CIC website can be painful because it does not come with a notification function. You have to check it again and again for any progress on your case. The update time is also random which does not reflect the actual status in real-time. Your status could be updated in midnight. Therefore, people check their ECAS a hundred times a day when they anxiously wait for their status update, wasting their time while bothering CIC servers.

To relive the applicants from desperate waiting and checking, and to reduce the load of CIC servers, I have developed a small tool called ECAS-monitor. It automatically checks ECAS for applicants every few hours, and sends the user an email alert when a status update is detected. Known status that can be detected includes but is not limited to:

* We started processing your application on YYYY-MM-DD.
* Medical results have been received.
* A decision has been made on your application. The office will contact you concerning this decision.

Here are steps of getting the tool working for you:

* You first need to change the configuration file `config.txt` and input your own information. There are clear instructions for you in the file. So follow them. The only thing to take care is the country of birth: you have to check your three-digit country code in the file [`countries.txt`](https://github.com/zhuheec/ECAS-monitor/blob/master/countries.txt), and update it accordingly in `config.txt`. For example, if you are from *China, People's Republic of*, then update the line to `Country Of Birth=202` in `config.txt`.

* Then you need to have <a href = "http://nodejs.org/" target="_blank">`Node.js`</a> runtime environment installed on your computer (`node` and `npm`). 

* After you have installed Node.js, to run this tool, Windows users can directly double-click `start.bat`. If you are using another OS, go to the directory of this tool and run:

```bash
$ npm start
```

You are done. Keep the program running so that it works for you all the time. Any time you want to stop the program, simply close the command-line window or press `Ctrl-C`.

**Note:** All your personal information is transmitted over the Internet securely using HTTPS, while saved in `config.txt` locally on your computer in a text file. I do not have any access of your information. So it is your responsibility to protect that file as well as your information.
