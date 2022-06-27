# Store
## Table of contents
- [Introduction](#introduction)
  * [Description and requirements](#description-and-requirements)
  * [Installation](#installation)
- [Apps Implementation](#apps-implementation)
  * [Models](#models)
    + [User Profile](#user-profile)
    + [Post](#post)
    + [Comment](#comment)
    + [Like](#like)
    + [Following](#following)
  * [Views](#views)
    + [index](#index)
    + [post_comment](#post-comment)
    + [user_profile](#user-profile)
    + [edit_profile](#edit-profile)
    + [like](#like)
    + [following](#following)
    + [follow_unfollow](#follow-unfollow)
    + [login_view](#login-view)
    + [logout_view](#logout-view)
    + [register](#register)
  * [Tests](#tests)

# Introduction
## Description and requirements
Using Python, Django, Django Rest Framework complete the implementation of a Store that allows users to make carts, add item to carts, access to end point with permissions and ... . 

You must be registered to use options such as viewing some endpoints.

## Installation
To set up this project on your computer:
1. Clone the project
2. Install all necessary dependencies
    ```python
        pipenv install
    ```
3. Make a migration
    ```python
        python manage.py migrate
    ```
# Apps Implementation
## Core
### Models
Contains User Model extension with additional fields.

#### USER 
Fields:
* Email : register with email

### Post 
Contains all post info.

Fields:
* user - who posted the post
* content - post's inner text
* date - post's publication date

### Comment
Contains all comment info.

Fields:
* user - who posted the comment
* post - the post which is being commented
* content - comment's inner text
* date - comment's publication date

### Like 
Contains all like info.

Fields:
* user - who liked a post/comment
* post - the post which has been liked
* comment - the comment which has been liked
* emoji_type - the emoji used as a like, available emojis:
    1. like
    2. dislike
    3. smile
    4. heart
    5. thanks

### Following 
Contains all who follows who info.

Fields:
* user - user who is following
* user_followed - user who is being followed

## Views
### index
Here you can:
* View all posts
* Edit posts (if you are the post's creator; only for logged-in users)
* Delete posts (if you are the post's creator; only for logged-in users)
* Like them (only for logged-in users)
* Create a new post (only for logged-in users)
* View all comments (only for logged-in users)
* Create a comment (only for logged-in users)
* Delete a comment (if you are the comment's creator; only for logged-in users)
* Edit a comment (if you are the comment's creator; only for logged-in users)

### post_comment 
(only for logged-in users)

Controls saving of a new post/comment (only POST method allowed).

### user_profile
(only for logged-in users)

Here you can:
* View user's bio
* View all user's posts
* Edit posts (if you are the post's creator)
* Delete posts (if you are the post's creator)
* Like them 
* View all comments on user's posts
* Create a comment
* Delete a comment (if you are the comment's creator)
* Edit a comment (if you are the comment's creator)
* Follow the user (if you are not this user)
* Click on edit profile button (if you are this user)

### edit_profile
(only for logged-in users)

Here you can:
* Change your *name*
* Change your *birthdate*
* Change your *about info*
* Change your *profile picture*
* Change your *country*

### like
(only for logged-in users)

Controls all actions regarding liking:
* Add a new like
* Change a like's emoji

### following
(only for logged-in users)

Here you can:
* View all posts created by followed users
* Like them
* View all comments
* Create a comment
* Delete a comment (if you are the comment's creator)
* Edit a comment (if you are the comment's creator)

### follow_unfollow
(only for logged-in users)

Controls following/unfollowing users (only POST method allowed).

### login_view
Controls logging in.

### logout_view
Controls logging out.

### register
Controls registration.

## Tests
There are 4 main test cases:
* ModelsTestCase - checks database integrity
* FormsTestCase - makes sure that forms work correctly
* ViewsTestCase - makes sure that all views work correctly and give proper responses
* FrontEndTestCase - uses Selenium to simulate user interaction with every element on the page

Test requirements can be viewed in [test requirents.md](https://github.com/serwatka-w-proszku/CS50-Network/blob/master/test%20requirements.md)

---
Special thanks to Brian and the entire CS50 team for making learning easy, engaging, and free.
