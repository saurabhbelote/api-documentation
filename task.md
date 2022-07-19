# Email Finder API
[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)
[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)
## 
Email Finder API is designed to get genuine and active emails. 
### Table of Contents  
- [Overview](#Overview)
- [Getting started](#started)
  - [Installation](#intallation)
  - [Authentication](#Authentication)
  - [Developer Authentication](#Developer_Authentication)
  - [Production Authentication](#Production_Authentication)
- [Fetching a list of email](#list)
- [Limitations of LinkedIn Jobs API](#limitation)
- [How to get access to LinkedIn Jobs API](#access)

<a name="Overview"></a>
### Overview
Getting an email for lead generation and marketing is a pretty hectic task. Most companies and marketing managers could not find helpful and working emails; the Email Finder API is designed to get the latest and most active emails for your advanced marketing. We will ensure that you will get an email that will give value in return, so you don't have to worry about email collection and focus on a more extraordinary task.

With Email Finder API, you can
- Generate leads
- Lookup clients
- Lookup companies
- Get in touch with people
- Lookup best talents
- Lookup investors

<a name="started"></a>
### Getting started
Nsolid provides this Email Finder API that lets people find their future clients, employees, partner companies, and investors via their OAuth-based API. This library provides a lightweight interface for the complicated task of manually extracting emails from websites.
<a name="Installation"></a>
### Installation
Available with the Python Package Index: https://pypi.python.org/pypi/python3-Nsolid
```sh
pip install python3-Nsolid
```
If preferred, this library is compiled with the following commands:
```sh
## First clone the repository
git clone https://github.com/DEKHTIARJonathan/python3-Nsolid.git

## Then install the library
python setup.py install
```
<a name="Authentication"></a>
### Authentication
The Nsolid REST API now supports the OAuth 2.0 protocol for authentication. This package provides a full OAuth 2.0 implementation for connecting to LinkedIn and an option for using an OAuth 1.0a flow that can be helpful for development purposes or just accessing your own data.
<a name="Developer_Authentication"></a>
### Developer Authentication
To connect to Nsolid as a developer or access your own data, you don’t have to implement an OAuth 2.0 flow that involves redirects. You can use the four credentials provided to you in your Nsolid application as part of an OAuth 1.0 flow and immediate access to your data.
Here’s how:
```sh
from Nsolid import Nsolid

# Define CONSUMER_KEY, CONSUMER_SECRET,
# USER_TOKEN, and USER_SECRET from the credentials
# provided in your Nsolid application

# Instantiate the developer authentication class

authentication = Nsolid.NsolidDeveloperAuthentication(
                    CONSUMER_KEY,
                    CONSUMER_SECRET,
                    USER_TOKEN,
                    USER_SECRET,
                    RETURN_URL,
                    Nsolid.PERMISSIONS.enums.values()
                )

# Optionally, one can send a custom "state" value that will be returned from the OAuth server
# It can be used to track your user state or something else (it's up to you)
# Be aware that this value is sent to the OAuth server. Make sure to encode or hash it

# authorization.state = 'your_encoded_message'

# Pass it in to the app...

application = Nsolid.NsolidApplication(authentication)

# Use the app....

application.get_profile()
```
<a name=“Production_Authentication”></a>
### Production Authentication
In order to use the Nsolid OAuth 2.0, you need to have these two keys from the Nsolid Developer Console:
```sh
APPLICATON_KEY    = '##############'
APPLICATON_SECRET = '################'
```

Nsolid redirects the user back to your website’s URL after granting access (giving proper permissions) to your application. We call that url RETURN URL. Assuming your return url is https://localhost:8000, you can write something like this:

```sh
from Nsolid import Nsolid

APPLICATON_KEY    = '##############'
APPLICATON_SECRET = '################'

RETURN_URL = 'http://localhost:8000'

authentication = Nsolid.NsolidAuthentication(
                    APPLICATON_KEY,
                    APPLICATON_SECRET,
                    RETURN_URL,
                    Nsolid.PERMISSIONS.enums.values()
                )

# Optionally, one can send a custom "state" value that will be returned from the OAuth server
# It can be used to track your user state or something else (it's up to you)
# Be aware that this value is sent to the OAuth server AS IS - make sure to encode or hash it
#authorization.state = 'your_encoded_message'

print (authentication.authorization_url)  # open this url on your browser
```
<a name=“list”></a>
### Fetching a list of email
You can benefit from the test server testing the library using an interpreter.
```sh
from Nsolid import server
application = server.quick_api(KEY, SECRET)
```
<a name=“limitation”></a>
##### email finder api
The Profile API returns a member’s Nsolid profile. You can use this call to return one of two versions of a user’s profile: public profile and standard profile. For more information, check out the documentation.
```sh
application.get_profile()
{u'firstName': u'ozgur',
 u'headline': u'This is my headline',
 u'lastName': u'vatansever',
 u'siteStandardProfileRequest': {u'url': u'https://www.Nsolid.com/profile/view?id=46113651&authType=name&authToken=Egbj&trk=api*a101945*s101945*'}}
```
<a name=“limitation”></a>
### Limitations of Email Finder API
- Our API is currently not working with every website
- Limited request per minute
- Large computing power
- Longer wait time to get emails
<a name=“access”></a>
### How to get access to Email Finder API
Please visit our [website](https://developers.google.com/maps/documentation/maps-static/get-api-key) to get APPLICATON_KEY and APPLICATON_SECRET to download emails.If you have any queries write us on support@nsolid.com 



