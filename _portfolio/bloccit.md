---
layout: post
title: Bloccit
thumbnail-path: "img/blocipedia.png"
short-description: Bloccit is a reddit replica where users can create topics and its posts. Users can also leave a comment on each topic as well as the ability to upvote or downvote a comment to their own liking.

---

{:.center}
![]({{ site.baseurl }}/img/blocipedia.png)

## Explanation

    Bloccit is the first ever project i worked as a bloc student. This is what i consider the cornerstone of software developer career.

    This project is mostly about interacting to a community on a particular topic. An author can create a post under a certain topic with the purpose of discussion. Other users then can share their opinions with respect to the post.

## Problem

  1. Create and register users

  * users are then classified into admin, members and guests.

  2. Create Topics.

  3. Create posts under Topics.

  * add favorite button.
  * add labels to associate topics and posts.

  4. Create comments integrated to posts.
  * add voting function where user can upvote or downvote comments.

  5. Add sample posts, topics and comments

  6. Design the project.

## Solution

  1. I first created a user model which will store all the necessary attributes of users such as name, email and passwords. Next is creating user controllers. It is where we will define all the necessary action/function in creating, showing, editing and destroying users.

  * In order to add authorization roles on users. You must add a migration which specifies that you are adding a role attribute to users. After doing so, you define the roles in the user model (e.g admins, members and guests). Then you must define the authorized actions ( as a private method ) in the controllers in which you want to use user authorizations.

  2. First of all, you need to create a topic model and migrate it. Then you create a topics controller where you will also define all the methods needed. Remember to associate topics and users using belongs_to and has_many association methods. Lastly, configure the routes..

  3. Create posts model, define the association with topics and all necessary codes and then migrate. Afterwards, create a post controller conatining all the necessary methods in creating the same and you need to configure the routes as well.

  * create a favorite model which references to users and posts then migrate it. Define the favorite method in which it retrieves a post's id. You also need to associate the same to users and posts since it is under it. Then, generate a controller in which you will define the method of favoriting and removing a favorited post. Then design the favorite button.

  * In creating labels, i used many-to-many relationship. I created a label model and then created a custom migration. I then created a new model named labelings which will serve as the medium of many-to-many relationship association. I associated label and posts through labelings. I went on to create label controller where i defined the label show method. Then configure the design of the label tabs.

  4. As for comments, i generated a comment model and associated it with posts using has_many and belongs_to. I then created a comments controller to configure all the methods for displaying, creating, editing and destroying posts.

  * As for voting features, i created a new vote model which references to users and posts and then migrate it. Then i will associate it with post and users by saying that it belongs_to post and users at the same time im going to add that user and posts has_many votes. I also defined the upvotes and downvotes in post model since im going to render it inside a post. After this, i generated a votes model to define the necessary methods of upvoting and downvoting posts.

  5. As for making sample posts and topics, i generated a seeds file. Inside a seeds file, i applied all the formulas of creating sample topics, posts, comments and votes using RandomData.

  6. I first configured all the models' respective views (e.g post/show.html.erb and topic/show.html.erb). The comment and votes models were rendered in posts show view and with the help of ajax. I also used embedly to add some features on my project.

## Results

I used the seed files in order to create pre made topics, posts, comments. I had a lot of trouble as i progress on my project since im still on the stage of familiarizing myself with rails. But i was able to solve some of the problems with the help of my mentor. The results are quite really similar to reddit. There are topics in which i can add a post, other users can leave their comment. They can also upvote and downvote comments.

## Conclusion

Being my first rails project, there's no doubt that this is one of hardest project i made. But as i progress through my work, i'm starting to understand the nature of rails little by little. In this project i first understood how models, controllers and view integrate with each other.
