---
layout: post
title: Blocitoff
thumbnail-path: "img/blocitoff.png"
short-description: Blocitoff is a to-do list application where users can add to-do items which they can later mark as done. The said to-do items expires after a week.

---

{:.center}
![]({{ site.baseurl }}/img/blocitoff.png)

## Explanation

Blocitoff is a to-do list project and a part of the Bloc rails curriculum. It enables user to add to-do items which can be marked as done or expires after 7 days.

## Problem

1. Create and register users.

2. Create own profile page

3. Create, show, edit and delete(marking as complete or by expiration after 7 days) to-do items and displaying the time remaining for each post.

4. Design the project

## Solution

1. In creating users, i used Devise gem which pretty much does all the job for creating users. It pre sets all the user models, registration controllers and views.

2. In creating my profile page, i created a new controller named users_controller and there i set all the configurations to display the items i created and its corresponding functionalities such as the button to mark the item as complete.

3. As for item CRUD, i generated a new model name item and associated it to user by using belongs_to. I also defined in the aforementioned model the time_in_words and the delete_expired_items which automatically deletes the item if its more than 7 days.

I also generated an items controller and write all the necessary codes to display items, edit, at mark as done using a checkbox.

4. I used the users view since i will display the list in my on profile. I configured all the item views. Dont forget to configure the routes.

## Results

Blocitoff is a simple app, i was able to finish it early as compared to other projects. The items is rendered in a tabled position and the checkboxes are right next to each item. Each item which exceeds 7 days from creation thereof are automatically delete.

## Conclusion

Blocitoff, eventhough it looks simple as it is, still gave me important ideas and features as i progress on my curriculum. It provided me on how to use checkboxes, and self destruct function.
