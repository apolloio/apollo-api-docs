# Enrichment API

## Bulk people enrichment

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "reveal_personal_emails": true,
    "details": [
        {
            "first_name": "Tim",
            "last_name": "Zheng",
            "domain": "apollo.io",
            "email": "tim@apollo.io",
            "hashed_email": "8d935115b9ff4489f2d1f9249503cadf",
            "organization_name": "Apollo",
            "linkedin_url": "http://www.linkedin.com/in/tim-zheng-677ba010"
        },
        {
            "first_name": "Roy",
            "last_name": "Chung",
            "email": "roy@apollo.io",
            "hashed_email": "97817c0c49994eb500ad0a5e7e2d8aed51977b26424d508f66e4e8887746a152",
            "organization_name": "Apollo",
            "linkedin_url": "http://www.linkedin.com/in/royychung"
        }
    ]
}' "https://api.apollo.io/api/v1/people/bulk_match"
```

```python
import requests

url = "https://api.apollo.io/api/v1/people/bulk_match"

data = {
    "api_key": "YOUR API KEY HERE",
    "reveal_personal_emails": true,
    "details": [
        {
            "first_name": "Tim",
            "last_name": "Zheng",
            "domain": "apollo.io",
            "hashed_email": "8d935115b9ff4489f2d1f9249503cadf",
            "email": "tim@apollo.io",
            "organization_name": "Apollo"
            "linkedin_url": "http://www.linkedin.com/in/tim-zheng-677ba010"
        },
        {
            "first_name": "Roy",
            "last_name": "Chung",
            "email": "roy@apollo.io",
            "hashed_email": "97817c0c49994eb500ad0a5e7e2d8aed51977b26424d508f66e4e8887746a152",
            "organization_name": "Apollo"
            "linkedin_url": "http://www.linkedin.com/in/royychung"
        }
    ]
}

