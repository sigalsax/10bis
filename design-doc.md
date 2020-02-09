# 10bis project

## Motivation

An single-page application that simplifies the 10bis food ordering process by allowing users to choose from their top 3 most-ordered meals. Because in the end, we are creatures of habit and usually order the same meal everyday, so why not limit the effort it takes to order?

## Scope

### Flow

1. User login attempt

    1. If successful, return user token and top 3 meals

    1. Otherwise, error with proper error status

1. User selects (radio button) the meal of their choice

    1. Edge case: if user is new, there is no favorite meals. Return an image with proper explanation

1. When ready to place order, user clicks "submit" button

1. Order is placed for user and 10bis sends an email order confirmation as they currently do.

If user revisits the page, they can cancel and update (each time receiving update email)

## Phase 0 Design phase

- Understand how to communicate with 10bis API and retrieve specific user information
   
    - Login, POST, https://www.10bis.co.il/Account/LogOnAjax w/ username and password in body
   
    - getUserAddress, POST https://www.10bis.co.il/NextApi/GetUserAddresses w/ userToken in body or header of request
    
    - getUserOrderHistory, GET https://www.10bis.co.il/NextApi/GetUserOrdersHistory w/ userToken, culture, uiCulture, timestamp, addressID in body or header of request
    
    - getPayment, understand payment REST call chain

### Open questions

- How to handle payment? Seems there are a lot of REST calls for order placement. Do I need to perform each of them? or would one ideally cascade a chain of calls?

- Why "nextApi"? Would it be next or nextApi?


## Phase 1 (3 weeks)

What will be accomplished:

- Build user flow and process diagram call chain to map out interactions

- Send initial requests and confirm that the endpoints work using Postman (DONE)

- Build router middleware
    
    - /login, /getUserAddress, etc
    
- Build models (User, Dish, Favorites (list of Dishes), Login, LoginModel (username and password)

### Phase 2

TBT