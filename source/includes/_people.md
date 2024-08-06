# People API

A person represents a person in Apollo's database.

## Search 

> Sample request:

```shell
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -H "X-Api-Key: YOUR API KEY HERE" -d '{
    "q_organization_domains": "apollo.io\ngoogle.com",
    "page" : 1,
    "per_page": 10,
    "organization_locations": ["California, US"],
    "person_seniorities": ["senior", "manager"],
    "organization_num_employees_ranges": ["1,1000000"],
    "person_titles" : ["sales manager", "engineer manager"]
}' "https://api.apollo.io/v1/mixed_people/search"
``` 

```python
import requests

url = "https://api.apollo.io/v1/mixed_people/search"

data = {
    "q_organization_domains": "apollo.io\ngoogle.com",
    "page" : 1,
    "per_page": 10,
    "organization_locations": ["California, US"],
    "person_seniorities": ["senior", "manager"],
    "organization_num_employees_ranges": ["1,1000000"],
    "person_titles" : ["sales manager", "engineer manager"]
}

headers = {
    'Cache-Control': 'no-cache',
    'Content-Type': 'application/json',
    'X-Api-Key': 'YOUR API KEY HERE'
}

response = requests.request("POST", url, headers=headers, json=data)

print(response.text)
```

> Sample response:

```json 
{
    "breadcrumbs": [
        {
            "label": "Titles",
            "signal_field_name": "person_titles",
            "value": "sales manager",
            "display_name": "sales manager"
        },
        {
            "label": "Titles",
            "signal_field_name": "person_titles",
            "value": "engineer manager",
            "display_name": "engineer manager"
        },
        {
            "label": "# Employees",
            "signal_field_name": "organization_num_employees_ranges",
            "value": "1,1000000",
            "display_name": "1-1000000"
        },
        {
            "label": "Management Level",
            "signal_field_name": "person_seniorities",
            "value": "senior",
            "display_name": "Senior"
        },
        {
            "label": "Management Level",
            "signal_field_name": "person_seniorities",
            "value": "manager",
            "display_name": "Manager"
        },
        {
            "label": "Company Locations",
            "signal_field_name": "organization_locations",
            "value": "California, US",
            "display_name": "California, US"
        },
        {
            "label": "Company Domains",
            "signal_field_name": "q_organization_domains",
            "value": [
                "apollo.io",
                "google.com"
            ],
            "display_name": "apollo.io, google.com"
        }
    ],
    "partial_results_only": false,
    "disable_eu_prospecting": false,
    "partial_results_limit": 10000,
    "pagination": {
        "page": 1,
        "per_page": 10,
        "total_entries": 2145,
        "total_pages": 215
    },
    "contacts": [],
    "people": [
        {
            "id": "618a24XXXXXXXXXXXXXXXXXX",
            "first_name": "Tim",
            "last_name": "Zheng",
            "name": "Tim Zheng",
            "linkedin_url": "http://www.linkedin.com/in/tim-zheng-677ba010",
            "title": "Founder & CEO",
            "email_status": "verified",
            "photo_url": "https://static-exp1.licdn.com/sc/h/244xhbkr7g40x6bsu4gi6q4ry",
            "twitter_url": null,
            "github_url": null,
            "facebook_url": null,
            "extrapolated_email_confidence": null,
            "headline": "Founder & CEO at Apollo",
            "email": "email_not_unlocked@domain.com",
            "employment_history": [
                {
                    "_id": "618afbXXXXXXXXXXXXXXXXXX",
                    "created_at": "2021-11-09T22:51:18.531Z",
                    "current": true,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": null,
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": "5e66b6XXXXXXXXXXXXXXXXXX",
                    "organization_name": "Apollo",
                    "raw_address": null,
                    "start_date": "2015-01-01",
                    "title": "Founder & CEO",
                    "updated_at": "2021-11-09T22:51:18.531Z",
                    "id": "618afbXXXXXXXXXXXXXXXXXX",
                    "key": "618afbXXXXXXXXXXXXXXXXXX"
                },
                {
                    "_id": "618afbXXXXXXXXXXXXXXXXXX",
                    "created_at": "2021-11-09T22:51:18.536Z",
                    "current": false,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": "2014-01-01",
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": null,
                    "organization_name": "Braingenie",
                    "raw_address": null,
                    "start_date": "2011-01-01",
                    "title": "Founder & CEO",
                    "updated_at": "2021-11-09T22:51:18.536Z",
                    "id": "618afbXXXXXXXXXXXXXXXXXX",
                    "key": "618afbXXXXXXXXXXXXXXXXXX"
                },
                {
                    "_id": "618afbXXXXXXXXXXXXXXXXXX",
                    "created_at": "2021-11-09T22:51:18.536Z",
                    "current": false,
                    "degree": null,
                    "description": null,
                    "emails": null,
                    "end_date": "2011-01-01",
                    "grade_level": null,
                    "kind": null,
                    "major": null,
                    "organization_id": "54a22fXXXXXXXXXXXXXXXXXX",
                    "organization_name": "Citadel Investment Group",
                    "raw_address": null,
                    "start_date": "2011-01-01",
                    "title": "Investment & Trading Associate",
                    "updated_at": "2021-11-09T22:51:18.536Z",
                    "id": "618afbXXXXXXXXXXXXXXXXXX",
                    "key": "618afbXXXXXXXXXXXXXXXXXX"
                }
            ],
            "state": "Texas",
            "city": "Austin",
            "country": "United States",
            "organization_id": "5e66b6XXXXXXXXXXXXXXXXXX",
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
                    "number": "(202) 374-XXXX",
                    "source": "Account"
                },
                "languages": [],
                "alexa_ranking": 685,
                "phone": "(202) 374-XXXX",
                "linkedin_uid": "185115XX",
                "founded_year": 2015,
                "publicly_traded_symbol": null,
                "publicly_traded_exchange": null,
                "logo_url": "https://apollo-server.com/uploads/pictures/6188cXXXXXXXXXXXXXXXXXXX/picture",
                "crunchbase_url": null,
                "primary_domain": "apollo.io",
                "persona_counts": {}
            },
            "account_id": "616d0eXXXXXXXXXXXXXXXXXX",
            "account": {
                "id": "616d0eXXXXXXXXXXXXXXXXXX",
                "name": "Apollo",
                "website_url": "http://www.apollo.io",
                "blog_url": null,
                "angellist_url": null,
                "linkedin_url": "http://www.linkedin.com/company/apolloio",
                "twitter_url": "https://twitter.com/MeetApollo/",
                "facebook_url": "https://www.facebook.com/MeetApollo/",
                "primary_phone": {
                    "number": "(202) 374-XXXX",
                    "source": "Account"
                },
                "languages": [],
                "alexa_ranking": 685,
                "phone": "(123) 456-XXXX",
                "linkedin_uid": "185115XX",
                "founded_year": 2015,
                "publicly_traded_symbol": null,
                "publicly_traded_exchange": null,
                "logo_url": "https://apollo-server.com/uploads/pictures/6188cXXXXXXXXXXXXXXXXXXX/picture",
                "crunchbase_url": null,
                "primary_domain": "apollo.io",
                "persona_counts": {},
                "domain": "apollo.io",
                "team_id": "5c1004a041f5ac0995d5f5e8",
                "organization_id": "5e66b6XXXXXXXXXXXXXXXXXX",
                "account_stage_id": "5c1004XXXXXXXXXXXXXXXXXX",
                "source": "crm",
                "original_source": "crm",
                "owner_id": null,
                "created_at": "2021-10-18T06:03:45.774Z",
                "phone_status": "no_status",
                "test_predictive_score": null,
                "hubspot_id": "699261XXXX",
                "salesforce_id": null,
                "crm_owner_id": "511281XX",
                "parent_account_id": null,
                "sanitized_phone": "+112345XXXXX",
                "account_playbook_statuses": [],
                "existence_level": "full",
                "label_ids": [],
                "typed_custom_fields": {},
                "modality": "account",
                "hubspot_record_url": "https://app.hubspot.com/sales/25200013/company/699261XXXX",
                "salesloft_id": "233684XX",
                "salesloft_url": "https://app.salesloft.com/app/company/233684XX"
            },
            "departments": [
                "c_suite", 
                "master_information_technology", 
                "master_operations"
            ],
            "subdepartments": [
                "operations_executive",
                "business_service_management_itsm",
                "operations"
            ],
            "functions": [
                "operations"
            ],
            "seniority": "c_suite"
        }
    ]
}
```

