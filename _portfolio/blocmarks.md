---
layout: post
title: Blocmarks
thumbnail-path: "img/blocitoff.png"
short-description: Blocmarks is an application that allows a user to bookmarks URLs via email, peruse other user's bookmarks and maintain a personal index of categorized bookmarks.

---

{:.center}
![]({{ site.baseurl }}/img/blocitoff.png)

## Explanation

Blockmarks is a bookmark managing app where users can add a bookmark manually or through email. With blocmarks, users create a topic and add bookmarks in it.

## Problem

1. Creating and registering users.

2. Create, show, edit and destroy topics.

3. Create, show, edit and destroy bookmarks.

  * Bookmark owners are the only ones allowed to edit and destroy their email.

  * Add the ability for users to like/unlike bookmarks

4. Create a user profile.

  * Show added and liked bookmarks in the user's own profile page.

## Solution

1. I used devise gem to create and register users. It's a handy gem that generates the necessary models, controllers, migrations and views to create users.

2. Topic CRUD includes creation of topic model and controller. Keep in mind also to associate it with users using belongs_to and has_many method. I configured the topic index, show, create, edit and destroy actions in topics controller.

3. Configuring the bookmark CRUD is similar with topic CRUD. I created a bookmark model, associate it with topic using belongs_to and has_many migrated it and added all the necessary codes. I then went to proceed on generating bookmarks controller defined all the action to create, display, edit and destroy bookmarks.

  * I added the Pundit gem to implement user authorizations. I configured the application policy of blocmarks and made sure the owners of the bookmarks are the only ones to edit and destroy their posts.

  * To add a like function, i added a new model named like, and associated it with user and bookmarks. I generated a likes_controller afterwards and defined likes create and destroy actions.

4. For this task, generated a new controller named users. This will serve as the backbone of my user profile. I defined the like action, like_bookmarks and created_bookmarks in user model. As for the controller, i added new variables that defined user_bookmarks(bookmarks created by user) and liked_bookmarks(bookmarks liked by user). I further added the necessary codes to display the aforementioned bookmarks in users view.

## Results

I was able to create an application in accordance to curriculum. I can create, edit, show, and destroy topics. I can also create, edit and destroy bookmarks under topics provided that they have the authority to do so. Users have the ability like bookmarks and display it on their profile page.

## Conclusion

As i work on this project, i noticed that this has a lot of potential. The project is simple yet with the right design, i would almost simulate a social media app at the same time a bookmark app. This is the second project i've done next to bloccit. It initially gave me the idea of grouping models such as displaying liked bookmarks in a profile page without much help. As a student myself, i'm definitely going to use it in the future as i also save a lot of bookmarks with my browser. 
