1. What type of encryption algorithms does your app implement? (This Issue come in testflight)
just add this line in info.plist
```
<key>ITSAppUsesNonExemptEncryption</key><false/>
```

2. to use firebase push notification
```
In your info.plist:

 FirebaseAppDelegateProxyEnabled: false

Replace this to your AppDelegate code:
import UIKit
import Flutter
import FirebaseCore
import FirebaseMessaging

@UIApplicationMain
@objc class AppDelegate: FlutterAppDelegate {
  override func application(
    _ application: UIApplication,
    didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
  ) -> Bool {
      FirebaseApp.configure()
    GeneratedPluginRegistrant.register(with: self)
    return super.application(application, didFinishLaunchingWithOptions: launchOptions)
  }

  override func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {

   Messaging.messaging().apnsToken = deviceToken
   super.application(application, didRegisterForRemoteNotificationsWithDeviceToken: deviceToken)
 }
}

```
3. If you get this error [no such module 'firebasecore' ]
 ref:-https://i.stack.imgur.com/HOF5t.png
```
Goto xcode general->scroll down->In fremwork, libraries and Embeded content-> Add FirebaseCore.fremwork  select (Do Not Embeded)
```



4. For Push notification ios [Do not forgot to take permission]
```

  await FirebaseMessaging.instance.requestPermission();
  // getting device token for device targeted notification
  await FirebaseMessaging.instance.getToken().then((token) {
    
    Constants.deviceToken = token.toString(); //store device token to constants
    debugPrint("-======"+token.toString()+"=========");
  });
```

5. Space in iOS app name is not showing
   ```
   For iOS 11 you can open the info.plist as source code and use &#x2007; instead of spaces
   ref:- https://stackoverflow.com/questions/35495888/space-in-ios-app-name-is-not-showing
   ```
