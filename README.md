# UnityShowcaseApp
A simple web app to focus on one project picked from MadeWithUnity showcase and show any available content for that project.

Language Choice: python

## other requirements
1. Each time refreshing the broswer, should show a different project from previous viewing

Ideally, we want a single user to see all n projects if he refresh the main page for n times. The problem is how can we remember the user to show them different content each time and somehow remember what each user viewed previously?

Thoughts: We might need to implement feature for session.

Result: Use web framework to handle session management
in this project, we chose Flask to minimize the server design

Challange: How to identify a user without login?

Solution: We choose to identify users by ip addresses
(i.e. see users different if ip addresses are different)

2. all contents are referenced from the external sources

Thoughts: We might need to crawl / reference data from other domain, MadeWithUnity in this case

Result: use Requests-html that provides easy way for parsing html

Challenge: How to deal with relative path?

Solution: