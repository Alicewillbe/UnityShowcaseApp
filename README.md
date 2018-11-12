# UnityShowcaseApp
A simple web app to focus on one project picked from MadeWithUnity showcase and show any available content for that project.

Language Choice: python

## Requirements
###Each time refreshing the broswer, should show a different project from previous viewing

Ideally, we want a single user to see all n projects if he refresh the main page for n times. The problem is how can we remember the user to show them different content each time and somehow remember what each user viewed previously?

Thoughts: We might need to implement feature for session.

Result: Use web framework to handle session management
in this project, we chose Flask to minimize the server design

Challange: How to identify a user without login?

Solution: We choose to identify users by ip addresses
(i.e. see users different if ip addresses are different)

###all contents are referenced from the external sources

Thoughts: We might need to crawl / reference data from other domain, MadeWithUnity in this case

Result: use Requests-html that provides easy way for parsing html

Challenge: How to deal with relative path?

Solution: (invertion from relative path to absolute path is not supported by current version)

## Validation
Since the web server is not deployed, we can only validate it in local environment.

### user authentication
After initiating server, we request ```localhost:5000/``` on two different broswers, e.g. firefox and chrome, and should observe different projects every time refreshing the page.

### randomly picked projects
Direct observation gained from refreshing the page.

## Installation
```bash
git clone https://github.com/Alicewillbe/UnityShowcaseApp temp_XZ
cd temp_XZ
pip install flask
pip install requests
pip install requests-html

python app.py
```
Wait server to finish set up, and try connecting to ```localhost:5000/```
