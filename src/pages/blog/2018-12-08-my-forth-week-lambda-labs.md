---
templateKey: blog-post
title: My Forth Week - Lambda Labs
date: 2018-12-08T02:56:42.411Z
description: My forth-week journey in Lambda Labs building the Auto Invoicer!!
tags:
  - Week Four
---
![Contribution Chart](/img/contributions.png)

# Detailed Analysis

This week we primarily focused on the frontend. I choose to style the landing page. Styling is not my strong suit, but I picked it anyway so I can get better. First thing I did was find a theme online that I liked. Once I found what I wanted, I started to make it my own. 

![Landing Page](/img/landingpage.png)

My next task to was to redirect the user to the dashboard after they created an invoice. After searching online for the best method to accomplish this, I found the ```<Redirect />``` function that is a part of `react-router-dom`. This allows you to redirect the user to any page you want. The trick is to have this action take place after a save of an invoice. So I decided to add a property to the state called `toDashboard` and I set this to `false`. Then I found the `event handler` that handles the `onSubmit` of the form and placed a `setState` inside of that function.  So now whenever that function is called it will change the `toDashboard` to `true`. 

```javascript
this.setState({ toDashboard: true });
 ```

Now I can use a conditional to check if `toDashboard` is `false`, the use `<Redirect />` to do its magic. 
