![6](https://user-images.githubusercontent.com/83256563/198080819-03c25bb8-67ce-4b6a-8831-94025ed630d1.png)

Next let's try scraping data from linkedin using Proxycurl and Nodejs

Create a folder directory
cd c:\\User\user\Folder name
Build file package
npm install express axios dotenv

or with Yarn

yarn add express axios dotenv
Generate API key from proxycurl
API_KEY = 'YOUR_API_KEY_HERE'
Code snippet
import express from 'express';
import axios from 'axios';
import dotenv from 'dotenv';

const app = express();

dotenv.config();

app.listen(8000, () => {
    console.log('App connected successfully!');
});
// Getting Company's job listing

const TWITTER_URL = 'https://www.linkedin.com/company/twitter/';  // Line 1

const COMPANY_PROFILE_ENDPOINT = 'https://nubela.co/proxycurl/api/linkedin/company';

const JOBS_LISTING_ENDPOINT = 'https://nubela.co/proxycurl/api/v2/linkedin/company/job';

const JOB_PROFILE_ENDPOINT = 'https://nubela.co/proxycurl/api/linkedin/job';

const companyProfileConfig = {  // Line 2
    url: COMPANY_PROFILE_ENDPOINT,
    method: 'get',
    headers: {'Authorization': 'Bearer ' + process.env.API_KEY},
    params: {
    url: TWITTER_URL
  }
};

const getTwitterProfile = async () => {  // Line 3
    return await axios(companyProfileConfig);
}

const profile = await getTwitterProfile();

const twitterID = profile.data.search_id;

console.log('Twitter ID:', twitterID);


const jobListingsConfig = {
    url: JOBS_LISTING_ENDPOINT,
    method: 'get',
    headers: {'Authorization': 'Bearer ' + process.env.API_KEY},
    params: {
    search_id: twitterID // Line 4
    }
}

const getTwitterListings = async () => { // Line 5
     return await axios(jobListingsConfig);
}

const jobListings = await getTwitterListings();

const jobs = jobListings.data.job;

console.log(jobs);
// Specific Job listing code snippet

const jobProfileConfig = {
    url: JOB_PROFILE_ENDPOINT,
    method: 'get',
    headers: { 'Authorization': 'Bearer ' + process.env.API_KEY },
    params: {
        url: jobs[0].job_url   // Line 1
    }
};

const getJobDetails = async () => {  // Line 2
    return await axios(jobProfileConfig);
};

const jobDetails = await getJobDetails(); 

console.log(jobDetails.data);

How the package.json should look like;
{
  "name": "nubela",
  "version": "1.0.0",
  "type": "module",
  "description": "",
  "main": "proxycurl.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "axios": "^1.1.3",
    "dotenv": "^16.0.3",
    "express": "^4.18.2"
  }
}
You can try scraping any data of your choice from Linkedin using Proxycurl Api

References
Proxycurl API
Proxycurl Documentation
Node js
Proxycurl Writer