This endpoint searches for people and does not return any new email information. To get email information, use the "enrich" endpoint. Newer plans utilizing Export Credits will be deducting **1 export credit** when calling this endpoint. This feature is not accessible to Apollo users on free plans.

<aside class="notice">
Note: The Search endpoint has a display limit of 50,000 records (100 records per page, up to 500 pages) to protect the platform's performance for all users. To navigate the records, please include more filters in your search to narrow down the results as much as possible. This paging limitation doesn't restrict your access to our database; it simply requires you to access the data in batches.
</aside>

`POST https://api.apollo.io/v1/mixed_people/search`

### Query parameters

Parameter | Description | Example
--------- | ----------- | -----------
person_titles (optional)                | An array of the person's title. Apollo will return results matching ANY of the titles passed in |  ["sales director", "engineer manager"]
q_keywords (optional)                   | A string of words over which we want to filter the results | "Tim"
prospected_by_current_team (optional)   | An array of string booleans defining whether we want models prospected by current team or not. "no" means to look in net new database only, "yes" means to see saved contacts only | ["no"]
person_locations (optional)             | An array of strings denoting allowed locations of the person | ["California, US", "Minnesota, US"]
person_seniorities (optional)           | An array of strings denoting the seniorities or levels  | ["senior", "manager"]
contact_email_status (optional)         | An array of strings to look for people having a set of email statuses | ["verified", "guessed", "unavailable", "bounced", "pending_manual_fulfillment"]
q_organization_domains (optional)       | An array of the company domains to search for, joined by the new line character.  | "google.com\nfacebook.com"
organization_locations (optional)       | An array of strings denoting allowed locations of organization headquarters of the person | ["California, US", "Minnesota, US"]
organization_ids (optional)             | An array of organization ids obtained from companies-search | ["63ff0bc1ff57ba0001e7eXXX"]
organization_num_employees_ranges (optional)   | An array of intervals to include people belonging in an organization having number of employees in a range | ["1,10", "101,200" ]
page (optional) | An integer that allows you to paginate through the results  | 1
per_page (optional) | An integer to load per_page results on a page. Should be in inclusive range [1, 100] | 10


### Return results
"people" are people in Apollo's database.
"contacts" are people already in your linked CRM.