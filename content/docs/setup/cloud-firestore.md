---
title: "Cloud Firestore"
description: ""
lead: ""
date: 2021-04-05T08:48:57+00:00
lastmod: 2021-04-05T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Setup"
weight: 105
toc: true
---
Every database needs rules to give limited permissions to users and full
control to the admin. So, we will add rules to Firestore.

### Rules

1. First, log in to your Firebase console and select your project.
2. Navigate to the "Authentication" section from the left-hand menu.
3. enable email and password authentication and google authentication from the sign-in method tab.
3. Click on the "Users" tab and then click on the "Add User" button at the top of the page.
4. add a user (it will be your admin user) and copy his uid.
5. Go to Firebase → Cloud Firestore → Rules and paste these rules:

**Important**: Replace ADMIN_UID with your admin UID.

    rules_version = '2';
    ervice cloud.firestore {
    match /databases/{database}/documents {

    // TODO: Put your admin UID
      function adminUid() {
      return "Put-Admin-Uid-Here";
    }
    
    // allow read,write to admin
      match /{document=**} {
      allow read, write: if request.auth.uid == adminUid();
    }
    
     // Restaurants collection
    // Allow read only to normal users
    match /restaurants/{restaurantId} {
      allow read: if request.auth != null;
    }

    //for collection group
    match /{path=**}/products/{productId} {
    allow read,write: if request.auth != null;

    }
    
    // users collection
    // allow users to read and write their own data
    match /users/{userId}{
  	allow read, write: if userId==request.auth.uid;
		}
    
    // allow users to read and write their orders
    match /users/{userId}/orders/{ordersId}{
  	allow read, write: if userId==request.auth.uid;
		}
    
    
    
    // allow users to read and write their own favorites
    match /users/{userId}/favorites/{favoriteId}{
  	allow read, write: if userId==request.auth.uid;
		}
    
    }} 


### Indexes

1. Open the Firebase console and select your project.
2. Click on the "Firestore Database" from the left-hand side menu.
3. Select the "Indexes" tab from the top menu.
4. Click on the "Single Field Indexes" dropdown and select "Add Index".
5. In the "Collection ID" field, enter "orders" (without quotes).
6. In the "Field Path" field, enter "id" (without quotes).
7. In the "Collection Group Scope" dropdown, select "Arrays","Ascending", "Descending".
8. Click on the "Create" button to add the index.
9. Repeat steps 4-8, but in step 5, enter "orders" and in step 6, enter "time".
10. Repeat steps 4-8, but in step 5, enter "products" and in step 6, enter "stars".
