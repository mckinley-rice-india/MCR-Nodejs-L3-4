
# Mckinley & Rice NodeJs Coding Challenge

> Welcome to the Mckinley & Rice Coding Challenge!


## Overview

To complete this challenge, you will need to write a  web app, and provide us the source files to be built.

This challenge is expected to take about 2- 4 hours.


# Task-Queue-Challenge

## Challenge: 
Create a job queue whose workers fetch data from a URL and store the results in a database.  The job queue should expose a REST API for adding jobs and checking their status / results.
## Example:
User submits www.google.com to your endpoint.  The user gets back a job id. Your system fetches www.google.com (the result of which would be HTML) and stores the result.  The user asks for the status of the job id and if the job is complete, he gets a response that includes the HTML for www.google.com

## Solution:
A job queue created using the Redis database and Kue, a priority job que. First, add new jobs by running:
```bash
curl localhost:5000/create/www.facebook.com
```
Or just enter the browser and type, http://localhost:5000/create/www.facebook.com

A response will return a job number, "Your new id for the url is 7"

Now, to verify if it has completed, enter in the job number, run 
```bash
curl localhost:5000/status/7
```
If the website is still in the queue, you will see a message that states that "This task is still running". Otherwise, you will see the HTML of the website being referred to. 


## To Run: 
First start your Redis server:
```bash
redis-server
```
Now run the program:
```bash
npm i 
npm test
```
