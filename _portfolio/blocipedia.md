---
layout: post
title: Blocipedia
thumbnail-path: "img/blocipedia.png"
short-description: Blocipedia is a wikipedia replica where users can create wikis with their corresponding collaborators.

---

{:.center}
![]({{ site.baseurl }}/img/blocipedia.png)

## Explanation

Blocipedia is one of the projects included in my rails curriculum. It is a replica of wikipedia, where users have the ability to create, edit, and delete wikis.

## Problem

1. Create and register users

  * Users are classified into admin, standard and premium users. Standard users can upgrade their account from to premium

2. Create, show, update and destroy public wikis

  * premium users can create their own private wikis

3. Add and remove collaborators to wikis

## Solution

1. In creating users, i used devise gem. Devise is a handy gem which presets all the models, controllers and views needed. You are only left with the views for you to customize. Other than that, you're good to create users.

  * Another way to classify users is by using the Pundit gem.
  After installing pundit gem. First, i have to create a migration by adding role as an attribute to the user. I then defined the different kinds of user classification in user model(standard, premium, admin). In order to use standard users as the default classification, I defined the default role in a private method and used it with after_initialize method. I then configured my wiki_policy file.

2. I created the public wikis by first, generating wikis model, associating it with users and defining private and public wikis. In order to make public and private wikis work, i generated a migration which adds private attribute to wikis. Afterwards, i generated the wikis controller configure the necessary code to create, show, update and destroy wikis.

  * I implemented the user role upgrade by installing stripe gem first. Stripe is a gem which process payments through credit cards and other forms of online payments. I then generated a charges controller where i will put all the codes that will give the ability for stripe to charge to upgrade from standard user to premium. And since theres an option for me to upgrade an account, there should also be an option to downgrade. I defined upgrade/downgrade account first in user model and went to proceed on defining the action in charges controller. Lastly, i created all the necessary codes to display the charge button.

3. I implemented user collaborators by using a has_many_to_many relationships. I generated a new model named collaboration, added belongs_to user and wiki, i then added has_many collaborations in wiki and user model then i proceeded in migrating it. Lastly, i added all the required codes in wikis_controller to display the collaborators.

## Results

Although this particular project is quite hard since i got into trouble with many-to-many relationships, i was still able to finish it. Collaborators were rendering. The stripe button is working as well, as soon as the stripe payment is finished, the user is upgraded to premium and has the privilege to create private wikis. Users can also create, edit, and destroy wikis.


## Conclusion

The Blocipedia project provided me much more experience in creating web applications. It's quite flexible since it is comprise of several rails functions and gems such as CRUD, Pundit, Devise, Stripe and has-many-to-many relationships. It's difficult at first but as long as you get to understand the concept, you will definitely finish it. 
