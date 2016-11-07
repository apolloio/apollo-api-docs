

# Core REST API

ZenProspect's Core REST API lets you interact with core ZenProspect objects like contacts, accounts, and sequences.

## Accounts



## Activities


## Calls


## Contacts

### Edit Contact
```shell
curl "https://www.zenprospect.com/api/v1/contacts/54a3b5a8746869367615770c" 
-H 'Content-Type: application/json' 
-H "Authorization: testzenprospectapikey"
-X PUT 
-d '{
  "first_name":"Bob",
  "custom_fields": {
    "Personalized Snippet": "Blah blah blah blah."
  }
}' 

```


#### Query Parameters

Parameter | Description 
--------- | ----------- 
first_name | 
last_name | 
custom_fields | A JSON object/hash of the custom fields (see example above). 
TODO | about 30 more fields that can be edited... TODO

## Customer Profiles


## Mailings


## Sequences


## Tasks


## Templates


## Users

