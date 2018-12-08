---
templateKey: blog-post
title: My Second Week - Lambda Labs
date: 2018-11-15T15:04:10.000Z
description: My second-week journey in Lambda Labs building the Auto Invoicer!!
tags:
  - Week Two
---
![Contribution Chart](/img/contributionsgit111518.png)

# Detailed Analysis

This week I choose to do the Stripe front-end and back-end. This was by far the most challenging task I have taken on so far. My first order of business was to research Stripe API. When I was done I decided to go with a package called `stripe-react-checkout`. My initial implementation of this package to the front end was good.

![Stripe Button](/img/stripebutton.png)

![Strip Checkout ](/img/stripecheckout.png)

Now it was time to do the backend. Midway into researching the backend, it dawns on me that the `stripe-react-checkout` may not be the best solution for us because we are a subscription app and the checkout feature is for item checkouts and not subscription based checkout. So I started to do more research on subscription-based packages for Stripe and found `stripe-react-elements`. I quickly realized this implementation was going to be much more challenging than the first one. After some trial and error, I enlisted the help of my teammate [Mark](https://github.com/markdavidwilliams). Using VS Code we started a live share session.

First, we created the `CheckoutForm.js` component with the guidance of the Stripe documentation.

![Checkout Form](/img/checkoutform.png)

After we tested we realized we were not getting the expected result because we didn't create the endpoint. We then created out endpoint.

![Charge JS](/img/chargejs.png)

###### Finally! The results we wanted.

![Stripe Dashboard](/img/stripedashbard.png)

# Milestone Reflections

This week we all worked well with each other again. Lots of pair programming going on. No conflicts what so ever.

# Submitted Work

## Front End

* Ticket 1
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/25>
  * Trello: <https://trello.com/c/NDgKYKjg>
* Ticket 2
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/37>
  * Trello: <https://trello.com/c/NDgKYKjg>

## Back End

* Ticket 1
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/8>
  * Trello: <https://trello.com/c/NDgKYKjg>
* Ticket 2
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/37>
  * Trello: <https://trello.com/c/NDgKYKjg>

# Group Work

Backend: <https://api-auto-invoicer.now.sh/>

Frontend:[ https://auto-invoicer.now.sh/](https://auto-invoicer.now.sh/)

# White Board Interview

<iframe width="560" height="315" src="https://www.youtube.com/embed/ALw0wYPtkZE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
