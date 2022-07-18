# Email Finder API
[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)
[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)
## 
Markdown is a lightweight markup language based on the formatting conventions
that people naturally use in email.

### Table of Contents  
- [What you can use Email finder API for](#use)
- [Getting started](#started)
  - [Installation](#intallation)
  - [Authentication](#Authentication)
  - [Developer Authentication](#Developer_Authentication)
  - [Production Authentication](#Production_Authentication)
- [Fetching a list of email](#list)
- [Limitations of LinkedIn Jobs API](#limitation)
- [How to get access to LinkedIn Jobs API](#access)

<a name="use"></a>
### What you can use Email finder API for
The LinkedIn REST API now supports the OAuth 2.0 protocol for authentication. This package provides a full OAuth 2.0 implementation for connecting to LinkedIn as well as an option for using an OAuth 1.0a flow that can be helpful for development purposes or just accessing your own data.

<a name="started"></a>
### Getting started
LinkedIn provides a service that lets people bring their LinkedIn profiles and networks with them to your site or application via their OAuth based API. This library provides a lightweight interface over a complicated LinkedIn OAuth based API to make it for python programmers easy to use.
<a name="Installation"></a>
### Installation
Available with the Python Package Index: https://pypi.python.org/pypi/python3-linkedin
```sh
pip install python3-linkedin
```
If prefered, the library can be compiled with following commands:
```sh
## First clone the repository
git clone https://github.com/DEKHTIARJonathan/python3-linkedin.git

## Then install the library
python setup.py install
```

### Authentication
The LinkedIn REST API now supports the OAuth 2.0 protocol for authentication. This package provides a full OAuth 2.0 implementation for connecting to LinkedIn as well as an option for using an OAuth 1.0a flow that can be helpful for development purposes or just accessing your own data.
### Developer Authentication
To connect to LinkedIn as a developer or just to access your own data, you don’t even have to implement an OAuth 2.0 flow that involves redirects. You can simply use the 4 credentials that are provided to you in your LinkedIn appliation as part of an OAuth 1.0a flow and immediately access your data. Here’s how:
```sh
from linkedin import linkedin

# Define CONSUMER_KEY, CONSUMER_SECRET,
# USER_TOKEN, and USER_SECRET from the credentials
# provided in your LinkedIn application

# Instantiate the developer authentication class

authentication = linkedin.LinkedInDeveloperAuthentication(
                    CONSUMER_KEY,
                    CONSUMER_SECRET,
                    USER_TOKEN,
                    USER_SECRET,
                    RETURN_URL,
                    linkedin.PERMISSIONS.enums.values()
                )

# Optionally one can send custom "state" value that will be returned from OAuth server
# It can be used to track your user state or something else (it's up to you)
# Be aware that this value is sent to OAuth server AS IS - make sure to encode or hash it

# authorization.state = 'your_encoded_message'

# Pass it in to the app...

application = linkedin.LinkedInApplication(authentication)

# Use the app....

application.get_profile()
```
### Production Authentication
In order to use the LinkedIn OAuth 2.0, you need to have these two keys from the from the LinkedIn Developer Console:
```sh
APPLICATON_KEY    = '##############'
APPLICATON_SECRET = '################'
```

LinkedIn redirects the user back to your website’s URL after granting access (giving proper permissions) to your application. We call that url RETURN URL. Assuming your return url is https://localhost:8000, you can write something like this:

```sh
from linkedin import linkedin

APPLICATON_KEY    = '##############'
APPLICATON_SECRET = '################'

RETURN_URL = 'http://localhost:8000'

authentication = linkedin.LinkedInAuthentication(
                    APPLICATON_KEY,
                    APPLICATON_SECRET,
                    RETURN_URL,
                    linkedin.PERMISSIONS.enums.values()
                )

# Optionally one can send custom "state" value that will be returned from OAuth server
# It can be used to track your user state or something else (it's up to you)
# Be aware that this value is sent to OAuth server AS IS - make sure to encode or hash it
#authorization.state = 'your_encoded_message'

print (authentication.authorization_url)  # open this url on your browser
```
### Fetching a list of email
For testing the library using an interpreter, you can benefit from the test server.
```sh
from linkedin import server
application = server.quick_api(KEY, SECRET)
```
##### email finder api
The Profile API returns a member’s LinkedIn profile. You can use this call to return one of two versions of a user’s profile which are public profile and standard profile. For more information, check out the documentation.
```sh
application.get_profile()
{u'firstName': u'ozgur',
 u'headline': u'This is my headline',
 u'lastName': u'vatansever',
 u'siteStandardProfileRequest': {u'url': u'https://www.linkedin.com/profile/view?id=46113651&authType=name&authToken=Egbj&trk=api*a101945*s101945*'}}
```

### Limitations of Email Finder API
This will print the authorization url to the screen. Go into that URL using a browser to grant access to the application. After you do so, the method will return with an API object you can now use.
### How to get access to Email Finder API
This will print the authorization url to the screen. Go into that URL using a browser to grant access to the application. After you do so, the method will return with an API object you can now use.
### What you can use Email Finder API
This will print the authorization url to the screen. Go into that URL using a browser to grant access to the application. After you do so, the method will return with an API object you can now use.
Dillinger is a cloud-enabled, mobile-ready, offline-storage compatible,
AngularJS-powered HTML5 Markdown editor.


                                                                              


