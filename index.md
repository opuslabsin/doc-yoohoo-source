---
title: "Yoohoo Documentation"
keywords: 
sidebar: 
hide_sidebar: true
search: false
permalink: index.html
summary: These instructions will help you in setup server and mobile application.
---

{% include note.html content="Video guide for getting Debug SHA1 fingerprint is available, checkout [https://www.youtube.com/watch?v=OQl6Me2_gEA](https://www.youtube.com/watch?v=OQl6Me2_gEA)" %}

# Introduction
Yoohoo is real-time complete chatting app with groups and voice messages functionality. The user can send pictures, audio, video, contact detail, map location, voice messages, a user can create groups as well.

# Setup

1. ### Android
      ***Note: Phone Authentication or some other functionality will not work on emulator. Kindly use real physical device for testing.** 

      Before continuing make sure you have :-
      - **Firebase Account** [https://console.firebase.google.com](https://console.firebase.google.com)
      - **Firebase's Realtime Database is enabled.**  Use following security rule or use **Start in test mode**:
          ```
          {   
            "rules": {
              // only authenticated users can read or write to my Firebase
              ".read": "auth !== null",
              ".write": "auth !== null"   
            }
          }
          ```
      - **Firebase's Storage is enabled**
      - **Phone Auth is enabled in Sign-in method in Firebase's Authentication section**
      - **Sinch Account** [https://www.sinch.com/](https://www.sinch.com/)
      - **Enabled `Places SDK for Android` in [https://console.cloud.google.com](https://console.cloud.google.com)**
      - **SHA-1 fingerprint of your machine** [https://cloud.google.com/solutions/mobile/mobile-firebase-app-engine-flexible#generating_a_sha-1_fingerprint_for_the_app](https://cloud.google.com/solutions/mobile/mobile-firebase-app-engine-flexible#generating_a_sha-1_fingerprint_for_the_app)

      After following the steps given below make sure you have values of all the following keys with you:
      - **applicationId**
      - **app_name**
      - **support_email**
      - **geo_api_key** - Follow [https://developers.google.com/places/android-sdk/signup#api-console](https://developers.google.com/places/android-sdk/signup#api-console)
      - **admob_app_id**
      - **admob_banner_id**
      - **sinch_app_key**
      - **sinch_app_secret**
      - **sinch_app_environment** - set this to `clientapi.sinch.com` for production app

      You will need to update above values in `app/build.gradle`

      **`Refactoring`**
      - Change the `applicationId` in `app/build.gradle`, set this to the package name you want to keep for your application e.g com.yoohoo
      - Use the same package name while setting up android app in Firebase in the next step.
      - Logo and placeholders used in app are png images which you will find in `app/src/main/res/drawable` folder.
      - To change the images in app simply replace the images at above mentioned location with your images.

      **`Firebase Setup`**
      - Create a Firebase account or log into an existing account.

      - Click **Add project**. Follow the remaining setup steps and click **Create project**.
      <p align="center"><img src="{{ "images/8.1-firebase-create-project.png" }}"/></p>

      - After the wizard provisions your project, click Continue.

      - In the Overview page of your project, click the Settings gear and then click Project settings.

      - Click Add Firebase to your Android app and follow the wizard
      <p align="center"><img src="{{ "images/8.3-firebase-add-android-app.png" }}"/></p>

      - In Debug signing certificate SHA-1, enter the SHA-1 value you generated in the previous section.

      - Click Register app.

      - Download the google-services.json file and place it in `app` folder.
      <p align="center"><img src="{{ "images/8.4-firebase-download-config-json.png" }}"/></p>

      - Click Next in the Download config file section and follow the rest of the steps if required.

      - Next click on **Authentication** and click on **Sign-in method**
      <p align="center"><img src="{{ "images/8.5-firebase-sign-in-method.png" }}"/></p>

      - Enable **Phone Authentication**

      **`Theming`**
      - You can control the color used in app from `app/build.gradle` itself.
      - We provide scope for customization of following values:

            resValue 'color', "colorPrimary", "#2196F3"
            resValue 'color', "colorPrimaryDark", "#1976D2"
            resValue 'color', "colorAccent", "#1A237E"

      **`Useful links`**
      - SHA-1 key related
        - [https://cloud.google.com/solutions/mobile/mobile-firebase-app-engine-flexible#generating_a_sha-1_fingerprint_for_the_app](https://cloud.google.com/solutions/mobile/mobile-firebase-app-engine-flexible#generating_a_sha-1_fingerprint_for_the_app)
        - [https://developers.google.com/android/guides/client-auth](https://developers.google.com/android/guides/client-auth)
        - [https://medium.com/pen-bold-kiln-press/sha-1-android-studio-ec02fb893e72](https://medium.com/pen-bold-kiln-press/sha-1-android-studio-ec02fb893e72)

**Note: If you are unable to understand any topic or find any topic needs more elaboration. 
Please raise an issue ticket at this link [https://opuslabs.freshdesk.com](https://opuslabs.freshdesk.com)**
