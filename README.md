# DailyJokes

## Table of Contents

1. [Overview](#overview)
2. [Product Spec](#product-spec)
3. [Wireframes](#wireframes)
4. [Schema](#schema)

---

## Overview

### Description
DailyJokes provides users with a new joke every day, sourced from an external API. Users must log in or sign up to use the app. Once logged in, they can view the daily joke, mark jokes as favorites, and optionally share jokes with friends.

### App Evaluation
- **Category:** Entertainment / Social Networking  
- **Mobile:** Mobile is essential for daily notifications, login, and quick access to jokes.  
- **Story:** Users get a fun daily joke while managing their own favorites. Login ensures personalized experience and persistence across devices.  
- **Market:** Anyone who enjoys humor and short-form content. Monetization could be through ads or premium features (e.g., more joke categories).  
- **Habit:** Users check the app daily for the joke of the day and interact with favorites.  
- **Scope:** Simple MVP: login/signup, view daily jokes, mark favorites. Sharing is optional.  

---

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**
- User can sign up for a new account.  
- User can log in to an existing account.  
- User can view the daily joke from the API.  
- User can mark jokes as favorites.  
- User can browse previously favorited jokes.  

**Optional Nice-to-have Stories**
- User can share jokes via social apps.  
- User can receive notifications for the daily joke.  

---

### 2. Screen Archetypes

- [ ] **Splash Screen**
  * Displays app title, student name, and Z-number  
- [ ] **Login/Signup Screen**  
  * Required: User can log in or create a new account.  
- [ ] **Home Screen**  
  * Required: User can view the joke of the day.  
- [ ] **Favorites Screen**  
  * Required: User can view and manage favorite jokes.  
- [ ] **Share Option**  
  * Optional: User can share a joke.  

---

### 3. Navigation

**Tab Navigation**
- [ ] Home  
- [ ] Favorites  

**Flow Navigation**
- [ ] Splash Sreen
  * Leads to Login/Signup
- [ ] Login/Signup Screen  
  * Leads to Home Screen after successful login  
- [ ] Home Screen  
  * Optionally shares joke via share sheet
  * Leads to Joke Details Screen  
  * Leads to Favorites Screen  
- [ ] Favorites Screen
  * Leads to Joke Details Screen 

---

## Wireframes

![Video Walkthrough](https://i.imgur.com/cyviZ6S.gif) 

### [BONUS] Digital Wireframes & Mockups
[Optional: Include links or images to Figma/Sketch mockups]  

### [BONUS] Interactive Prototype
[Optional: Include prototype links if created]  

---

## Schema

### Models

**User**
| Property | Type   | Description                                  |
|----------|--------|----------------------------------------------|
| id       | String | Unique identifier for the user               |
| username | String | User login name                               |
| email    | String | User email for account login                 |
| password | String | User password (stored securely via Back4App)|

**Joke**
| Property | Type   | Description                                  |
|----------|--------|----------------------------------------------|
| id       | String | Unique identifier for the joke (from API)   |
| text     | String | The joke text                                |
| favorites| Bool   | Whether the user marked this joke as favorite |

### Networking
- `[POST] /users/signup` - Create a new user account via Back4App  
- `[POST] /users/login` - Log in existing user via Back4App  
- `[GET] /dailyjoke` - Retrieve the daily joke from the API  
- `[GET] /favorites` - Retrieve user's favorite jokes (Back4App or local storage)  
- `[POST] /favorites` - Mark a joke as favorite  

