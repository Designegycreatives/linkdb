![6](https://user-images.githubusercontent.com/83256563/198080419-31dbf8ff-76cb-4f60-bd91-05ba730975ce.png)


Today, I want to show you how you can scrape data from linkedin using Proxycurl api, Python programming and nodejs.

Let's scrape data using python programming and the library request.

I am going to use the **Proxycurl Company api** to **[get the Employee Count Endpoint ](https://nubela.co/proxycurl/docs#company-api-employee-count-endpoint)**

install the package **request** 

```
!pip install requests
```

let's get our Proxycurl api create an account with[ Proxycurl](https://nubela.co/) and generate your api.

**Let's count the number of employees working at Apple.inc**

Using the library

```
import requests

api_endpoint ='https://nubela.co/proxycurl/api/linkedin/company/employees/count/'

api_key = 'YOUR_API_KEY_HERE'

header_dic = {'Authorization': 'Bearer ' + api_key}

params = {
    'linkedin_employee_count': 'include',
    'employment_status': 'current',
    'url': 'https://www.linkedin.com/company/apple/',
}

response = requests.get(api_endpoint,
                        params=params,
                        headers=header_dic)

```
The output response is:
`
{
 'total_employee': 94262,
 'linkedin_employee_count': 567686,
 'linkdb_employee_count': 94262
 }
`

Let's try to count the number of employees working at twitter

```
import requests

api_endpoint = 'https://nubela.co/proxycurl/api/linkedin/company/employees/count/'
api_key = '3HqZGXdoejPB8YYT4KRb3w'
header_dic = {'Authorization': 'Bearer ' + api_key}
params = {
    'linkedin_employee_count': 'include',
    'employment_status': 'current',
    'url': 'https://www.linkedin.com/company/twitter/',
}
response = requests.get(api_endpoint,
                        params=params,
                        headers=header_dic)

```

The output is

`{'total_employee': 7472,
 'linkedin_employee_count': 7992,
 'linkdb_employee_count': 7472
}`

You can try this with as many companies as possible

