TELLo
========

Concept
--------

The concept of TELLo is to have a social medium only accessable through telnet. The idea is to base the social media off twitter, but allowing comments.

Featurelist
-----------

 * Posts - These are posted not as a reply of anything, but alone. 
 * Wall - This is a list of posts from users the logged in user is following
 * Comments - These are posted as a reply of a post. They are listed in order depending on the time they were posted

Technical structure
---------------------

Comments and posts share same table for easy use. Following is the structure

 * id - ID of post/comment
 * replyto - post this is reply to if comment, blank if post
 * timeposted - unix epoch time of post
 * postedby - ID of user who posted
 * contents - max 2048 char string - contents of post/comment

Users are stored separately

 * id - ID of user
 * username - name of user, max 16 characters
 * fullname - full name of user.
 * birthdate - unix epoch of user birth. not required
 * avatar - 5x4 char ascii avatar string
 * bio - max 512 characters description

Other
-------

Users are "linked"/identified using &, like twitter uses @. You can't click it, but it is used to identify if a user is mentioned. Should also be highlighted.