====If emuletor is not responding===
delete all *.lock files and start coldboot emuletor
goto /home/sltech/.android/avd/Pixel_3a_API_33_x86_64.avd path
and run sudo rm *.lock

====To implement dynamic link ref to this blog=====
https://blog.devgenius.io/firebase-flutter-dynamic-links-step-by-step-guide-630402ee729b


====to generate gradlew signingReport ===
goto android
```cd android/```
and run 
``` ./gradlew signingReport ```


===tap outside remove keyboard====
```
runApp(GestureDetector(
    onTap: () {
      WidgetsBinding.instance.focusManager.primaryFocus?.unfocus();
    },
    child: const MyApp(),
  ));
```

======UI=======
1.resizeToAvoidBottomInset: false,-(code for scafold resize)
2. Change Status bar color
'''
body: AnnotatedRegion<SystemUiOverlayStyle>(
        value: SystemUiOverlayStyle.light.copyWith(
          statusBarColor: Colors.transparent,
        ),
        child:
'''


======DART=========
1.format double to 2 decimal places:- double.parse((10.99999).toStringAsFixed(2));
2.Dart code analized https://docs.codemagic.io/flutter-testing/static-code-analysis/

3. Remove html tags from string dart
``` import 'package:intl/intl.dart';
Bidi.stripHtmlIfNeeded("<p>Hello World</p>");
```

===Firebase config===
1.To  get Debug signing certificate SHA-1 => go to android folder and un this ./gradlew signingReport 


=====FIREBASE=====
1.for stop recapcha verification in firebase otp auth
    i> install Android Device Verification in your google cloud console(in your project)link-https://console.cloud.google.com/apis/api/androidcheck.googleapis.com/metrics?project=stayhook-b55ee
2.If realtime database gives error "access denied" -> Togo Firebase console click on realtime database then go to rules. Update the rules set everything true.


=======GETX=========
1. use of offNamedUntil
        Get.offNamedUntil(
              Routes.MY_BOOKINGS, ModalRoute.withName(Routes.INDEX));
2. ref: https://dev-yakuza.posstree.com/en/flutter/getx/route/#getoffnameduntil
3. use of Get.until
        Get.until((route) => Get.currentRoute == '/index');


=============FLUTTER SDK============

1.Any type of build error TRY:- 
    flutter clean,
    flutter pub get,
    flutter pub cache repair
==IF NOT SOLVE THEN===
   flutter channel stable
   flutter upgrade --force
   flutter clean
   flutter pub get
   flutter pub run build_runner build
   flutter packages pub run build_runner build --delete-conflicting-outputs

2. Remove OverScroll Glow effect of any scroll view
  try: """ 
  NotificationListener<OverscrollIndicatorNotification>(

        onNotification: (overScroll) {

          overScroll.disallowGlow();

          return;

        },

child: //Your scrolling widget goes here(like ListView)

);
  
  """
  
  3.To run in debug mode (with letsplay-server running locally)

  flutter run --dart-define=DEBUG=TRUE
  
  =====luncher icon old======
    flutter_launcher_icons: ^0.9.2

flutter_icons: 
  android: launcher_icon
  image_path: assets/images/ic_launcher.png
  ios: true



=====CHROME HACK=====
(INSPECT MOBILE WEBSITE IN LAPTOP)
strps->
1. open chrome in laptop and type in url chrome://inspect/#devices
2. connect your mobile to laptop using usb
3. check  Discover network targets option
4. now open any website in your mobile 

======Readymade multivendor app========
``` https://docs.6amtech.com/docs-six-am-mart/mobile-apps/mandatory-setup ```

===Signup with facebook docs====
>package anme = flutter_facebook_auth
```
https://facebook.meedu.app/docs/5.x.x/android
```
