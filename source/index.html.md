---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - http
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - properties
  - property_savings
  - showing_requests
  - users
  - user_profiles
  - images
  - pets
  - employers
  - schools
  - cities
  - subway_lines
  - amenities
  - traits
  - rules
  - pagination
  - errors

search: true
---

# Introduction

Welcome to the Roomeze API! You can use our API to access Roomeze API endpoints, which can get information on various rooms, users, and buildings in our database.

You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

## Session Authentication

Roomeze uses session based authentication to allow access to the API. The server will create a session for the user after the user logs in. The session id is stored on a cookie on the user's browser. While the user stays logged in, the cookie is sent along with every subsequent request. 

<aside class="notice">
You must be signed in as a user with the <code>admin</code> role to make restricted API requests.
</aside>

You can sign in using the session api. The sign in page can be found [here](https://roomeze.com/users/sign_in).

You can create a new account using the registration api. The sign up page can be found [here](https://roomeze.com/users/sign_up).

## Api Token Authentication

```http
POST /api/users HTTP/1.1
Accept: application/json
Authorization: Token <YOUR_API_TOKEN>
Host: roomeze.com
```

For certain routes, Roomeze also supports API Token Authentication. First, you need to [create a new api key](https://roomeze.com/admin/api_keys)

<aside class="notice">
You must be signed in as a user with the <code>admin</code> role to create a new API key.
</aside>

<!-- <aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside> -->
