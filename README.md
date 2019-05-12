## search for a website with a different proxy each time
This script automates the process of searching for a website via keywords
and the Bing search engine.... page after page.
<br><br>
Pass a complete URL and at least 1 keyword as command line arguments:
<br>
python proxy_crawler.py -u https://www.example.com -k keyword
<br><br>
or if you would like to see the browser while crawling add the -d flag
<br>
python proxy_crawler.py -u https://www.example.com -k keyword -d
<br><br>

It first scrapes a list of proxies from the web
using <a href="https://www.sslproxies.org">SSL Proxies</a>.
<br><br>
When the object is initialized in the constructor, the following method is called:
<br><br>
<code>self.scrape_socket()</code>
<br><br>
This saves each ip/port for each proxy server into a list after scraping the table
of proxy servers from sslproxies.org.
<br><br>
Then using a new socket from the list for each iteration, a random keyword is
searched for via https://www.bing.com until the desired website is found.
<br><br>
The website is then visited, and one link is randomly clicked within the website.
<br><br>
The bot is slowed down on purpose.
<br><br>
Along with Python 3 and geckodriver, the following are also required:
<pre>
    <code>
apt-get install xfvb
pip install pyvirtualdisplay
pip install selenium
pip install requests
    </code>
</pre>
<br><br>
I use this version of geckodriver on Ubuntu:
<br><br>
wget https://github.com/mozilla/geckodriver/releases/download/v0.23.0/geckodriver-v0.23.0-linux64.tar.gz
<br><br>
geckodriver should be saved somewhere in your PATH... ie: /usr/local/bin
<hr>
This was developed on Ubuntu 16.04.4 LTS with selenium/geckodriver and firefox 60.0
<b>Author: James Loye Colley  22MAY2018</b>
