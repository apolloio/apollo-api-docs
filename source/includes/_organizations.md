# Organizations API

An organization represents a company in Apollo's database.

## Organization jobs postings

> Sample request:

```shell
curl -X GET -H "Content-Type: application/json" -H "Cache-Control: no-cache" "https://api.apollo.io/v1/organizations/ORGANIZATION_ID/job_postings?api_key=YOUR_API_KEY_HERE"
```

```python
import requests

url = "https://api.apollo.io/v1/organizations/ORGANIZATION_ID/job_postings"

querystring = {
    "api_key": "YOUR API KEY HERE"
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
  "organization_job_postings": [
    {
      "id": "5ed76XXXXXXXXXXXXXXXX",
      "title": "Product Marketing Manager, Security",
      "url": "https://www.linkedin.com/jobs/view/product-marketing-manager-security-at-google-1878106711?refId=e19c8d31-7452-4bfc-8097-66ab00fe06a8&position=14&pageNum=9&trk=public_jobs_job-result-card_result-card_full-click",
      "city": "San Francisco",
      "state": "California",
      "country": "United States",
      "last_seen_at": "2020-06-03T09:09:57.751+00:00",
      "posted_at": "2020-06-03T07:09:57.751+00:00"
    },
    {
      "id": "5ed768XXXXXXXXXXXXXXXX",
      "title": "Product Marketing Manager, Security",
      "url": "https://www.linkedin.com/jobs/view/product-marketing-manager-security-at-google-1878108613?refId=e19c8d31-7452-4bfc-8097-66ab00fe06a8&position=17&pageNum=9&trk=public_jobs_job-result-card_result-card_full-click",
      "city": "Sunnyvale",
      "state": "California",
      "country": "United States",
      "last_seen_at": "2020-06-03T09:09:57.754+00:00",
      "posted_at": "2020-06-03T07:09:57.754+00:00"
    },
    {
      "id": "5ed768XXXXXXXXXXXXXXXX",
      "title": "Staff Software Engineer, Platforms, Google Cloud",
      "url": "https://www.linkedin.com/jobs/view/staff-software-engineer-platforms-google-cloud-at-google-1878104847?refId=e19c8d31-7452-4bfc-8097-66ab00fe06a8&position=18&pageNum=9&trk=public_jobs_job-result-card_result-card_full-click",
      "city": "Sunnyvale",
      "state": "California",
      "country": "United States",
      "last_seen_at": "2020-06-03T09:09:57.755+00:00",
      "posted_at": "2020-07-30T07:32:24.298+00:00"
    }
  ]
}
```

Get a list of active job postings for a company.

`GET https://api.apollo.io/v1/organizations/ORGANIZATION_ID/job_postings`

### Query parameters

| Parameter | Description                                                                                                                 | Example                  |
| --------- | --------------------------------------------------------------------------------------------------------------------------- | ------------------------ |
| id        | The id of the organization (i.e. NOT account id). You can obtain this with a company's domain by using the enrich endpoint. | 54fca1087369647fcXXXXXXX |



## Organization search 

> Sample request:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
  "api_key": "YOUR API KEY HERE",
  "page": 1,
  "per_page": 10,
  "organization_num_employees_ranges": ["1,100", "1,1000"],
  "organization_locations": ["United States"],
  "q_organization_keyword_tags": ["sales strategy", "lead"],
  "q_organization_name": "Apollo.io"
}' "https://api.apollo.io/api/v1/mixed_companies/search"
``` 

```python
import requests

url = "https://api.apollo.io/api/v1/mixed_companies/search"