headers = {
    'Cache-Control': 'no-cache',
    'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, json=data)

print(response.text)
```

> Sample response:

```json
{
    "status": "success",
    "error_code": null,
    "error_message": null,
    "total_requested_enrichments": 2,
    "unique_enriched_records": 2,
    "missing_records": 0,
    "credits_consumed": 1.01,
    "matches": [
        {
            "id": "6453e9bd8f50d40001f1e348",
            "first_name": "Tim",
            "last_name": "Zheng",
            "name": "Tim Zheng",
            "linkedin_url": "http://www.linkedin.com/in/tim-zheng-677ba010",
            "title": "Founder & CEO",
            "email_status": null,
            "photo_url": "https://media.licdn.com/dms/image/D5603AQEFiVRxq2aFCg/profile-displayphoto-shrink_200_200/0/1676521918175?e=1701907200&v=beta&t=6QqL_xwsDybj-FIUTr6XaEeLyrHxs7QS-IHSbVtYCak",
            "twitter_url": null,
            "github_url": null,
            "facebook_url": null,
            "extrapolated_email_confidence": null,
            "headline": "Founder & CEO at Apollo",
            "email": "tim@apollo.io",
            "organization_id": "5e66b6381e05b4008c8331b8",
            "employment_history": [
                {
                    "_id": "651e57392998d400013ac5bd",
                    "created_at": null,
                    "current": true,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": null,
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": "5e66b6381e05b4008c8331b8",
                    "organization_name": "Apollo",
                    "raw_address": null,
                    "start_date": "2016-01-01",
                    "title": "Founder & CEO",
                    "updated_at": null,
                    "id": "651e57392998d400013ac5bd",
                    "key": "651e57392998d400013ac5bd"
                },
                {
                    "_id": "651e57392998d400013ac5be",
                    "created_at": null,
                    "current": false,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": "2015-01-01",
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": null,
                    "organization_name": "Braingenie",
                    "raw_address": null,
                    "start_date": "2011-01-01",
                    "title": "Founder & CEO",
                    "updated_at": null,
                    "id": "651e57392998d400013ac5be",
                    "key": "651e57392998d400013ac5be"
                },
                {
                    "_id": "651e57392998d400013ac5bf",
                    "created_at": null,
                    "current": false,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": "2011-01-01",
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": "54a22f23746869331840e813",
                    "organization_name": "Citadel Investment Group",
                    "raw_address": null,
                    "start_date": "2011-01-01",
                    "title": "Investment & Trading Associate",
                    "updated_at": null,
                    "id": "651e57392998d400013ac5bf",
                    "key": "651e57392998d400013ac5bf"
                },
                {
                    "_id": "651e57392998d400013ac5c0",
                    "created_at": null,
                    "current": false,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": "2010-09-01",
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": "54a1216169702d7fe6dfca02",
                    "organization_name": "The Boston Consulting Group",
                    "raw_address": null,
                    "start_date": "2010-08-01",
                    "title": "Summer Associate",
                    "updated_at": null,
                    "id": "651e57392998d400013ac5c0",
                    "key": "651e57392998d400013ac5c0"
                },
                {
                    "_id": "651e57392998d400013ac5c1",
                    "created_at": null,
                    "current": false,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": "2010-08-01",
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": "64cca0e9f6489200019570a1",
                    "organization_name": "Goldman Sachs",
                    "raw_address": null,
                    "start_date": "2010-06-01",
                    "title": "Summer Analyst",
                    "updated_at": null,
                    "id": "651e57392998d400013ac5c1",
                    "key": "651e57392998d400013ac5c1"
                },
                {
                    "_id": "651e57392998d400013ac5c2",
                    "created_at": null,
                    "current": false,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": "2010-02-01",
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": "54a1a06274686945fa1ffc02",
                    "organization_name": "Jane Street",
                    "raw_address": null,
                    "start_date": "2009-12-01",
                    "title": "Trading Intern",
                    "updated_at": null,
                    "id": "651e57392998d400013ac5c2",
                    "key": "651e57392998d400013ac5c2"
                }
            ],
            "state": "California",
            "city": "San Francisco",
            "country": "United States",
            "organization": {
                "id": "5e66b6381e05b4008c8331b8",
                "name": "Apollo.io",
                "website_url": "http://www.apollo.io",
                "blog_url": null,
                "angellist_url": null,
                "linkedin_url": "http://www.linkedin.com/company/apolloio",
                "twitter_url": "https://twitter.com/meetapollo/",
                "facebook_url": "https://www.facebook.com/MeetApollo",
                "primary_phone": {
                    "number": "+1415-640-9303",
                    "source": "Owler",
                    "country_code_added_from_hq": true
                },
                "languages": [],
                "alexa_ranking": 3514,
                "phone": "+1415-640-9303",
                "linkedin_uid": "18511550",
                "founded_year": 2015,
                "publicly_traded_symbol": null,
                "publicly_traded_exchange": null,
                "logo_url": "https://zenprospect-production.s3.amazonaws.com/uploads/pictures/64beb2c5e966df0001384ac1/picture",
                "crunchbase_url": null,
                "primary_domain": "apollo.io",
                "sanitized_phone": "+14156409303",
                "industry": "information technology & services",
                "keywords": [
                    "sales engagement",
                    "lead generation",
                    "predictive analytics",
                    "lead scoring",
                    "sales strategy",
                    "conversation intelligence",
                    "sales enablement",
                    "lead routing",
                    "sales development",
                    "email engagement",
                    "revenue intelligence",
                    "sales operations",
                    "demand generation"
                ],
                "estimated_num_employees": 1200,
                "industries": [
                    "information technology & services"
                ],
                "secondary_industries": [],
                "snippets_loaded": true,
                "industry_tag_id": "5567cd4773696439b10b0000",
                "industry_tag_hash": {
                    "information technology & services": "5567cd4773696439b10b0000"
                },
                "retail_location_count": 0,
                "raw_address": "535 mission street, san francisco, california, united states",
                "street_address": "535 Mission Street",
                "city": "San Francisco",
                "state": "California",
                "postal_code": "94105",
                "country": "United States"
            },
            "account_id": "64dcd04136650700bc538f61",
            "account": {
                "id": "64dcd04136650700bc538f61",
                "name": "Apollo",
                "website_url": "http://www.apollo.io",
                "blog_url": null,
                "angellist_url": null,
                "linkedin_url": "http://www.linkedin.com/company/apolloio",
                "twitter_url": "https://twitter.com/meetapollo/",
                "facebook_url": "https://www.facebook.com/MeetApollo",
                "primary_phone": {
                    "number": "+1415-640-9303",
                    "source": "Owler",
                    "country_code_added_from_hq": true
                },
                "languages": [],
                "alexa_ranking": 3514,
                "phone": "+1(202) 374-1312",
                "linkedin_uid": "18511550",
            },
            "phone_numbers": [
                {
                    "raw_number": "+1415-640-9303",
                    "sanitized_number": "+14156409303",
                    "type": "work_hq",
                    "position": 0,
                    "status": "no_status",
                    "dnc_status": null,
                    "dnc_other_info": null
                }
            ],
            "intent_strength": null,
            "show_intent": false,
            "revealed_for_current_team": true,
            "hashed_email": "8d935115b9ff4489f2d1f9249503cadf",
            "personal_emails": [],
            "departments": [
                "c_suite"
            ],
            "subdepartments": [
                "executive",
                "founder"
            ],
            "functions": [
                "entrepreneurship"
            ],
            "seniority": "founder"
        },
        {
            "id": "611c931f1b404b00014e884c",
            "first_name": "Roy",
            "last_name": "Chung",
            "name": "Roy Chung",
            "linkedin_url": "http://www.linkedin.com/in/royychung",
            "title": "Entrepreneur",
            "email_status": null,
            "photo_url": "https://media.licdn.com/dms/image/C5603AQFVolaIjLeG3g/profile-displayphoto-shrink_800_800/0/1517707907539?e=1701302400&v=beta&t=JFd1eHlKnvAfz77El2lIOAmRFZpmvz6uiRzpP1hqs70",
            "twitter_url": "https://twitter.com/r1strategy",
            "github_url": null,
            "facebook_url": null,
            "extrapolated_email_confidence": null,
            "headline": "Ideating & Optimizing 💪📈🧪️",
            "email": "roy@apollo.io",
            "organization_id": "627b71bc1c295500a55e4928",
            "employment_history": [
                {
                    "_id": "651534cefdb6690001d16b63",
                    "created_at": null,
                    "current": true,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": null,
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": "627b71bc1c295500a55e4928",
                    "organization_name": "Stealth",
                    "raw_address": null,
                    "start_date": "2022-07-01",
                    "title": "Entrepreneur",
                    "updated_at": null,
                    "id": "651534cefdb6690001d16b63",
                    "key": "651534cefdb6690001d16b63"
                },
                {
                    "_id": "651534cefdb6690001d16b64",
                    "created_at": null,
                    "current": true,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": null,
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": "5dba6791a2edd900e79a4b48",
                    "organization_name": "Flow Research Collective",
                    "raw_address": null,
                    "start_date": "2019-11-01",
                    "title": "Strategy",
                    "updated_at": null,
                    "id": "651534cefdb6690001d16b64",
                    "key": "651534cefdb6690001d16b64"
                },
                {
                    "_id": "651534cefdb6690001d16b65",
                    "created_at": null,
                    "current": true,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": null,
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": "5b1314cda6da98dcb8928c42",
                    "organization_name": "Pioneer Fund",
                    "raw_address": null,
                    "start_date": "2021-01-01",
                    "title": "Venture Partner",
                    "updated_at": null,
                    "id": "651534cefdb6690001d16b65",
                    "key": "651534cefdb6690001d16b65"
                },
                {
                    "_id": "651534cefdb6690001d16b66",
                    "created_at": null,
                    "current": true,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": null,
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": "60c554c05c097d00d9155e20",
                    "organization_name": "JoyFund",
                    "raw_address": null,
                    "start_date": "2019-05-01",
                    "title": "Venture Partner",
                    "updated_at": null,
                    "id": "651534cefdb6690001d16b66",
                    "key": "651534cefdb6690001d16b66"
                },
                {
                    "_id": "651534cefdb6690001d16b67",
                    "created_at": null,
                    "current": true,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": null,
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": "5e562f92440ea5000178a0b1",
                    "organization_name": "Lionheart Ventures",
                    "raw_address": null,
                    "start_date": "2020-01-01",
                    "title": "Venture Partner",
                    "updated_at": null,
                    "id": "651534cefdb6690001d16b67",
                    "key": "651534cefdb6690001d16b67"
                }
            ],
            "state": "New York",
            "city": "New York",
            "country": "United States",
            "organization": {
                "id": "627b71bc1c295500a55e4928",
                "name": "Stealth",
                "website_url": null,
                "blog_url": null,
                "angellist_url": null,
                "linkedin_url": "http://www.linkedin.com/company/ice9",
                "twitter_url": null,
                "facebook_url": null,
                "primary_phone": {},
                "languages": [],
                "alexa_ranking": null,
                "phone": null,
                "linkedin_uid": "80022788",
                "founded_year": null,
                "publicly_traded_symbol": null,
                "publicly_traded_exchange": null,
                "logo_url": "https://zenprospect-production.s3.amazonaws.com/uploads/pictures/645166e576ec8b00010ea120/picture",
                "crunchbase_url": null,
                "primary_domain": null,
                "industry": "venture capital & private equity",
                "keywords": [],
                "estimated_num_employees": 110,
                "industries": [
                    "venture capital & private equity"
                ],
                "secondary_industries": [],
                "snippets_loaded": true,
                "industry_tag_id": "5567e1587369641c48370000",
                "industry_tag_hash": {
                    "venture capital & private equity": "5567e1587369641c48370000"
                },
                "retail_location_count": 0,
                "raw_address": "Dallas, Texas",
                "street_address": "",
                "city": "Dallas",
                "state": "Texas",
                "postal_code": null,
                "country": "United States"
            },
            "intent_strength": null,
            "show_intent": false,
            "revealed_for_current_team": true,
            "hashed_email": "97817c0c49994eb500ad0a5e7e2d8aed51977b26424d508f66e4e8887746a152",
            "personal_emails": [
                "royychung@gmail.com"
            ],
            "departments": [
                "c_suite"
            ],
            "subdepartments": [
                "founder"
            ],
            "functions": [
                "entrepreneurship"
            ],
            "seniority": "entry"
        }
    ]
}
```

This endpoint enriches people information in bulk - the more information you pass in, the more likely we can find a match. 

Up to 10 records can be enriched at the same time through this endpoint. It will deduct 1 email credit for each email found.

### Rate limits

Rate limits on this endpoint are 1/10th of what is available on the single enrichment endpoint.

`POST https://api.apollo.io/api/v1/people/bulk_match`

### Request parameters

Parameter | Description | Example
--------- | ----------- | -----------
first_name (optional) | The person's first name | Tim
last_name (optional) | The person's last name | Zheng
name (optional) | The person's full name | Tim Zheng
email (optional) | The person's email | example@domain.com
hashed_email (optional) | The person's md5 or sha256 hashed email | 8d935115b9ff4489f2d1f9249503cadf OR 97817c0c49994eb500ad0a5e7e2d8aed 51977b26424d508f66e4e8887746a152
organization_name (optional) | The person's company name | Apollo Inc.
domain (optional) | The person's company domain | apollo.io
id (optional) |  The person's ID obtained from the search endpoint | "583f2f7ed9ced98ab5bfXXXX"
linkedin_url (optional) | The person's linkedin URL | http://www.linkedin.com/in/tim-zheng
reveal_personal_emails (optional) | Flag to reveal personal emails | true
reveal_phone_number (optional) | Flag to reveal phone number | true
webhook_url (optional) | Webhook URL for sending 'reveal_phone_number' response | "https://example.com/hook"


## Bulk organization enrichment

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "domains": [
        "apollo.io",
        "outreach.com",
        "microsoft.com"
    ]
}' "https://api.apollo.io/api/v1/organizations/bulk_enrich"
```

```python
import requests

url = "https://api.apollo.io/api/v1/organizations/bulk_enrich"

data = {
    "api_key": "YOUR API KEY HERE",
    "domains": [
        "apollo.io",
        "outreach.com",
        "microsoft.com"
    ]
}

headers = {
    'Cache-Control': 'no-cache',
    'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, json=data)

print(response.text)
```

> Sample response:

```json
{
   "status":"success",
   "error_code":null,
   "error_message":null,
   "total_requested_domains":3,
   "unique_domains":3,
   "unique_enriched_records":3,
   "missing_records":0,
   "organizations":[
      {
         "id":"5e66b6381e05b4008c8331b8",
         "name":"Apollo.io",
         "website_url":"http://www.apollo.io",
         "blog_url":null,
         "angellist_url":null,
         "linkedin_url":"http://www.linkedin.com/company/apolloio",
         "twitter_url":"https://twitter.com/MeetApollo/",
         "facebook_url":"https://www.facebook.com/MeetApollo/",
         "primary_phone":{
            "number":"+1 415-763-6055",
            "source":"Owler"
         },
         "languages":[
            
         ],
         "alexa_ranking":2651,
         "phone":"+1 415-763-6055",
         "linkedin_uid":"18511550",
         "founded_year":2015,
         "publicly_traded_symbol":null,
         "publicly_traded_exchange":null,
         "logo_url":"https://zenprospect-production.s3.amazonaws.com/uploads/pictures/6232fbed6106460001ca5dc7/picture",
         "crunchbase_url":null,
         "primary_domain":"apollo.io",
         "persona_counts":{
            
         },
         "industry":"computer software",
         "keywords":[
            "sales engagement",
            "lead generation",
            "predictive analytics",
            "lead scoring",
            "sales strategy",
            "conversation intelligence",
            "sales enablement",
            "lead routing",
            "sales development",
            "email engagement",
            "revenue intelligence",
            "sales operations",
            "demand generation"
         ],
         "estimated_num_employees":210,
         "snippets_loaded":true,
         "industry_tag_id":"5567cd4e7369643b70010000",
         "retail_location_count":0,
         "raw_address":"535 mission st, suite 1100, san francisco, california 94105, us",
         "street_address":"535 Mission St",
         "city":"San Francisco",
         "state":"California",
         "country":"United States",
         "postal_code":"94105",
         "owned_by_organization_id":null,
         "account_id":"6182b6670e22be00ded90b0f",
         "account":{
            "id":"6182b6670e22be00ded90b0f",
            "domain":"apollo.io",
            "name":"Apollo.io",
            "team_id":"6181a50999668600ded6fe71",
            "organization_id":"5e66b6381e05b4008c8331b8",
            "account_stage_id":"6181a50999668600ded6fe7c",
            "source":"deployment",
            "original_source":"deployment",
            "owner_id":"6181a50a99668600ded6feed",
            "created_at":"2021-11-03T16:18:47.229Z",
            "phone":"2023741312",
            "phone_status":"no_status",
            "test_predictive_score":null,
            "hubspot_id":null,
            "salesforce_id":null,
            "crm_owner_id":null,
            "parent_account_id":null,
            "sanitized_phone":"+12023741312",
            "account_playbook_statuses":[
               {
                  "_id":"61844b47a4258e00c2499c8e",
                  "added_by_id":"6181a50a99668600ded6feed",
                  "added_on":"2021-11-04T21:06:15.053+00:00",
                  "completed_step_ids":[
                     "6184391f26e0aa00a4ccc56b"
                  ],
                  "created_at":null,
                  "current_step_id":"61844dba8b94530112288546",
                  "finished_reason_cd":"completed_all_steps",
                  "paused_reason_cd":null,
                  "playbook_id":"6184388a0515e4008cbf5129",
                  "position":2,
                  "status_cd":"finished",
                  "updated_at":null,
                  "id":"61844b47a4258e00c2499c8e",
                  "key":"61844b47a4258e00c2499c8e"
               }
            ],
            "existence_level":"full",
            "label_ids":[
               
            ],
            "typed_custom_fields":{
               "618438b906b01300da086546":"Google, Okta, Lyft"
            },
            "modality":"account",
            "persona_counts":{
               
            }
         },
         "departmental_head_count":{
            "engineering":46,
            "business_development":14,
            "support":21,
            "finance":2,
            "marketing":10,
            "administrative":1,
            "product_management":7,
            "arts_and_design":8,
            "operations":7,
            "accounting":2,
            "entrepreneurship":3,
            "information_technology":2,
            "consulting":9,
            "human_resources":6,
            "sales":17,
            "education":3,
            "legal":0,
            "media_and_commmunication":0,
            "data_science":0
         }
      },
      {
         "id":"55ea57fdf3e5bb1430000ac7",
         "name":"Outreach, Inc.",
         "website_url":"http://www.outreach.com",
         "blog_url":null,
         "angellist_url":null,
         "linkedin_url":"http://www.linkedin.com/company/outreach-inc-",
         "twitter_url":null,
         "facebook_url":"https://www.facebook.com/outreachinc",
         "primary_phone":{
            "number":"+1 800-991-6011",
            "source":"Owler"
         },
         "languages":[
            "English",
            "English"
         ],
         "alexa_ranking":597090,
         "phone":"+1 800-991-6011",
         "linkedin_uid":"314305",
         "founded_year":1996,
         "publicly_traded_symbol":null,
         "publicly_traded_exchange":null,
         "logo_url":"https://zenprospect-production.s3.amazonaws.com/uploads/pictures/623369279d4f650001b93cb3/picture",
         "crunchbase_url":null,
         "primary_domain":"outreach.com",
         "persona_counts":{
            
         },
         "industry":"marketing \u0026 advertising",
         "keywords":[
            "outreach marketing product for christian churches",
            "customized design services",
            "professional design",
            "print \u0026 full service delivery",
            "targeted mailings done by inhouse mail services",
            "thought leader in outreach",
            "resource provider \u0026 content network",
            "churches",
            "marketing",
            "professional services",
            "religious organizations"
         ],
         "estimated_num_employees":170,
         "snippets_loaded":true,
         "industry_tag_id":"5567cd467369644d39040000",
         "retail_location_count":1,
         "raw_address":"5550 tech center drive, colorado springs, co 80919, us",
         "street_address":"5550 Tech Center Drive",
         "city":"Colorado Springs",
         "state":"Colorado",
         "country":"United States",
         "postal_code":"80919",
         "owned_by_organization_id":null,
         "departmental_head_count":{
            "accounting":3,
            "operations":4,
            "finance":2,
            "arts_and_design":5,
            "human_resources":3,
            "sales":11,
            "marketing":8,
            "media_and_commmunication":7,
            "product_management":3,
            "engineering":5,
            "consulting":6,
            "support":4,
            "entrepreneurship":2,
            "information_technology":5,
            "business_development":1,
            "administrative":2,
            "legal":0,
            "education":0,
            "data_science":0
         }
      },
      {
         "id":"5d09312ca3ae61489386b467",
         "name":"Microsoft",
         "website_url":"http://www.microsoft.com",
         "blog_url":null,
         "angellist_url":null,
         "linkedin_url":"http://www.linkedin.com/company/microsoft",
         "twitter_url":"https://twitter.com/microsoft",
         "facebook_url":"https://facebook.com/Microsoft",
         "primary_phone":{
            "number":"+1 425-882-8080",
            "source":"Owler"
         },
         "languages":[
            "English"
         ],
         "alexa_ranking":19,
         "phone":"+1 425-882-8080",
         "linkedin_uid":"1035",
         "founded_year":1975,
         "publicly_traded_symbol":"MSFT",
         "publicly_traded_exchange":"nasdaq",
         "logo_url":"https://zenprospect-production.s3.amazonaws.com/uploads/pictures/6232f7976d60b600019c2644/picture",
         "crunchbase_url":null,
         "primary_domain":"microsoft.com",
         "persona_counts":{
            
         },
         "market_cap":"2099.6B",
         "industry":"computer software",
         "keywords":[
            "business software",
            "developer tools",
            "home",
            "educational software",
            "tablets",
            "search",
            "advertising",
            "servers",
            "windows operating system",
            "windows applications",
            "platforms",
            "smartphones",
            "cloud computing",
            "quantum computing",
            "future of work",
            "productivity",
            "ai",
            "artificial intelligence",
            "machine learning",
            "laptops",
            "mixed reality",
            "virtual reality",
            "gaming",
            "developers",
            "it professional",
            "computers",
            "electronics",
            "mobile phones",
            "shopping"
         ],
         "estimated_num_employees":224000,
         "snippets_loaded":true,
         "industry_tag_id":"5567cd4e7369643b70010000",
         "retail_location_count":96,
         "raw_address":"1 microsoft way, redmond, washington 98052, us",
         "street_address":"1 Microsoft Way",
         "city":"Redmond",
         "state":"Washington",
         "country":"United States",
         "postal_code":"98052",
         "owned_by_organization_id":null,
         "departmental_head_count":{
            "sales":10117,
            "business_development":9413,
            "engineering":66732,
            "media_and_commmunication":1612,
            "finance":3079,
            "marketing":5327,
            "operations":3747,
            "support":12733,
            "consulting":5822,
            "product_management":4099,
            "data_science":1922,
            "administrative":350,
            "education":13249,
            "human_resources":3818,
            "arts_and_design":2125,
            "information_technology":3727,
            "legal":625,
            "accounting":476,
            "entrepreneurship":121
         }
      }
   ]
}
```

This endpoint enriches organization information in bulk with info such as industry, company size, etc. based on the domain parameter passed in.

Up to 10 records can be enriched at the same time through this endpoint. Newer plans utilizing Export Credits will be deducting 1 export credit when calling this endpoint.

### Rate limits

Rate limits on this endpoint are 1/10th of what is available on the single enrichment endpoint. 

`POST https://api.apollo.io/api/v1/organizations/bulk_enrich`

### Request parameters

| Parameter | Description        | Example    |
| --------- | ------------------ | ---------- |
| domains    | The company domain | google.com |


## People enrichment

> Sample request:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "api_key": "YOUR API KEY HERE",
    "id": "583f2f7ed9ced98ab5bfXXXX",
    "first_name": "Tim",
    "last_name": "Zheng",
    "organization_name": "Apollo",
    "email": "name@domain.io",
    "hashed_email": "8d935115b9ff4489f2d1f9249503cadf",
    "domain": "apollo.io",
    "reveal_personal_emails": true,
    "linkedin_url": "http://www.linkedin.com/in/tim-zheng-677ba010"
}' "https://api.apollo.io/v1/people/match"
```

```python
import requests

