# Performance-Testing-on-Test-Site

This performance testing was done on test website. Link: https://reqres.in/api/users?page=2

## Table of Contents


# Performance testing (Testing load and stress)



#### Maven dependencies - JUnit5 Jupiter Tests
JMeter is an open source performance testing tool, based on Java.

Download and Install JMeter
Go to the website https://jmeter.apache.org/download_jmeter.cgi
Go to the Binaries section and download the zip file

3. Open the zip folder that is installed and extract it

4. After the folder is extracted, open it and go to the Bin folder

5. In the bin folder, open jmeter (windows batch file)


It will take sometime to open JMeter. It will look like as shown in the below screenshot


For doing performance testing of API’s, I will use dummy APIs from https://reqres.in/.

Follow the below steps for setting up API’s for testing

Step 1: Test Plan

A Test Plan acts as a framework for conducting tests. It specifies what needs to be tested and the methodology to be used. A well-structured test plan typically includes components such as:

Thread groups
Logic controllers
Timers
Pre and Post Processors
Configuration Elements, etc.
It’s crucial to note that every test plan must include at least one thread group.

Step 2: Setting Up the Test Plan

Now, we have to create a “Thread Group”, to do so right-click on the "Test Plan," then navigate to "Add > Threads (Users) > Thread Group."


Thread Group is created as shown below:


To perform a load test, we need to put a lot of pressure on the API’s endpoint and we need to adjust the following settings in the Thread Group

Number of Threads (users): The number of users that JMeter will pretend to be.
Ramp-Up Period (in seconds): The time over which JMeter will spread out the starting of these users.
Loop Count: How many times JMeter will run the test.

Now, next is to add another element “HTTP Request” under “Thread Group” . To do so, right click on the “Thread Group, navigate to “Add > Sample > HTTP Request”


HTTP Request will be added under “Thread Group” as shown below


To set up a “GET” request, we will use dummy APIs from “https://reqres.in/"

GET Endpoint: https://reqres.in/api/users?page=2

Here are the fields, we need to configure:

Name: Change the name of the HTTP Request to “Get Users” since we are using a GET request.
Protocol: Specify the protocol being used, which is “https”.
Server Name or IP: Enter the server name, which is “reqres.in”.
HTTP Request: Since we are using the “GET” method, select “GET”.
Path: Specify the path of our URL, which is “api/users”.
Parameters: Add path parameters by clicking on the “Add” button. Set “Name” as “page” and “Value” as “2”.

Adding a Listener

Listeners display the results of a load test. JMeter offers various types of listeners.

For this test, using “View Results Tree” and “View Results in Table”.

To add these listeners:

Right-click on the “Thread Group”.
Select “Add > Listener > View Results Tree”.
Repeat the steps to add “View Results in Table”.


Both listeners are now added.

We need to save the test plan before running the test.

Running The Tests

Now that we have configured the test plan correctly, let’s run the test and see the results.

Select the “View Results Tree” element in the left pane.
Click “Run” from the main menu.
Click “Start” (or simply click the green Start arrow below the main menu), as shown in the screenshot below.


We received a 200 success response along with the response data, indicating that the GET request was successful. Please refer below screenshot:


Click on the “View Results in Table” to view the results as shown below:


In essence, we simulated 50 users accessing a single API endpoint over a span of 10 seconds, with 5 users starting every second.







####HTML Reports
===


```
