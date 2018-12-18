<!-- TITLE: Home Page -->
<!-- SUBTITLE: A quick summary of Home Page -->

# Header
Related:
Order Page - https://docs.google.com/document/d/15ZAMvUBNZhttuhD2kN9or24HJRqAmr7huRSxkotEZGQ/edit?usp=sharing



	Entry point
base_url/home 
This is a EXACT path of the page
base_url/
This will go to main content page of the system, where system shall check if user already logged in, or has any active session bound to them. If no active session, then shall redirect back to this page
When user visit any invalid route, user will be redirected back to this page
Valid: base_url/1/category
Invalid: base_url/mysupertable/your_are_stupid
After made complete settlement and admin decides to close the order session, Firebase will be updated and listener shall be fired to redirect user back to this page

How to use (user perspective)
Tap on Scan QR button
App will request permission to use camera, click allow
QR scanner will run
After successfully scan a valid QR code, will redirect the food ordering page

	Implementation
When user redirected to /home from ANY of the entry points
Check if has table_id attached to the session
YES
Check order session id
HAS order session id
Check if order session is expired/closed
YES - Clear the session ID, proceed to (2)
NO - Proceed to (2)
Redirect to /{table_id}/category, END
NO - Show the home page and wait for user to trigger QR scan
After scan QR and QR is of valid URL “https://minipos.goodfriends.com.my/{table_id}/category”
YES -  Redirect to /{table_id}/category
NO - Show appropriate error message