url = "https://api.apollo.io/v1/people/match"

data = {
    "api_key": "YOUR API KEY HERE",
    "id": "583f2f7ed9ced98ab5bfXXXX",
    "first_name": "Tim",
    "last_name": "Zheng",
    "organization_name": "Apollo",
    "email": "name@domain.io",
    "hashed_email": "8d935115b9ff4489f2d1f9249503cadf",
    "domain": "apollo.io",
    "reveal_personal_emails": true,
    "linkedin_url": "http://www.linkedin.com/in/tim-zheng-677ba010"
}

headers = {
    'Cache-Control': 'no-cache',
    'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, json=data)

print(response.text)
```

> Sample response:

```json
{
    "person": {
        "id": "6453e9bd8f50d40001f1e348",
        "first_name": "Tim",
        "last_name": "Zheng",
        "name": "Tim Zheng",
        "linkedin_url": "http://www.linkedin.com/in/tim-zheng-677ba010",
        "title": "Founder & CEO",
        "email_status": null,
        "photo_url": "https://media.licdn.com/dms/image/D5603AQEFiVRxq2aFCg/profile-displayphoto-shrink_200_200/0/1676521918175?e=1701907200&v=beta&t=6QqL_xwsDybj-FIUTr6XaEeLyrHxs7QS-IHSbVtYCak",
        "twitter_url": null,
        "github_url": null,
        "facebook_url": null,
        "extrapolated_email_confidence": null,
        "headline": "Founder & CEO at Apollo",
        "email": "name@domain.io",
        "organization_id": "5e66b6381e05b4008c8331b8",
        "employment_history": [
            {
                "_id": "651e57392998d400013ac5bd",
                "created_at": null,
                "current": true,
                "degree": null,
                "description": null,
                "emails": null,
                "end_date": null,
                "grade_level": null,
                "kind": null,
                "major": null,
                "organization_id": "5e66b6381e05b4008c8331b8",
                "organization_name": "Apollo",
                "raw_address": null,
                "start_date": "2016-01-01",
                "title": "Founder & CEO",
                "updated_at": null,
                "id": "651e57392998d400013ac5bd",
                "key": "651e57392998d400013ac5bd"
            },
            {
                "_id": "651e57392998d400013ac5be",
                "created_at": null,
                "current": false,
                "degree": null,
                "description": null,
                "emails": null,
                "end_date": "2015-01-01",
                "grade_level": null,
                "kind": null,
                "major": null,
                "organization_id": null,
                "organization_name": "Braingenie",
                "raw_address": null,
                "start_date": "2011-01-01",
                "title": "Founder & CEO",
                "updated_at": null,
                "id": "651e57392998d400013ac5be",
                "key": "651e57392998d400013ac5be"
            },
            {
                "_id": "651e57392998d400013ac5bf",
                "created_at": null,
                "current": false,
                "degree": null,
                "description": null,
                "emails": null,
                "end_date": "2011-01-01",
                "grade_level": null,
                "kind": null,
                "major": null,
                "organization_id": "54a22f23746869331840e813",
                "organization_name": "Citadel Investment Group",
                "raw_address": null,
                "start_date": "2011-01-01",
                "title": "Investment & Trading Associate",
                "updated_at": null,
                "id": "651e57392998d400013ac5bf",
                "key": "651e57392998d400013ac5bf"
            }
        ],
        "state": "California",
        "city": "San Francisco",
        "country": "United States",
        "organization": {
            "id": "5e66b6381e05b4008c8331b8",
            "name": "Apollo.io",
            "website_url": "http://www.apollo.io",
            "blog_url": null,
            "angellist_url": null,
            "linkedin_url": "http://www.linkedin.com/company/apolloio",
            "twitter_url": "https://twitter.com/meetapollo/",
            "facebook_url": "https://www.facebook.com/MeetApollo",
            "primary_phone": {
                "number": "+1415-640-9303",
                "source": "Owler",
                "country_code_added_from_hq": true
            },
            "languages": [],
            "alexa_ranking": 3514,
            "phone": "+1415-640-9303",
            "linkedin_uid": "18511550",
            "founded_year": 2015,
            "publicly_traded_symbol": null,
            "publicly_traded_exchange": null,
            "logo_url": "https://zenprospect-production.s3.amazonaws.com/uploads/pictures/64beb2c5e966df0001384ac1/picture",
            "crunchbase_url": null,
            "primary_domain": "apollo.io",
            "sanitized_phone": "+14156409303",
            "industry": "information technology & services",
            "keywords": [
                "sales engagement",
                "lead generation",
                "predictive analytics",
                "lead scoring",
                "sales strategy",
                "conversation intelligence",
                "sales enablement",
                "lead routing",
                "sales development",
                "email engagement",
                "revenue intelligence",
                "sales operations",
                "demand generation"
            ],
            "estimated_num_employees": 1200,
            "industries": [
                "information technology & services"
            ],
            "secondary_industries": [],
            "snippets_loaded": true,
            "industry_tag_id": "5567cd4773696439b10b0000",
            "industry_tag_hash": {
                "information technology & services": "5567cd4773696439b10b0000"
            },
            "retail_location_count": 0,
            "raw_address": "535 mission street, san francisco, california, united states",
            "street_address": "535 Mission Street",
            "city": "San Francisco",
            "state": "California",
            "postal_code": "94105",
            "country": "United States",
            "owned_by_organization_id": null,
            "suborganizations": [],
            "num_suborganizations": 0,
            "seo_description": "Search, engage, and convert over 265 million contacts at over 70 million companies with Apollo's sales intelligence and engagement platform.",
            "short_description": "Apollo.io combines a buyer database of over 270M contacts and powerful sales engagement and automation tools in one, easy to use platform. Trusted by over 160,000 companies including Autodesk, Rippling, Deel, Jasper.ai, Divvy, and Heap, Apollo has more than one million users globally. By helping sales professionals find their ideal buyers and intelligently automate outreach, Apollo helps go-to-market teams sell anything.\n\nCelebrating a $100M Series D Funding Round 🦄",
            "annual_revenue_printed": "345.6M",
            "annual_revenue": 345600000.0,
            "total_funding": 251200000,
            "total_funding_printed": "251.2M",
            "latest_funding_round_date": "2023-08-01T00:00:00.000+00:00",
            "latest_funding_stage": "Series D",
            "funding_events": [
                {
                    "id": "6520fc8e0f5b210001b5285b",
                    "date": "2023-08-01T00:00:00.000+00:00",
                    "news_url": null,
                    "type": "Series D",
                    "investors": "Bain Capital Ventures, Sequoia Capital, Tribe Capital, Nexus Venture Partners",
                    "amount": "100M",
                    "currency": "$"
                },
                {
                    "id": "624f4dfec786590001768016",
                    "date": "2022-03-01T00:00:00.000+00:00",
                    "news_url": null,
                    "type": "Series C",
                    "investors": "Sequoia Capital, Tribe Capital, Nexus Venture Partners, NewView Capital",
                    "amount": "110M",
                    "currency": "$"
                },
                {
                    "id": "61b13677623110000186a478",
                    "date": "2021-10-01T00:00:00.000+00:00",
                    "news_url": null,
                    "type": "Series B",
                    "investors": "Tribe Capital, NewView Capital, Nexus Venture Partners",
                    "amount": "32M",
                    "currency": "$"
                },
                {
                    "id": "5ffe93caa54d75077c59acef",
                    "date": "2018-06-26T00:00:00.000+00:00",
                    "news_url": "https://techcrunch.com/2018/06/26/yc-grad-zenprospect-rebrands-as-apollo-lands-7-m-series-a/",
                    "type": "Series A",
                    "investors": "Nexus Venture Partners, Social Capital, Y Combinator",
                    "amount": "7M",
                    "currency": "$"
                },
                {
                    "id": "6520fc8f0f5b210001b52860",
                    "date": "2016-10-01T00:00:00.000+00:00",
                    "news_url": null,
                    "type": "Other",
                    "investors": "Y Combinator, SV Angel, Social Capital, Nexus Venture Partners",
                    "amount": "2.2M",
                    "currency": "$"
                }
            ]
        },
        "phone_numbers": [
            {
                "raw_number": "+1415-640-9303",
                "sanitized_number": "+14156409303",
                "type": "work_hq",
                "position": 0,
                "status": "no_status",
                "dnc_status": null,
                "dnc_other_info": null
            }
        ],
        "intent_strength": null,
        "show_intent": false,
        "revealed_for_current_team": true,
        "hashed_email": "8d935115b9ff4489f2d1f9249503cadf",
        "personal_emails": [],
        "departments": [
            "c_suite"
        ],
        "subdepartments": [
            "executive",
            "founder"
        ],
        "functions": [
            "entrepreneurship"
        ],
        "seniority": "founder"
    }
}
```

This endpoint enriches a person's information, the more information you pass in, the more likely we can find a match. It will deduct 1 email credit for each email found.

`POST https://api.apollo.io/v1/people/match`

### Query parameters

Parameter | Description | Example
--------- | ----------- | -----------
first_name (optional) | The person's first name | Tim
last_name (optional) | The person's last name | Zheng
name (optional) | The person's full name | Tim Zheng
email (optional) | The person's email | example@domain.com
hashed_email (optional) | The person's md5 or sha256 hashed email | 8d935115b9ff4489f2d1f9249503cadf OR 97817c0c49994eb500ad0a5e7e2d8aed 51977b26424d508f66e4e8887746a152
organization_name (optional) | The person's company name | Apollo Inc.
domain (optional) | The person's company domain | apollo.io
id (optional) |  The person's ID obtained from the search endpoint | "583f2f7ed9ced98ab5bfXXXX"
linkedin_url (optional) | The person's linkedin URL | http://www.linkedin.com/in/tim-zheng
reveal_personal_emails (optional) | Flag to reveal personal emails | true
reveal_phone_number (optional) | Flag to reveal phone number | true
webhook_url (optional) | Webhook URL for sending 'reveal_phone_number' response | "https://example.com/hook"


## Organization enrichment

> Sample request:

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" "https://api.apollo.io/v1/organizations/enrich?api_key=YOUR_API_KEY_HERE&domain=apollo.io"
```

```python
import requests

url = "https://api.apollo.io/v1/organizations/enrich"

querystring = {
    "api_key": "YOUR API KEY HERE",
    "domain": "apollo.io"
}

headers = {
    'Cache-Control': 'no-cache',
    'Content-Type': 'application/json'
}

response = requests.request("GET", url, headers=headers, params=querystring)

print(response.text)
```

> Sample response:

```json
{
    "organization": {
        "id": "5e66b6XXXXXXXXXXXXXXXXXX",
        "name": "Apollo.io",
        "website_url": "http://www.apollo.io",
        "blog_url": null,
        "angellist_url": null,
        "linkedin_url": "http://www.linkedin.com/company/apolloio",
        "twitter_url": "https://twitter.com/MeetApollo/",
        "facebook_url": "https://www.facebook.com/MeetApollo/",
        "primary_phone": {
            "number": "202374XXXX",
            "source": "Account"
        },
        "languages": [],
        "alexa_ranking": 522,
        "phone": "202374XXXX",
        "linkedin_uid": "185115XX",
        "founded_year": 2015,
        "publicly_traded_symbol": null,
        "publicly_traded_exchange": null,
        "logo_url": "https://apollo-server.com/uploads/pictures/61824XXXXXXXXXXXXXXXXXXX/picture",
        "crunchbase_url": null,
        "primary_domain": "apollo.io",
        "persona_counts": {},
        "industry": "computer software",
        "keywords": [
            "sales engagement",
            "lead generation",
            "predictive analytics",
            "lead scoring",
            "sales strategy",
            "conversation intelligence",
            "sales enablement",
            "lead routing",
            "sales development",
            "email engagement",
            "revenue intelligence",
            "sales operations",
            "demand generation"
        ],
        "estimated_num_employees": 170,
        "snippets_loaded": true,
        "industry_tag_id": "5567cdXXXXXXXXXXXXXXXXXX",
        "retail_location_count": 0,
        "raw_address": "535 Mission St, Suite 1100, San Francisco, California 94105, US",
        "street_address": "535 Mission St",
        "city": "San Francisco",
        "state": "California",
        "postal_code": "94105",
        "country": "United States",
        "owned_by_organization_id": null,
        "suborganizations": [],
        "num_suborganizations": 0,
        "seo_description": "Apollo is a data-first engagement platform that embeds intelligence within your workflows to help you execute, analyze, and improve on your growth strategy.",
        "short_description": "Apollo is the unified engagement acceleration platform that gives reps the ability to dramatically increase their number of quality conversations and opportunities. Reps are empowered do more than just conduct outreach, they learn who to target, how to reach out, and what to say at speed and scale. We help drive growth and success by providing the means for teams to discover and utilize their organization’s unique best practices. \n\nBy working in a unified platform, reps and managers alike save hours of time each day, strategy changes are instantly scaled across the whole team, and managers can finally dig into data at each step of their pipeline to continually find new ways to improve. \n\nTeams get access to our database of 200+ million contacts with a built-in fully customizable Scoring Engine, full sales engagement stack, our native Account Playbook builder, and the industry’s only custom deep analytics suite. Managers create and enforce order and process with the industry’s most advanced Rules Engine.\n\nApollo is the foundation for your entire end-to-end sales strategy.\n\nJoin teams like Autodesk, Copper (ProsperWorks), and Snowflake to experience the future of sales today. Ready to join our crew? Email sales@apollo.io. ",
        "annual_revenue_printed": "10M",
        "annual_revenue": 10000000,
        "total_funding": 9200000,
        "total_funding_printed": "9.2M",
        "latest_funding_round_date": "2018-06-26T00:00:00.000+00:00",
        "latest_funding_stage": "Series A",
        "funding_events": [
            {
                "id": "5ffe93XXXXXXXXXXXXXXXXXX",
                "date": "2018-06-26T00:00:00.000+00:00",
                "news_url": "https://techcrunch.com/2018/06/26/yc-grad-zenprospect-rebrands-as-apollo-lands-7-m-series-a/",
                "type": "Series A",
                "investors": "Nexus Venture Partners",
                "amount": "7M",
                "currency": "$"
            },
            {
                "id": "5ffe93XXXXXXXXXXXXXXXXXX",
                "date": "2016-10-01T00:00:00.000+00:00",
                "news_url": null,
                "type": "Other",
                "investors": "Y Combinator, SV Angel, Social Capital, Nexus Venture Partners",
                "amount": "2.2M",
                "currency": "$"
            }
        ],
        "technology_names": [
            "Cloudflare DNS",
            "Mailchimp Mandrill",
            "Gmail",
            "Marketo",
            "Google Apps",
            "Microsoft Office 365",
            "CloudFlare Hosting",
            "Route 53",
            "Zendesk",
            "Google Cloud Hosting",
            "Stripe",
            "Lever",
            "Segment.io",
            "Amplitude",
            "Hubspot",
            "Nginx",
            "CrazyEgg",
            "Squarespace ECommerce",
            "Linkedin Marketing Solutions",
            "Yandex Metrica",
            "Mobile Friendly",
            "Typekit",
            "Google Tag Manager"
        ],
        "current_technologies": [
            {
                "uid": "cloudflare_dns",
                "name": "Cloudflare DNS",
                "category": "Domain Name Services"
            },
            {
                "uid": "mailchimp_mandrill",
                "name": "Mailchimp Mandrill",
                "category": "Email Delivery"
            },
            {
                "uid": "gmail",
                "name": "Gmail",
                "category": "Email Providers"
            },
            {
                "uid": "marketo",
                "name": "Marketo",
                "category": "Marketing Automation"
            }
        ],
        "account_id": "614264XXXXXXXXXXXXXXXXXX",
        "account": {
            "id": "614264XXXXXXXXXXXXXXXXXX",
            "domain": "apollo.io",
            "name": "Apollo",
            "team_id": "5c1004XXXXXXXXXXXXXXXXXX",
            "organization_id": "5e66b6XXXXXXXXXXXXXXXXXX",
            "account_stage_id": "5c1004XXXXXXXXXXXXXXXXXX",
            "source": "salesforce",
            "original_source": "salesforce",
            "owner_id": "5c1004XXXXXXXXXXXXXXXXXX",
            "created_at": "2021-09-15T21:24:18.374Z",
            "phone": "(123) 456-XXXX",
            "phone_status": "no_status",
            "test_predictive_score": null,
            "hubspot_id": null,
            "salesforce_id": "0015g0XXXXXXXXXXXX",
            "crm_owner_id": "0055g0XXXXXXXXXXXX",
            "parent_account_id": null,
            "sanitized_phone": "+112345XXXXX",
            "account_playbook_statuses": [],
            "existence_level": "full",
            "label_ids": [],
            "typed_custom_fields": {},
            "modality": "account",
            "persona_counts": {}
        },
        "departmental_head_count": {
            "engineering": 45,
            "accounting": 4,
            "product_management": 5,
            "support": 31,
            "arts_and_design": 10,
            "sales": 37,
            "education": 6,
            "consulting": 10,
            "human_resources": 10,
            "business_development": 22,
            "operations": 10,
            "finance": 8,
            "entrepreneurship": 4,
            "marketing": 7,
            "information_technology": 5,
            "administrative": 3,
            "legal": 0,
            "media_and_commmunication": 0,
            "data_science": 0
        }
    }
}
```

This endpoint enriches a company with info such as industry, company size, etc. based on the domain parameter passed in. Newer plans utilizing Export Credits will be deducting 1 export credit when calling this endpoint.

`GET https://api.apollo.io/v1/organizations/enrich`

### Query parameters

| Parameter | Description        | Example    |
| --------- | ------------------ | ---------- |
| domain    | The company domain | google.com |

