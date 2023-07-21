1. What type of encryption algorithms does your app implement? (This Issue come in testflight)
just add this line in info.plist
```
<key>ITSAppUsesNonExemptEncryption</key><false/>
```

2. to use firebase pish notification
```
In your info.plist:

 FirebaseAppDelegateProxyEnabled: false
Add this to your AppDelegate:

import FirebaseMessaging


override func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {

   Messaging.messaging().apnsToken = deviceToken
   super.application(application, didRegisterForRemoteNotificationsWithDeviceToken: deviceToken)
 }
```
