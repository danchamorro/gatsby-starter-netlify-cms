---
templateKey: blog-post
title: My Third Week - Lambda Labs
date: 2018-11-30T15:04:10.000Z
description: My third-week journey in Lambda Labs building the Auto Invoicer!!
tags:
  - Week Three
---
![Contribution Chart](/img/contribution113018.png)

# Detailed Analysis

This week I worked on multiple front-end functionality jobs. I paired programmed with one of my teammates mark couples times as well. One of the first things I did on the beginning of the week implemented a package called `concurrently`. This helped my team be able to run the frontend server and backend server at the same time with one command `yarn run dev`.  After installing the package there were some configuration changes that needed to be made to the `package.json` on the server side. 

![Package.json](/img/packagejson.png)

Next Mark and I starting pair programming to get our Stripe form to accept a charge for a variable amount. This was tougher than it sounds. The main issues were that a user could pay $0.99 for a single credit, but the user could also pay $9.99 for unlimited credits. In the end, we ended up writing some logic to check if the user chooses one over the other we would update the credits accordingly.

![Checkout Form ](/img/checkoutform1130.png)

The next requirement was for me to figure out how to update the city and state of our invoice form by only typing in the zip code. For this, I used google's Geolocation API. After I implemented it I noticed some bugs. When I used the zip code it would you give you a city and a state and other times it gave you a city and a county instead. I then enlisted the help of Mark. Together we brainstormed the best approach.

![Invoice Form](/img/invoiceform113018.png)

# Milestone Reflections

This week we all worked well with each other again. Lots of pair programming going on. No conflicts what so ever.

# Submitted Work

## Front End

* Ticket 1
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/45>
  * Trello: <https://trello.com/c/RwLnAGlX>
* Ticket 2
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/46>
  * Trello: <https://trello.com/c/OljZqcO2>
  * Trello: <https://trello.com/c/PvuFuQoh>
* Ticket 3
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/58>
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/55>
  * Trello: <https://trello.com/c/1ZTkgaOJ>
  * Trello: <https://trello.com/c/0YMWEvv5>

# Group Work

Backend: <https://auto-invoicer.now.sh>

Frontend:<https://auto-invoicer.now.sh>

# Whiteboard Interview

<iframe width="560" height="315" src="https://www.youtube.com/embed/QotZbvdkqb0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


