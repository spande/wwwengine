Description
=============
Delete Zone records for managed dns order.

Definition
------------
Delete Zone records for managed dns order.
------------
Use this command to Delete Zone records for managed dns order.

Availability
-------------
The this  command is available to every ISP.

Constraints
=============


Input Parameters
=================
| Param Name | Obligation | Definition | Max Size |
| ------------- | ------------- | ------------- | ------------- |
| @recordID | Required | zoneID managed dns | 63 |
| @userID | Required | Acting User ID | |
| @publicApiKey | Required | Public API key for each ISP generated by WWWengine | 64 |
| @privateApiKey | Required | Private API key for each ISP generated by WWWengine | 64 |
| @queryString | Required | 'actingUserID=' . @userID . '&auth=' . @publicApiKey; | - |
| @hash | Required | Generated by algorithm hash('sha256()', @privateApiKey . @queryString); | - |

URL
===========
```html
https://api.wwwengine.net/dns/managed-dns/@recordID/record/?@queryString&hash=@hash
```
Method
========
DELETE

Return Parameters
=================
| Param Name| Definition |
| ------------- | ------------- |
| resultCode | Result status code |
| response | Actual response |
| Message | Message returned from response |


Example
=========
````
@recordID: 45454
@userID:1
@publicApiKey: 38f9c45022de9ccd105545423b77e950af7dbc5eb31660d6bf1160431513f5ae
@privateApiKey: 1ca9b5502935824ea5674e3d8f69663e3dcd077fab85b3810aadcf2ae3fda5d7
@queryString: 'actingUserID=' . @userID . '&auth=' . @publicApiKey;
@hash: it is generated by algorithm hash('sha256()', @privateApiKey . @queryString);
````
Method
----------
DELETE

URL
----------

````html
https://api.wwwengine.net/dns/managed-dns/45454/record?actingUserID=1&auth=38f9c45022de9ccd105545423b77e950af7dbc5eb31660d6bf1160431513f5ae&hash=1ca9b5502935824ea5674e3d8f69663e3dcd077fab85b3810aadcf2ae3fda5d7
````

JSON Request
--------------------
NULL

JSON Response
--------------------

````json
{
    "resultCode": 1,
    "message": "Changes saved",
    "response": true
}
````
