# blogger-import
Blogger (Google API) import script from basic RSS feed

This is a simple PHP script that will allow you to import any standard rss feed into Blogger blog (using Google APIs).

Download google-api-php-client first and extract it along with this script (https://github.com/google/google-api-php-client)

A few things you need to do first:
  Open up a google API/developer account and get it active, go to: https://console.developers.google.com/
  Create a project to use for this, create a simple name.
  Under "APIs & Auth" on the left, select APIs, then you need to enable "Blogger API v3"
  Under "Credentials" click "Create new client ID" and choose "Web application", Ensure Authorised Javascript and Authorised Redirect are set to your website URL. In my case I added all combinations (with www, without, with full /path/ and without to be sure!)
  That will then generate you the codes you need to edit into the script.
  Now create the PUBLIC api code, so click "Create new key" under public API access (for browser applications).

In index.php change "setapplicationname" to be the project name you created in Google.
change setClientID to be the client ID show to you in the developer console as client id (will look like a subdomain and end with .apps.googleusercontent.com)
Change ClientSecret to be the secret shown below Client ID in the google developer console.
Change setDeveloperKey to the key in your public API for browser applications.
Change getByURL to your blogger website address (either your own domain or something.blogger.com)
Finally you need to find your blogger ID, go into your blogger admin panel (as though you are about to post a blog entry) and in the address bar you'll see the numeric ID.

Once you've done all that, you can put your full.rss file into the same folder and it should upload your pages.
Whenn you visit the URL index.php will prompt for authority from Google, confirm that and it will begin importing.

LIMITATIONS:
  It won't import images, url's/images aren't translated they are left as is in the content.
  It doesn't 'parse' XML properly, it uses a few search/find strings and just copy exactly as seen.
  All posts are marked as DRAFT so you have to put them live.
  Posts are added with the original publish date, so in theory dates are preserved.
  
