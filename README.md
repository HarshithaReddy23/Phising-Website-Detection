# Phising-Website-Detection
The availability of multiple services such as online banking, entertainment, education, software downloading, and social networking has accelerated the Web's evolution in recent years. As a result, a massive amount of data is constantly downloaded and transferred to the Internet. This allows attackers to access sensitive personal or financial data such as usernames, passwords, account numbers, and social security numbers. This is known as a Web phishing attack, and it is one of the most serious issues in web security. In a Web phishing attack, the attacker creates phishing websites that look similar to real websites in order to trick Web users and get their sensitive financial and personal information. The phishing attack begins with the victim clicking on a link contained in an email. Victims will receive an email with a link to update or validate their personal information. The Web browser will send the target victims to a phishing website that looks similar to the original website if they click this link. Because web users are asked to input critical information on the phishing website, attackers can steal important information from them.
PROPOSED METHOD:
This project presents a methodology for phishing website detection based on
machine learning classifiers with a wrapper features selection method. In this
project, some common supervised machine learning techniques such as Random
Forest Classifier, confusion matrix, etc.; are applied with effective and significant
features selected using the wrapper features selection approach to accurately detect
phishing websites. The experimental results demonstrated that the performance of
the machine learning classifiers was improved by using the wrapper-based features
selection. Moreover, the machine learning classifiers with the wrapper-based
features selection outperformed the machine learning classifiers with other features
selection methods.
DATA SET:
The data set that is used for this project was provided by the organization. There are
two sets of data, the first type of dataset contains all the legitimate type of websites
and the other data set contains different kinds of URLs that are all phishing
websites (450177)
Sample data set entries:
url,label
1. diaryofagameaddict.com,bad
2. espdesign.com.au,bad
3. iamagameaddict.com,bad
4. kalantzis.net,bad
5. slightlyoffcenter.net,bad
6. toddscarwash.com,bad
7. tubemoviez.com,bad
8. ipl.hk,bad
9. crackspider.us/toolbar/install.php?pack=exe,bad
3
10. pos-kupang.com/,bad
11. rupor.info,bad
12. svisiononline.de/mgfi/administrator/components/com_babackup/classes/fx29id1.tx
t,bad
13. officeon.ch.ma/office.js?google_ad_format=728x90_as,bad
14. sn-gzzx.com,bad
15. sunlux.net/company/about.html,bad
16. outporn.com,bad
17. timothycopus.aimoo.com,bad
18. xindalawyer.com,bad
19. freeserials.spb.ru/key/68703.htm,bad
20. deletespyware-adware.com,bad
21. orbowlada.strefa.pl/text396.htm,bad
22. ruiyangcn.com,bad
23. zkic.com,bad
24. adserving.favoritnetwork.com/eas?camp=19320;cre=mu&grpid=1738&tagi
d=618&nums=FGApbjFAAA,bad
25. cracks.vg/d1.php,bad
26. juicypussyclips.com,bad
27. nuptialimages.com,bad
28. andysgame.com,bad
29. bezproudoff.cz,bad
30. hotspot.cz,bad












FEATURE EXTRACTION
We have implemented python program to extract features from URL. Below are the
features that we have extracted for detection of phishing URLs.
1) Presence of IP address in URL:
If IP address present in URL then the feature is set to 1 else set to 0. Most of the benign
sites do not use IP address as an URL to download a webpage. Use of IP address in
URL indicates that attacker is trying to steal sensitive information.
2) Presence of @ symbol in URL:
If @ symbol present in URL then the feature is set to 1 else set to 0. Phishers add
special symbol @ in the URL leads the browser to ignore everything preceding the “@”
symbol and the real address often follows the “@” symbol
3) Number of dots in Hostname:
Phishing URLs have many dots in URL. For example
http://shop.fun.amazon.phishing.com, in this URL phishing.com is an actual domain
name, whereas use of “amazon” word is to trick users to click on it. Average number of
dots in benign URLs is 3. If the number of dots in URLs is more than 3 then the feature
is set to 1 else to 0.
4) Prefix or Suffix separated by (-) to domain:
If domain name separated by dash (-) symbol then feature is set to 1 else to 0. The dash
symbol is rarely used in legitimate URLs. Phishers add dash symbol (-) to the domain
name so that users feel that they are dealing with a legitimate webpage.
For example Actual site is http://www.onlineamazon.com but phisher can create another
fake website like http://www.online-amazon.com to confuse the innocent users
5) URL redirection:
11
If “//” present in URL path then feature is set to 1 else to 0. The existence of “//” within
the URL path means that the user will be redirected to another website.
6) HTTPS token in URL:
If HTTPS token present in URL then the feature is set to 1 else to 0. Phishers may add
the “HTTPS” token to the domain part of a URL in order to trick user.
7) Age of SSL Certificate:
The existence of HTTPS is very important in giving the impression of website
legitimacy. But minimum age of the SSL certificate of benign website is between 1 year
to 2 year.
8) URL Shortening Services “TinyURL”:
TinyURL service allows phisher to hide long phishing URL by making it short. The
goal is to redirect user to phishing websites. If the URL is crafted using shortening
services (like bit.ly) then feature is set to 1 else 0
9) Length of Host name:
Average length of the benign URLs is found to be a 25, If URL’s length is greater than
25 then the feature is set to 1 else to 0
10) Presence of sensitive words in URL:
Phishing sites use sensitive words in its URL so that users feel that they are dealing with
a legitimate webpage.
Below are the words that found in many phishing URLs :- 'confirm', 'account', 'banking',
'secure', 'ebyisapi', 'webscr', 'signin', 'mail', 'install', 'toolbar', 'backup', 'paypal',
'password', 'username', etc;
11) Number of slash in URL:
The number of slashes in benign URLs is found to be a 5; if number of slashes in URL
is greater than 5 then the feature is set to 1 else to 0. 
12
12) Presence of Unicode in URL:
Phishers can make a use of Unicode characters in URL to trick users to click on it. For
example the domain “xn--80ak6aa92e.com” is equivalent to "аррӏе.com". Visible URL
to user is "аррӏе.com" but after clicking on this URL, user will visit to “xn--
80ak6aa92e.com” which is a phishing site.
13) Information submission to Email:
Phisher might use “mail()” or “mailto:” functions to redirect the user’s information to
his personal email. If such functions are present in the URL then feature is set to 1 else
to 0.
14) URL of Anchor:
We have extracted this feature by crawling the source code oh the URL. URL of the
anchor is defined by tag. If the tag has a maximum number of hyperlinks which are
from the other domain then the feature is set to 1 else to 0
