# Branch-Monster-Factory-Android
**Branch Monster Factory** is an android app to create your own monster that includes the Branch SDK, creates a Branch link for sharing, and deep links appropriately for both existing users (app is already installed) as well as new users (app downloaded after clicking a link). The link you generate for a monster should open the app to that monster.

## Platform

Android, Java, Android Studio

## Tasks

- [x] Integrate the Branch SDK, following the SDK integration steps outlined here: https://docs.branch.io/pages/apps/android/
- [x] Set up custom event tracking, link creation, and content sharing
      
      - [x] Track that the user visited the monster edit page (call event "monster_edit") on the MonsterCreatorActivity
      - [x] Track that the user visited the monster view page (call event "monster_view") on the MonsterViewerActivity. This time, include state information (specified in `myMonsterObject.monsterMetaData()`)
      - [x] Using an asynchronous method inside `initUI()`, get a shortURL with params, using the static keys provided in `MonsterPreferences` and the values from `myMonsterObject.prepareBranchDict()`. Put that URL into the `monsterUrl` TextView, and be sure to move the `progressBar.setVisibility(View.GONE);` inside the completionhandler
      - [x] Inside `shareMyMonster`, get a short URL with params. Get the params from `myMonsterObject.prepareBranchDict()`, set the channel to be "sms", and make sure that you use an asynchronous method.
      - [x] Only attempt to send the SMS if there is no error in getting the Branch link.

## App Walkthrough

This section is a walkthrough detailing how the app works, what it is doing and how to use it.

**Android App Demo on the real device (Pixel 1) (App installed)**

- [x] Get started by cloning the project to your local machine: https://github.com/akashungarala/Branch-Monster-Factory-Android
- [x] Open the existing project (Folder "Branchster-Android-No-SDK") in the Android Studio (recommended IDE) and run the app on Emulator or on the real device (Pixel 1 in my demo) connected via USB
- [x] You should see the Monster Creator Activity screen where you can type name, choose color index, face index and also body index of your Branchster and click on "DONE" button
- [x] You should see the Monster Viewer Activity screen with your branchster information and also a branch link url to share your branchster
- [x] Click on the share icon, select the option 'Share with Messages' and follow the instructions to share your branchster by sending a message which has the generated branch link url in it.
- [x] Test the branch link received in the message by clicking on it when you have the app already installed, which should take you to the Monster Viewer Activity screen of the app directly with the information of the branchster shared.

![licecap recording - android app demo using pixel 1 app installed](https://user-images.githubusercontent.com/7720015/44677109-fa808180-a9e9-11e8-8204-a310f26441ca.gif)

**Android App Demo on the real device (Pixel 1) (App not installed)**

- [x] Now test the branch link received in the message by clicking on it when you do not have the app already installed, which should take you to the browser and open the dropbox url where the app-debug.apk file is hosted (which is the custom URL mentioned in Android redirects section in Branch dashboard)
- [x] Follow the on-screen instructions and install the apk file from Dropbox and then again click on the branch link received in the message, which should now take you to the Monster Viewer Activity screen of the app directly with the information of the branchster shared.

![licecap recording - android app demo using pixel 1 app not installed](https://user-images.githubusercontent.com/7720015/44677160-1ab04080-a9ea-11e8-930f-0bacc50a05e9.gif)

**Test the branch link in an iPhone**

![branch link with content preview is received via sms in iphone](https://user-images.githubusercontent.com/7720015/44681163-b5ae1800-a9f4-11e8-86e6-4931b94dda08.PNG)

- [x] Now in an iPhone, test the branch link received in the message by clicking on it, which should take you to the browser and open the branch website http://branch.io (which is the Default URL as mentioned in iOS redirects section in Branch dashboard)

![clicking on the branch link in an iphone takes to branch website in safari browser](https://user-images.githubusercontent.com/7720015/44681147-a5963880-a9f4-11e8-85ca-b2c39d1a0a88.PNG)
