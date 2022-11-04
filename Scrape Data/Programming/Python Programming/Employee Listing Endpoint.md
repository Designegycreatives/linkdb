### Scraping employees details with proxycurl

![6](https://user-images.githubusercontent.com/83256563/200051164-d0a11714-fd6a-45a1-9a7e-29fff442102c.png)


Hello, I want to show you how to scrape employee details from linkedin company profiles using proxy curl.

I will be using the Employee Listing Endpoint.

This endpoint is best used to list employees working in companies based in locations like US, UK, Canada, Israel, Australia, Ireland, New Zealand and Singapore only.

I will be using Python Programming language.

```
import requests

api_endpoint = 'https://nubela.co/proxycurl/api/linkedin/company/employees/'
api_key = 'YOUR_API_KEY'
header_dic = {'Authorization': 'Bearer ' + api_key}
params = {
    'enrich_profiles': 'enrich',
    'role_search': '[Ff][Oo][Uu][Nn][Dd][Ee][Rr]',
    'page_size': '100',
    'employment_status': 'current',
    'resolve_numeric_id': 'false',
    'url': 'https://www.linkedin.com/company/microsoft',
}
response = requests.get(api_endpoint,
                        params=params,
                        headers=header_dic)
```

Using this endpoint will cost you 3 credits / employee returned.

You can purchase the credits at [Proxycurl](https://nubela.co)

The output to our code is

```
{
    "employees": [
        {
            "profile": {
                "accomplishment_courses": [],
                "accomplishment_honors_awards": [],
                "accomplishment_organisations": [],
                "accomplishment_patents": [],
                "accomplishment_projects": [],
                "accomplishment_publications": [],
                "accomplishment_test_scores": [],
                "activities": [],
                "articles": [],
                "background_cover_image_url": null,
                "certifications": [],
                "city": "Seattle",
                "connections": null,
                "country": "US",
                "country_full_name": "United States of America",
                "education": [
                    {
                        "degree_name": null,
                        "description": null,
                        "ends_at": {
                            "day": 31,
                            "month": 12,
                            "year": 1975
                        },
                        "field_of_study": null,
                        "logo_url": "https://media-exp1.licdn.com/dms/image/C4E0BAQF5t62bcL0e9g/company-logo_400_400/0/1519855919126?e=1672876800\u0026v=beta\u0026t=9twXof1JlnNHfFprrDMi-C1Kp55HTT4ahINKHRflUHw",
                        "school": "Harvard University",
                        "school_linkedin_profile_url": null,
                        "starts_at": {
                            "day": 1,
                            "month": 1,
                            "year": 1973
                        }
                    },
                    {
                        "degree_name": null,
                        "description": null,
                        "ends_at": null,
                        "field_of_study": null,
                        "logo_url": "https://media-exp1.licdn.com/dms/image/C4D0BAQENlfOPKBEk3Q/company-logo_400_400/0/1519856497259?e=1672876800\u0026v=beta\u0026t=v7nJTPaJMfH7WOBjb22dyvNKxAgdPdVd8uLCUkMB1LQ",
                        "school": "Lakeside School",
                        "school_linkedin_profile_url": null,
                        "starts_at": null
                    }
                ],
                "experiences": [
                    {
                        "company": "Breakthrough Energy ",
                        "company_linkedin_profile_url": "https://www.linkedin.com/company/breakthrough-energy/",
                        "description": null,
                        "ends_at": null,
                        "location": null,
                        "logo_url": "https://media-exp1.licdn.com/dms/image/C4D0BAQGwD9vNu044FA/company-logo_400_400/0/1601560874941?e=1672876800\u0026v=beta\u0026t=VKb6OAHEwlnazKYKm4fc9go-y4zkUv2BT6tosOdQ54Y",
                        "starts_at": {
                            "day": 1,
                            "month": 1,
                            "year": 2015
                        },
                        "title": "Founder"
                    },
                    {
                        "company": "Bill \u0026 Melinda Gates Foundation",
                        "company_linkedin_profile_url": "https://www.linkedin.com/company/bill-\u0026-melinda-gates-foundation/",
                        "description": null,
                        "ends_at": null,
                        "location": null,
                        "logo_url": "https://media-exp1.licdn.com/dms/image/C4E0BAQE7Na_mKQhIJg/company-logo_400_400/0/1633731810932?e=1672876800\u0026v=beta\u0026t=Mz_ntwD4meCMcgo1L3JqDxBQRabFLIesd0Yz2ciAXNs",
                        "starts_at": {
                            "day": 1,
                            "month": 1,
                            "year": 2000
                        },
                        "title": "Co-chair"
                    },
                    {
                        "company": "Microsoft",
                        "company_linkedin_profile_url": "https://www.linkedin.com/company/microsoft/",
                        "description": null,
                        "ends_at": null,
                        "location": null,
                        "logo_url": "https://media-exp1.licdn.com/dms/image/C560BAQE88xCsONDULQ/company-logo_400_400/0/1618231291419?e=1672876800\u0026v=beta\u0026t=I1mJMWAR_W2R_0h-lyL9Ln1ewby1Gg7ExCbpzhMJr5g",
                        "starts_at": {
                            "day": 1,
                            "month": 1,
                            "year": 1975
                        },
                        "title": "Co-founder"
                    }
                ],
                "first_name": "Bill",
                "full_name": "Bill Gates",
                "groups": [],
                "headline": "Co-chair, Bill \u0026 Melinda Gates Foundation",
                "languages": [],
                "last_name": "Gates",
                "occupation": "Co-chair at Bill \u0026 Melinda Gates Foundation",
                "people_also_viewed": [],
                "profile_pic_url": "http://localhost:4566/proxycurl-web-dev/person/williamhgates/profile?X-Amz-Algorithm=AWS4-HMAC-SHA256\u0026X-Amz-Credential=%2F20221003%2F%2Fs3%2Faws4_request\u0026X-Amz-Date=20221003T091809Z\u0026X-Amz-Expires=3600\u0026X-Amz-SignedHeaders=host\u0026X-Amz-Signature=653f499173f225e30141b4f7ff86e45b16a4fdb6cc91fec10f395fb27427ad26",
                "public_identifier": "williamhgates",
                "recommendations": [],
                "similarly_named_profiles": [],
                "state": "Washington",
                "summary": "Co-chair of the Bill \u0026 Melinda Gates Foundation. Founder of Breakthrough Energy. Co-founder of Microsoft. Voracious reader. Avid traveler. Active blogger.",
                "volunteer_work": []
            },
            "profile_url": "https://www.linkedin.com/in/williamhgates"
        }
    ],
    "next_page": null
}
```

Using the code will basically bring out al the bio-data of all the employees present in the company.

But if you need a specific employee details you can use the [Employee search api point](https://nubela.co/proxycurl/docs#company-api-employee-search-api-endpoint).

You can reach out to me if you need any assistant with using this endpoint I'll be glad to help.

You can check out our other articles:

[The Ultimate Guide to Alternative Data - What Is It Really?](https://nubela.co/blog/the-ultimate-guide-to-alternative-data-what-is-it-really/)
