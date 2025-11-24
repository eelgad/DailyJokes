# DailyJokes

Submitted by: **Elisheva El-Gad**  
**Z23723068**

## Table of Contents

1. [Overview](#overview)
2. [App Features](#app-features)
3. [Product Spec](#product-spec)
4. [Screen Archetypes](#screen-archetypes)
5. [Navigation](#navigation)
6. [Wireframes](#wireframes)
7. [Backend Integration](#backend-integration)
8. [External-api](#external-api)
9. [Schema](#schema)
10. [Milestone 6 Requirements Checklist](#milestone-6-requirements-checklist)

---

## Overview

DailyJokes is a mobile app that provides users with a new joke every day sourced from an external API. Users must log in or sign up using Parse. Logged-in users can view the daily joke, save jokes to their favorites, and revisit them anytime. Favorites are stored and persisted using Parse (Back4App).

---

## App Features

- Login and signup using Parse  
- Fetch and display the daily joke via an external API  
- Favorite jokes and save them to Parse  
- View previously saved favorite jokes  
- Splash screen with student name and Z-number  
- Joke details screen  
- Optional: Share jokes

---

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**
- User can sign up for a new account  
- User can log in to an existing account  
- User can view the daily joke from the API  
- User can mark jokes as favorites  
- User can browse previously favorited jokes  
- User sees a Splash Intro screen with Student Name and Z#  

**Optional Nice-to-have Stories**
- User can share jokes via social apps  
- User can receive notifications for the daily joke  

---

## Screen Archetypes

- **Splash Screen**
  - Displays app title, student name, and Z-number  

- **Login/Signup Screen**
  - User can sign up or log in via Parse  

- **Home Screen**
  - Displays the joke of the day from the API  
  - Users can favorite or share the joke  

- **Favorites Screen**
  - Displays a list of jokes favorited by the user  

- **Joke Details Screen**
  - Shows the full joke  
  - Options to share or favorite/unfavorite  

---

## Navigation

### Tab Navigation
- Home  
- Favorites  

### Flow Navigation
- Splash Screen  
  - Leads to Login/Signup  
- Login/Signup Screen  
  - Leads to Home Screen after successful login  
- Home Screen  
  - Optionally shares joke  
  - Leads to Favorites Screen  
  - Leads to Joke Details Screen  
- Favorites Screen  
  - Leads to Joke Details Screen  

---

## Wireframes

![Wireframes](https://i.imgur.com/cyviZ6S.gif)

---

## Backend Integration

DailyJokes uses Parse (Back4App) for:

- User authentication  
- Persisting favorite jokes  
- Retrieving previously saved data  

Each favorited joke includes:

| Field   | Type    | Description                 |
|---------|---------|-----------------------------|
| user    | Pointer | The logged-in user          |
| jokeId  | String  | API joke ID                 |
| text    | String  | The joke text               |

---

## External API

DailyJokes retrieves its daily joke from a public joke API.

**Endpoint:**  
`GET /dailyjoke` – returns a new joke of the day

Returns:  
- id  
- text  

---

## Schema

### Models

**User**
| Property  | Type   | Description                                   |
|-----------|--------|-----------------------------------------------|
| objectId  | String | Unique identifier for the user                |
| username  | String | User login name                               |
| email     | String | User email                                    |
| password  | String | Encrypted password handled by Parse           |

**Joke (Favorite Joke Object in Parse)**
| Property | Type    | Description                                  |
|----------|---------|----------------------------------------------|
| objectId | String  | Unique identifier for the favorite entry     |
| user     | Pointer | Associated Parse user                        |
| jokeId   | String  | Unique identifier for the joke               |
| text     | String  | The joke text                                |

### Networking
- `POST /users/signup` – create a new user account  
- `POST /users/login` – log in existing user  
- `GET /dailyjoke` – retrieve the daily joke from the external API  
- `GET /favorites` – get user's saved jokes  
- `POST /favorites` – add a joke to favorites  

---

## Milestone 6 Requirements Checklist

### Required Functions
- Login/signup with Parse  
- Use external API for daily joke  
- Use Parse backend for persistence  

### 4 Required Non-Login Screens
- Splash Screen  
- Home Screen  
- Favorites Screen  
- Joke Details Screen  

### Additional Requirements
- README included  
- Demo video presentation  

### Extra Credit (Optional)
- Map and Location  
- Camera  
- TestFlight Deployment  

---
