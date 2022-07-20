
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
    - [Get user emails](#gmails)
    - [Get company emails](#Cgmails)

- [Limitations of Email Finder API](#limitation)

- [How to get access to Email Finder API](#access)

- [Errors](#errors)

- [access](#access)

  

<a  name="Overview"></a>

### Overview

Getting an email for lead generation and marketing is a pretty hectic task. Most companies and marketing managers could not find helpful and working emails; the Email Finder API is designed to get the latest and most active emails for your advanced marketing. We will ensure that you will get an email that will give value in return, so you don't have to worry about email collection and focus on a more extraordinary task.

  

With Email Finder API, you can

- Generate leads

- Lookup clients

- Lookup companies

- Get in touch with people

- Lookup best talents

- Lookup investors

  

<a  name="started"></a>

### Getting started

Nsolid provides this Email Finder API that lets people find their future clients, employees, partner companies, and investors via their [OAuth-based API.](https://developer.okta.com/blog/2017/06/21/what-the-heck-is-oauth) Nsolid provides a lightweight library to use API for the complicated task of manually extracting emails from websites.

<a  name="Installation"></a>

### Installation

Available with the Python Package Index: https://pypi.python.org/pypi/python3-Nsolid

```sh

pip install python3-Nsolid

```

To install this package with conda run one of the following:

```sh

conda install -c conda-forge/label/python3-Nsolid

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

The Email Finder API now supports the [OAuth 2.0 protocol](https://auth0.com/docs/authenticate/protocols/oauth) for authentication. This package provides a full OAuth 2.0 implementation for connecting to Nsolid and an option for using an [OAuth 1.0a](https://oauth.net/core/1.0a/) flow that can be helpful for development purposes or just accessing credentials.

<a name="Developer_Authentication"></a>

### Developer Authentication

To connect to Nsolid as a developer or access your own credentials, you don’t have to implement an OAuth 2.0 flow that involves redirects. You can use the four credentials provided to you in your Nsolid application [(get here)](https://developers.google.com/maps/documentation/maps-static/get-api-key) as part of an OAuth 1.0 a flow and immediate access to your credentials. you can access creadentials here

Here’s how:

```sh

from Nsolid import Nsolid

  

# Define CONSUMER_KEY, CONSUMER_SECRET from the credentials

# USER_TOKEN, and USER_SECRET from the credentials

# provided in your Nsolid application

  

# Instantiate the developer authentication class

  

authentication = Nsolid.NsolidDeveloperAuthentication(

CONSUMER_KEY,

CONSUMER_SECRET,

USER_TOKEN,

USER_SECRET,

Nsolid.PERMISSIONS.enums.values()

)

  

# Optionally, one can send a custom "state" value that will be returned from the OAuth server

# It can be used to track your user state or something else (it's up to you)

# Be aware that this value is sent to the OAuth server. Make sure to encode or hash it

  

# authorization.state = 'your_encoded_message'

  

# Pass it in to the app...

  

application = Nsolid.NsolidApplication(authentication)

  

# Use the app....

  

application.get_emails()

```

<a  name=“Production_Authentication”></a>

### Production Authentication

In order to use the Nsolid OAuth 2.0, you need to have these two keys from the [Nsolid Developer Console:](https://developers.google.com/maps/documentation/maps-static/get-api-key)

```sh

APPLICATON_KEY = '##############'

APPLICATON_SECRET = '################'

```

  

Nsolid redirects the user back to your code after granting access (giving proper permissions) to your Code. We call that url RETURN URL. Assuming your return url is https://Nsolid/authentication/application_key, you can write something like this:

  

```sh

from Nsolid import Nsolid

  

APPLICATON_KEY = '##############'

APPLICATON_SECRET = '################'

  

RETURN_URL = 'https://Nsolid/authentication/application_key'

  

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

  

print (authentication.authorization_url) # open this url on your browser

```

<a  name=“list”></a>

### Fetching a list of email

You can benefit from the test server testing the library using an interpreter.

```sh

from Nsolid import server

application = server.quick_api(KEY, SECRET)

```



### Email finder api

The email finder API returns the email address on the website. You can use this Get up to 10 emails per minute.
<a  name=gmails></a>
### Get user gmail
This API helps download user emails containing @gmail.com (e.g., example@gmail.com). Our API searches into websites and filters emails return  users emails.

URL Parameters

| Parameter   | Required | Description | Example |
| ----------  | --------------------- |-------|------|
| url         | True | Enter the url of website  |www.example.com|
| No  | True |No of emails to download| 10|

  

```sh

application.get_email('www.example.com', '10')

{'1': 'ozgur@gmail.com',

'2': 'headline@gmail.com',

'3': 'vatansever@gmail.com',

'4': 'shantaram@gmail.com'

'5': 'shantabai@gmail.com'

'6': 'jamunabai@gmail.com'

'7': 'dadabhaubelote@gmail.com'

'8': 'rajkuamrmar@gmail.com'

'9': 'suunypaji@gmail.com'

'10': 'kapilsharma@gmail.com'

}

```
<a  name="Cgmails"></a>
### Get Company emails

This API helps download user emails containing @example.com (e.g., abc@example.com). Our API searches into websites and filters emails to return company emails.

URL Parameters

| Parameter   | Required | Description | Example |
| ----------  | --------------------- |-------|------|
| url         | True | Enter the url of the website |www.example.com|
| No of email | False |No of the emails | 10|
| email | True |example of ompany email  | abc@example.com|


  

```sh

application.get_email('www.example.com', '10', 'abc@example.com')

{'1': 'ozgur@example.com',

'2': 'headline@example.com',

'3': 'vatansever@exmple.com',

'4': 'shantaram@example.com'

'5': 'shantabai@example.com'

'6': 'jamunabai@example.com'

'7': 'dadabhaubelote@example.com'

'8': 'rajkuamrmar@example.com'

'9': 'suunypaji@example.com'

'10': 'kapilsharma@example.com'

}

```

<a  name=“limitation”></a>

### Limitations of Email Finder API

- Our API is currently not working with every website

- Limited request per minute

- Large computing power

- Longer wait time to get emails

  

<a  name="errors"></a>

### Errors

| HTTP Code     | Description   |
| ------------- | ------------- |
| 400           | Invalid parameters provided. Please Contact us for assistance      |
| 401           | Invalid API Key   |
| 403           | You have run out of credits  |
| 404           | Enrichment failed, please retry.  |
| 503           | There is an error with our API. Please [Contact us]() for assistance      |
| 500           | Rate limited. Please retry  |



<a  name=“access”></a>

### Get access to Email Finder API 

Please visit our [website](https://developers.google.com/maps/documentation/maps-static/get-api-key) to get APPLICATON_KEY and APPLICATON_SECRET. If you have any queries write us on support@nsolid.com