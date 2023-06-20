---
title: "Stripe"
description: ""
lead: ""
date: 2021-04-05T08:48:57+00:00
lastmod: 2021-04-05T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Setup"
weight: 108
toc: true
---

#### User App

###### Here are the steps to integrate Stripe and allow payment with credit cards.


1. Create [Stripe Account](https://dashboard.stripe.com/register).
2. Add your business details to activate your account.
3. Go to `Developers → API` Keys and get your `publishable key` and paste it in `constants.dart` file.
![image alt text](images/Stripe.JPG)

###### Free plan setup
1. Sign up for a Cloudflare account. [Cloudflare workers](https://workers.cloudflare.com/)
2. Access the Cloudflare Workers dashboard
3. Click on the "Create a Worker" button to start creating a new serverless function. Give your Worker a name.
4. Open `create-payment.js` and search for variable named `stripeSecretKey` and put your stripe secret key there.
5. Select and copy the entire code from the "create-payment.js" file and then  Paste the code into the serverless function on Cloudflare.
6. Save and deploy the Worker
7. Copy the URL of the serverless function and paste it in `constants.dart` file.
![image alt text](images/Stripe.JPG)

