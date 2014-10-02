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
 * Interrests - A user will specify interrests, and will get posts on their wall under that interrest. A user would be told to specify interrests a post fills when they post

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
 * gender - 0 for male, 1 for female
 * password - SHA512 hashed password

Interrest table:

 * id - ID of interrest
 * name - Name of interrest
 * desc - max 512 characters. Auto-fetched from wikipedia?

UserInterrest table: - has interrests user has specified. A user would have an entry in here for every interrest they have

 * id - ID of entry
 * userId - user the entry is about
 * interrestId - interrest id this entry is about

PostInterrest table: - Has interrests a post fits in

 * id - ID of entry
 * postId - post the entry is about
 * interrestId - interrest the entry is about

Other
-------

Users are "linked"/identified using &, like twitter uses @. You can't click it, but it is used to identify if a user is mentioned. Should also be highlighted.
Users should be able to report a post as being "Not in interrest". This is not needed yet.