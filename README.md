# wso2apim-monetization-demo
A Docker Compose based WSO2 API Manager Monetization Demo

## Steps
The purpose of the demo to demonstrate WSO2 API Manager Monetization capability by generating an invoice for a sample API.

### Step 01: Starting the servers
Boot up the docker compose setup by issuing following command and wait until every server is up and running(you can watch the logs through `docker-compose logs -f` and ensure the successful server start up).

`docker-compose up -d`

### Step 02: Adding DNS for Billing Engine
Add following to /etc/hosts.

`127.0.0.1       billing-engine`

### Step 03: Deploying A Sample API
Access the publisher at [https://localhost:9443/publisher] and login using default credential(admin:admin). Then deploy the sample.

### Step 04: Defining Billing Plan
Login into [Billing engine](http://billing-engine:8080/apim-billing-engine-1.4.0/) using the defualt credentials(admin:admin) and define a plan for the sample API. After creating the billing plan, makesure to logout of the application.

### Step 05: Subscribing the API
Login into [Store](https://localhost:9443/publisher) using defualt credential(admin:admin) and subscribe to the sample API. During the subscription process it will direct to the billing engine. Sign up as a new user in the billing engine, login using the new user credential and subscribe to the billing plan.

### Step 06: Invoking the API
Login into [Store](https://localhost:9443/publisher) using defualt credential(admin:admin) and generate token for the application used to subscribe in previous step.
Invoke the API with the token multiple time(Do it in a loop).

### Step 07: Generating Invoice
Login into [Billing engine](http://billing-engine:8080/apim-billing-engine-1.4.0/) using the defualt credentials(admin:admin) and generate invoice by clicking invoice button. Select the current month and admin user as subscriber and it will generate invoice for the admin user for current month.

