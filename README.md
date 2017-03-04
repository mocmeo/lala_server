# lala-server

A RESTful API built with Node.js and [Express 4](http://expressjs.com/).

## Running Locally

Make sure you have [Node.js](http://nodejs.org/) installed.

```sh
$ git clone https://github.com/mocmeo/lala_server.git # or clone your own fork
$ cd lala_server
$ npm install
$ npm start
```

Your app should now be running on [localhost:5000](http://localhost:5000/).

## Deploying to Heroku

The application will automatically deploy for master branch. Heroku will build and deploy all pushes to that branch.

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

## Documentation

For more information about our API, check out this guides:

**Table of Contents** 

# Prefix: /api
## Sample acc:
username: admin
pass: 123456


# ===================== USER SIDE ==============================
##create new user:
POST: /users

##get users list:
GET: /users

##view particular user info:
GET: /users/:user_id

##update info + delete my account:
PUT: /home
DELETE: /home


#===================== ACTION ==============================
##Following + Unfollow someone:
PUT: /home/following_people/:following_id (add to "followings")
PUT: /users/:following_id/followers (add to someone's follower list)

DELETE: /followings/:following_id (remove from "followings")
DELETE: /users/:following_id/followers (remove from someone's follower list)



##Following + Unfollow a post (for current user):
PUT: /home/following_posts/:post_id (add to "following_posts")
DELETE: /home/following_posts/:post_id

PUT: /posts/:post_id/followers
DELETE: /posts/:post_id/followers


##Following + Unfollow a category (for current user):
PUT: /home/following_categories/:category_id (add to "following_categories")
DELETE: /home/following_categories/:category_id

PUT: /category/:category_id/followers
DELETE: /category/:category_id/followers



##Following + Unfollow a tag (for current user):
PUT: /home/following_tags/:tag_id (add to "following_tags")
DELETE: /home/following_tags/:tag_id

PUT: /tags/:tag_id/followers
DELETE: /tags/:tag_id/followers



##Add/Remove post to a category:
PUT: /category/:category_id/posts/:post_id
PUT: /posts/post_id (change "categoryId" in put request)

DELETE: /category/:category_id/posts/:post_id
PUT: /posts/post_id (change "categoryId" in put request to "")



##Add/Remove post to a tag:
PUT: /tags/:tag_id/posts/:post_id
PUT: /posts/:post_id/tags/:tag_id

DELETE: /posts/:post_id/tags/:tag_id
DELETE: /tags/:tag_id/posts/:post_id


##Create new comment + Get all comments from post: 
POST: /posts/:post_id/comments
GET: /posts/:post_id/comments


##Add/Remove comment to post (add/remove to comments array) 
PUT: /posts/:post_id/comments/:comment_id
DELETE: /posts/:post_id/comments/:comment_id


##Post/Get all posts from particular category:
GET: /category/:category_id/posts
POST: /category/:category_id/posts


##Get all posts by particular user:
GET: /users/:user_id/posts

##Get all posts by current user:
GET: /home/posts

#===================== POST SIDE ==============================
##Add new post:
POST: /posts

##Get posts:
GET: /posts

##CRUD with particular post:
GET: /posts/:post_id
PUT: /posts/:post_id
DELETE: /posts/:post_id

#===================== COMMENT SIDE ==============================

##Get all comments (of current user):
GET: /comments

##CRUD for particular comment:
GET: /comments/:comment_id
PUT: /comments/:comment_id
DELETE: /comments/:comment_id

#===================== CATEGORY SIDE ==============================
##Create new category
POST: /category

##Get all categories
GET: /category

##Get a particular category:
GET: /category/:category_id

#===================== TAG SIDE ==============================
##Create new tag
POST: /tags

##Get all tags
GET: /tags

##Get a particular tag:
GET: /tags/:tag_id