data = {
    "api_key": "YOUR API KEY HERE",
    "page":1,
    "per_page":10,  
    "organization_num_employees_ranges":["1,100", "1,1000"],
    "organization_locations":["United States"],
    "q_organization_keyword_tags":["sales strategy", "lead"],
    "q_organization_name":"Apollo.io"
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
    "breadcrumbs": [
        {
            "label": "Company Name",
            "signal_field_name": "q_organization_name",
            "value": "Apollo.io",
            "display_name": "Apollo.io"
        },
        {
            "label": "# Employees",
            "signal_field_name": "organization_num_employees_ranges",
            "value": "1,100",
            "display_name": "1-100"
        },
        {
            "label": "# Employees",
            "signal_field_name": "organization_num_employees_ranges",
            "value": "1,1000",
            "display_name": "1-1000"
        },
        {
            "label": "Company Locations",
            "signal_field_name": "organization_locations",
            "value": "United States",
            "display_name": "United States"
        },
        {
            "label": "Company Keywords Contain ANY Of",
            "signal_field_name": "q_organization_keyword_tags",
            "value": "sales strategy",
            "display_name": "sales strategy"
        },
        {
            "label": "Company Keywords Contain ANY Of",
            "signal_field_name": "q_organization_keyword_tags",
            "value": "lead",
            "display_name": "lead"
        }
    ],
    "partial_results_only": false,
    "disable_eu_prospecting": false,
    "partial_results_limit": 10000,
    "pagination": {
        "page": 1,
        "per_page": 10,
        "total_entries": 1,
        "total_pages": 1
    },
    "accounts": [
        {
            "id": "63b3e47f0deb820001XXXXX",
            "name": "Apollo.io",
            "website_url": null,
            "blog_url": null,
            "angellist_url": null,
            "linkedin_url": "http://www.linkedin.com/company/apolXXXXX",
            "twitter_url": "https://twitter.com/MeetApolXXXXX/",
            "facebook_url": "https://facebook.com/MeetApoXXXXX/",
            "primary_phone": {
                "number": "+1 415-640-9303",
                "source": "Account"
            },
            "languages": [],
            "alexa_ranking": 3514,
            "phone": null,
            "linkedin_uid": "18511550",
            "founded_year": 2015,
            "publicly_traded_symbol": null,
            "publicly_traded_exchange": null,
            "logo_url": "https://zenprospect-production.s3.amazonaws.com/uploads/pictures/63d3a127e242df0001eXXXXX/picture",
            "crunchbase_url": null,
            "primary_domain": null,
            "sanitized_phone": "+14156409303",
            "owned_by_organization_id": null,
            "organization_raw_address": "535 mission st, suite 1100, san francisco, california 94105, us",
            "organization_city": "San Francisco",
            "organization_street_address": "535 Mission St",
            "organization_state": "California",
            "organization_country": "United States",
            "organization_postal_code": "94105",
            "suggest_location_enrichment": false,
            "parent_account": {
                "id": "62b5283531e821000XXXXX",
                "name": "Apollo.io"
            },
            "domain": "apollo.io",
            "team_id": "551e3ef072616951471XXXXX",
            "organization_id": "65080f223660ac000XXXXX",
            "account_stage_id": "5711a6247ff0bb33edXXXXX",
            "source": "job_change",
            "original_source": "job_change",
            "creator_id": null,
            "owner_id": "5eaf980991763800eXXXXX",
            "created_at": "2023-01-03T08:17:03.163Z",
            "phone_status": "no_status",
            "hubspot_id": null,
            "salesforce_id": "0015a00003AXXXXX",
            "crm_owner_id": "0052L000003XXXXX",
            "parent_account_id": "62b5283531e82100012XXXXX",
            "account_playbook_statuses": [],
            "account_rule_config_statuses": [],
            "existence_level": "full",
            "label_ids": [],
            "typed_custom_fields": {
                "5b7aff6c55884769e38XXXXX": 7.0,
                "5ee1d989add32701128XXXXX": "0015a00003AjsaS",
                "5f28afc474e70000f12XXXXX": "High Tier"
            },
            "modality": "account",
            "salesforce_record_url": "https://apolloio.my.salesforce.com/0015a00003AjsXXXXX",
            "contact_emailer_campaign_ids": [
                "6488dbeb72e68a00d9XXXXX"
            ],
            "contact_campaign_status_tally": {
                "finished": 6,
                "paused": 4,
                "not_sent": 1,
                "active": 1
            },
            "num_contacts": 17,
            "last_activity_date": "2023-09-26T05:31:52.000+00:00",
            "intent_strength": null,
            "show_intent": true
        }
    ],
    "organizations": [],
    "model_ids": [
        "63b3e47f0deb820001fXXXXX"
    ],
    "num_fetch_result": null,
    "derived_params": {
        "recommendation_config_id": "650bc3a2c7d5a700d09XXXXX"
    }
}
```

This endpoint searches for organizations. Newer plans utilizing Export Credits will be deducting **1 export credit** when calling this endpoint. 

`POST https://api.apollo.io/api/v1/mixed_companies/search`

### Query parameters

Parameter                                         | Description                                                                                 | Example
------------------------------------------------- | --------------------------------------------------------------------------------------------|----------------------------------------| 
organization_ids (optional)                       | An array of organization ids obtained from companies-search                                 | ["63ff0bc1ff57ba0001e7eXXX"]           |
organization_num_employees_ranges (optional)      | An array of intervals to include organizations having number of employees in a range        | ["1,10", "101,200" ]                   |
organization_locations (optional)                 | An array of strings denoting allowed locations of organization headquarters                 | ["California, US", "Minnesota, US"]    |
organization_not_locations (optional)             | An array of strings denoting un-allowed locations of organization headquarters              | ["Chicago, US"]                        |
q_organization_keyword_tags (optional)            | An array of strings denoting the keywords an organization should be associated with         | ["sales strategy", "lead"]              |
prospected_by_current_team (optional)             | An array of string booleans defining whether we want models prospected by current team or not. "no" means to look in net new database only, "yes" means to see saved organizations only | ["no"]
q_organization_name (optional)                    | A string representing the name of the organization we want to filter                        | "Apollo"                               |
page (optional)                                   | An integer that allows you to paginate through the results                                  | 1                                      |
per_page (optional)                               | An integer to load per_page results on a page. Should be in inclusive range [1, 100]        | 10                                     |


### Return results
"organizations" are organizations in Apollo's database.
"accounts" are organizations already in your linked CRM.