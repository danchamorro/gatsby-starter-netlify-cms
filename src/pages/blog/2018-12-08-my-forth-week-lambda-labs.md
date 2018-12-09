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

### Redirect User after Save of Invoice

My next task to was to redirect the user to the dashboard after they created an invoice. After searching online for the best method to accomplish this, I found the `<Redirect />` function that is a part of `react-router-dom`. This allows you to redirect the user to any page you want. The trick is to have this action take place after a save of an invoice. So I decided to add a property to the state called `toDashboard` and I set this to `false`. Then I found the `event handler` that handles the `onSubmit` of the form and placed a `setState` inside of that function.  So now whenever that function is called it will change the `toDashboard` to `true`. 

```javascript
this.setState({ toDashboard: true });
```

Now I can use a conditional to check if `toDashboard` is `true`, then use `<Redirect />` to do its magic. 

```javascript
if (this.state.toDashboard === true) {
      return <Redirect to="/" />;
    }
```

### Decrement User Credits

Next, I needed to decrement the user's credits everytime they created an invoice. For this, I made an `axios` call to the backend to first determine how many the credits the user has. Then in the same function, I decremented the user's credits by one. 

```javascript
decrementCredits = () => {
    axios
      .get(`/api/users/${this.mongo_id}`)
      .then(res => {
        let credits = res.data.credits;
        console.log(credits);
        axios
          .put(`/api/users/${this.mongo_id}`, {
            credits: (credits -= 1)
          })
          .then(res => {
            this.props.fetchUser();
          });
      })
      .catch(err => {
        console.log(err);
      });
  };
```

Finally, I added the function to the same logic I used for the redirect. Now when the user creates an invoice and gets redirected his credits will decrement at the same time. 

```javascript
if (this.state.toDashboard === true) {
      this.decrementCredits();
      return <Redirect to="/" />;
    }
```

### Redirect to Dashboard after Purchase

In this task I needed t redirect the user to the dashboard after they made a payment for a single credit. I used the same logic as I did with the redirect. 

### Prevent User from Creating Invoice on Zero Credits

My final task of the week was to prevent the user from creating additional invoices of they had zero credits. For this, I added a component called `AddInvoice`. This was just to render the add invoice button. That feature was already present but I extracted into its own component so I could use it in conditional rendering. Then I created a function to determine if the user has zero credits. If so he would see an add invoice but the button would read "Please Add Credits" and would link the user to the billing page. Else, it would link the user to create an invoice. 

```javascript
addInvoice = () => {
    if (this.props.credits > 0) {
      return <AddInvoice />;
    } else {
      return (
        <div className="create-new-invoice">
          <p> Please Add Credits </p>
          <Link to="/billing" exact>
            <button> + </button>
          </Link>
        </div>
      );
    }
  };
```

![Add Credits](/img/addcredits.png)

# Milestone Reflections

This week we all worked well with each other again. Lots of pair programming going on. No conflicts what so ever.

# Submitted Work

## Front End

* Ticket 1
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/68>
  * Trello: <https://trello.com/c/eaiNH4P5/97-style-landing-page>
* Ticket 2
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/76>
  * Trello: <https://trello.com/c/WdtYEpyE/116-change-font-color-and-padding-landing-page>
* Ticket 3
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/73>
  * Trello: <https://trello.com/c/tO6qtnuQ/100-redirect-to-invoice-list-after-creating-or-updating-invoice>
* Ticket 4
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/82>
  * Trello: <https://trello.com/c/rhjUZOst/110-decrement-user-credits-when-invoice-is-saved>
* Ticket 5
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/73>
  * Trello: <https://trello.com/c/XyJPX8Wd/138-redirect-to-createinvoice-after-purchasing-a-single-credit>
* Ticket 6
  * Github: <https://github.com/Lambda-School-Labs/Labs8-AutoInvoicer/pull/90>
  * Trello: <https://trello.com/c/N2Jeh8dP/120-dont-allow-user-to-create-invoice-if-zero-credits-give-an-alert>


# Group Work

Backend: <https://api-auto-invoicer.now.sh/>

Frontend:[ https://auto-invoicer.now.sh/](https://auto-invoicer.now.sh/)

# Whiteboard Interview

<iframe width="560" height="315" src="https://www.youtube.com/embed/B15jUuDyVYw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
