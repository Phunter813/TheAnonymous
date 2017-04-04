# Get Your Attendance 
+  get your Update Attendance with one click 
+  reason of doing it? cause it is the most anticipating topic amoung us.
+  talking about the work, I did the request by `Robobrowser` wiz. another of those module of Python composed of `Mechanize`,  `requests`, `webtests`, `BeautifulSoup`, `requests` etc.. The issue is to get the attendace tab, which is protected by the some erp's .Net security. my Objective is to introduce it to this subject and help you interact with this field, and find solution to the erp problem if you already got you hands dabbed in it. 
+  click on `url` after you run the code on the console which is provided after the unexpected response from the `Attendace` tab. 
+  for further explanation contact the E-mail on the notice, here is the code.

```Python 3
from robobrowser import RoboBrowser
import requests

start = requests.session()

token = '3BA8C6EB'
token_1 = '/wEPDwUKLTI0NTk0MzIwMw8WAh4PQ2hhaXJtYW5NZXNzYWdlBRkxMDAxNV9DaGFpcm1hbk1lc3NhZ2UuanBnFgICAw9kFgoCAQ8PFgIeCEltYWdlVXJsBTV+XFVwbG9hZGVkRmlsZVxOb3RpZmljYXRpb25cMTAwMTVfQ2hhaXJtYW5NZXNzYWdlLmpwZ2RkAgMPDxYCHgRUZXh0BZwCVGhlIE5vcnRoQ2FwIFVuaXZlcnNpdHkgd2FzIGZvdW5kZWQgaW4gMTk5NiwgdG8gcHJvbW90ZSBleGNlbGxlbmNlIGluIFRlY2huaWNhbCBhbmQgTWFuYWdlbWVudCBlZHVjYXRpb24gYnkgRWR1Y2F0ZSBJbmRpYSBTb2NpZXR5LCByZWdpc3RlcmVkIHVuZGVyIHRoZSBSZWdpc3RyYXRpb24gb2YgU29jaWV0aWVzIEFjdCBvZiAxODYwLg0KVGhlIFVuaXZlcnNpdHkgd2FzIGNvbmNlaXZlZCBhcyBJbnN0aXR1dGUgb2YgVGVjaG5vbG9neSBhbmQgTWFuYWdlbWVudCBpbiByZXNwb25zZSB0byB0aC4uLi5kZAIHDw8WAh8BBTh+L0hhbmRsZXIvQ29sbGVnZUxvZ28uYXNoeD9Db2xsZWdlU3lzQ29kZT0xMDAxNSZVU2VySWQ9MGRkAgkPDxYCHwIFF1RIRSBOT1JUSENBUCBVTklWRVJTSVRZZGQCFQ8PFgIfAgUXVEhFIE5PUlRIQ0FQIFVOSVZFUlNJVFlkZBgBBR5fX0NvbnRyb2xzUmVxdWlyZVBvc3RCYWNrS2V5X18WAQUPQ2hrU3RheVNpZ25lZEluxX0otmSpE8Fty+bH2y3L6MS+l2A='

# some predeclared data
stuff = {
    '__VIEWSTATEGENERATOR': token,
    'btnLogIn': 'Login',
    '__VIEWSTATE': token_1, 'ASP.NET_SessionId': 'xgrun2iptyyhkn45zvecxo55',

}

# assigning the headers
start.headers = stuff

browser = RoboBrowser(parser='lxml', session=start,
                      user_agent='Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/57.0.2987.98 Safari/537.36')
browser.open('http://erp.ncuindia.edu/')
sign_up = browser.get_form(action='Welcome_iie.aspx')
sign_up.fields['tbUserName'].value = 'YOUR_ID'
sign_up.fields['tbPassword'].value = 'YOUR_PASSWORD'
opens = browser.submit_form(sign_up, submit='Login')
news = browser.parsed  # check that the login was successful

stuff = {
    'ctl00$ContentPlaceHolder1$rptAttendance$ctl01$hfSubjectId" id="ctl00_ContentPlaceHolder1_rptAttendance_ctl01_hfSubjectId': '1001711341',
    'ctl00$ContentPlaceHolder1$rptAttendance$ctl02$hfSubjectId" id="ctl00_ContentPlaceHolder1_rptAttendance_ctl02_hfSubjectId': '1001710915',
    'ctl00$ContentPlaceHolder1$rptAttendance$ctl03$hfSubjectId" id="ctl00_ContentPlaceHolder1_rptAttendance_ctl03_hfSubjectId': '1001710100',
    'ctl00$ContentPlaceHolder1$rptAttendance$ctl04$hfSubjectId" id="ctl00_ContentPlaceHolder1_rptAttendance_ctl04_hfSubjectId': '1001710094',
    'ctl00$ContentPlaceHolder1$rptAttendance$ctl05$hfSubjectId" id="ctl00_ContentPlaceHolder1_rptAttendance_ctl05_hfSubjectId': '1001710916',
    'ctl00$ContentPlaceHolder1$rptAttendance$ctl06$hfSubjectId" id="ctl00_ContentPlaceHolder1_rptAttendance_ctl06_hfSubjectId': '1001710093',
    }


new_cookies = {'__utma': '239018655.581728463.1490460449.1490460449.1490460449.1',
    '__utmc': '239018655',
    '__utmz': '239018655.1490460449.1.1.utmcsr=(direct)|utmccn=(direct)|utmcmd=(none)',
    'ASP.NET_SessionId': 'itus5e55cs5xd0q1opquwjz2'}

url_of_brow = browser.url
response = browser.session.post(url=url_of_brow, data=stuff)
browser._update_state(response)
browser.session.cookies.update(new_cookies)
browser.session.get('http://erp.ncuindia.edu/Student/StudentAttendanceView.aspx?SID=vU1sRsNsheScuBc7TiYnGw==|y8zwDmaAchA=')
browser.session.get('http://erp.ncuindia.edu/fancybox/jquery.fancybox-1.3.4.css')
browser.session.get('http://erp.ncuindia.edu/NYSAJS/jquery-1.5.1.min.js')
browser.session.get('http://erp.ncuindia.edu/fancybox/jquery.fancybox-1.3.4.pack.js')
browser.session.get('http://erp.ncuindia.edu/Style/Form.css')
browser.session.get('http://erp.ncuindia.edu/Style/Extra.css')
browser.session.get('http://erp.ncuindia.edu/Style/Main_BlueTheme.css')
browser.session.get('http://erp.ncuindia.edu/Style/pagePrint.css')
browser.session.get('http://erp.ncuindia.edu/WebResource.axd?d=i_-cXTuVQ_I-_qn7PlgBepqfeJe94XdOIOMIn40Y-PPY_LY0KQNzy14y143prKpS5LoRk_kH2aJeOY0WhcBCXYgT7gQ1&t=635315356158437500')
browser.session.get('http://erp.ncuindia.edu/ScriptResource.axd?d=xKxP0b-Pc-PzukjulBCARyg6yC0XppkkI94TT_i0Ee0_bhYBXQMfyM69HnPtXXz1lF-557srkSfsvqozNP1ZMiUu3MWPlmVUT-_YareA4NkDHAP1Yle6sPbtXumMCG8WKU2IkNNsH3GpvAVqM2taXvSggJQ1&t=1cd82cb2')
browser.session.get('http://erp.ncuindia.edu/ScriptResource.axd?d=yVPaNCaujFZQxn2hft66lLmxJzIHOiYuTmJpV3hnpm5fouH6k2VkeatEZSHpou1nNyVa99yp6iUkDGzatzGwiXGxreOtSx0QaB-tWfNJFEAClzWj6ZMHjnoAl0cWgrTESjyXyGkHO4emByVJzvoJZ8JlVmk2T58XJyMOaO3UgSRJ1e1A0&t=1cd82cb2')
browser.session.get('http://erp.ncuindia.edu/Handler/CollegeLogo.ashx?CollegeSysCode=10017&USerId=0')
browser.session.get('http://erp.ncuindia.edu/Handler/StudentPhoto.ashx?Mode=A&EID=100171416245&EInst=10017')

new_link = browser.follow_link(browser.get_link('Attendance'), data=stuff)
browser.session.get('http://erp.ncuindia.edu/Student/StudentAttendanceView.aspx?SID=JQg5rX6jt7HRk993gwIZQw==|b3cyZF04Rp4=')
browser.session.get('http://erp.ncuindia.edu/fancybox/jquery.fancybox-1.3.4.css')

print(browser.parsed)
print('........................\nabove is the response from website')
print('........................\nhere is the url of webpage')
print(browser.url)
```
