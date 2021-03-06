Description
=============

Definition
------------
Add Customer under an ISP.

Usage
------------
Use this command to add Customer under an ISP.

Availability
-------------
This command is available to every ISP.

Constraints
=============

The actingUserID, authKey and hash must be valid.

Input Parameters
=================

| Param Name | Obligation | Definition | Max Size |
| ------------- | ------------- | ------------- | ------------- |
|	type	|	Required	|	Type of user (Customer)	|		|
|	password	|	Required	|	Password of user	|	1/8/2020	|
|	email	|	Required	|	Email address of user	|	50	|
|	parentID	|	Required	|	ISP id under which user going to be register	|	-	|
|	autoSignup	|	Required	|	AutoSign up otion if enabled or not	|	65	|
|	buyingCurrency	|	Required	|	BuyingCurrency of user	|	50	|
|	allow	|	Required	|	Address of user	|		|
|	allowIPV	|	Required	|	Street of user	|		|
|	SocialPages	|	Optional	|	Soical pages of users	|		|
|	Soicalinfo	|	Optional	|	SocialUrls of usrs (eg. Facebook,google, twitter)	|		|
|	userInfo	|	Required	|	User's personal info	|		|
|	Date of birth	|	Required	|	Date of birth dd-mm-YY	|		|
|	contactInfo	|	Required	|	User's contact Info	|		|
|	PostalInfo	|	Required	|	User's postal Info	|		|
|	title	|	Required	|	Title of user (Mr./Mrs./Other)	|		|
|	organization	|	Required	|	Organization of user	|		|
|	firstName	|	Required	|	FirstName of user	|		|
|	LastName	|	Required	|	Last name of user	|		|
|	address	|	Required	|	Address of user	|		|
|	Street	|	Required	|	Streets1,Streets2,Streets3	|		|
|	city	|	Required	|	City of user	|		|
|	State	|	Required	|	State of user	|		|
|	countryCode	|	Required	|	Country Code of user	|		|
|	postalCode	|	Required	|	Postalof user	|		|
|	Voice	|	Required	|	Phone number of user	|		|
|	Number	|	Required	|	Phone number	|		|
|	ext	|	Required	|	Extention	|		|
|	cell	|	Required	|	User's Cell phone	|		|
|	Type	|	Required	|	Type of cellphone(e.g. Window)	|		|
|	Number	|	Required	|	Phone number	|		|
|	ext	|	Required	|	Extention cell number	|		|
|	countryCode	|	Required	|	Country Code of user's cell number	|		|
|	callInPin	|	Required	|	User's call in pin	|		|
|	Fax	|	Required	|	Fax number of user	|		|
|	number	|	Required	|	Fax number	|		|
|	ext	|	Required	|	Extention	|		|
|	Preference	|	Required	|	User's phone number preferance	|		|
|	phoneNoType	|	Required	|	User's phone numer type	|		|
|	@userID	|	Required	|	Acting User ID	|		|
|	@publicApiKey	|	Required	|	it is publick api key for each user generated by system.	|	64	|
|	@privateApiKey	|	Required	|	 It is private key of user.	|	64	|
|	@queryString	|	Required	|	'actingUserID=' . @userID . '&auth=' . @publicApiKey;	|	-	|
|	@hash	|	Required	|	it is  generated by algorithm hash('sha256()', @privateApiKey .  @queryString);	|	-	|
|	@tld	|	Required	|	Tld for which you are adding contact details	|	20	|

URL
===========
```html
https://api.wwwengine.net/user?@queryString&hash=@hash
```
Method
========
POST

Return Parameters
=================
| Param Name| Definition |
| ------------- | ------------- |
| resultCode | Result status code |
| response | Actual response |
| id | ID of data |

Example
=========

This is an example of adding a Customer under an ISP.

Method
----------

POST

URL
----------

````html
https://api.wwwengine.net/user?actingUserID=1&auth=38f9c45022de9ccd105545423b77e950af7dbc5eb31660d6bf1160431513f5ae&hash=1ca9b5502935824ea5674e3d8f69663e3dcd077fab85b3810aadcf2ae3fda5d7
````
JSON POST Parameters
--------------------

````json
{
    "type": "customer",
    "email": "abc.xyz@abc.org",
    "password": "abc@path6re",
    "parentID": "1",
    "autoSignup": 0,
    "buyingCurrency": "INR",
    "allow": [
        ""
    ],
    "allowIPV": [
        {
            "ipv4address": ""
        }
    ],
    "socialPages": [],
    "socialInfo": [],
    "userInfo": {
        "dateOfBirth": "1970-01-01"
    },
    "contactInfo": {
        "postalInfo": {
            "firstName": "Abc",
            "lastName": "Xyz",
            "title": "Mr.",
            "organization": "ABC Education Service, India",
            "address": {
                "street": [
                    "2nd Floor, 39/43 ABC Complex, Nesbit Road, Mazgaon",
                    "",
                    ""
                ],
                "city": "Mumbai",
                "postalCode": "400 010",
                "state": "Maharashtra",
                "countryCode": "IN"
            }
        },
        "voice": {
            "number": "+91.2554254",
            "countrycode": "29",
            "ext": ""
        },
        "callInPin": "1234"
    },
    "preferences": {
        "phoneNoType": "work"
    },
    "head": {
        "userIpAddress": "10.10.10.325"
    }
}
````

JSON POST Response
-----------

````json
{
    "resultCode": 1,
    "message": "Changes saved",
    "response": {
        "id": 47921
    }
}
````
