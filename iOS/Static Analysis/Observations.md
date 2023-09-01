
Static Analysis for iOS 
Most iOS Applications are based on Objective C. 
Swift is the latest version of code for iOS 
Applications Applications are in a .iPA format, this is similar to an APK 
• An .ipa is a signed bundle of folders and assets 
• A .ipa contains a /Payload Folder and some important files from a pentester perspective: 
/Payload/Application.app – the application itself 
/Payload/iTunesMetadata.plist - Info about the app developer 
/Payload/Application.app/Info.plist - Where important app info is stored (Similar to Android Manifest.xml)

-----

Rename the IPA file to a zip file and extract contents

Things to looks for:
Info.plist
Firebase urls
API keys
hardcoded credentials, coupon codes
Can identify urls in the json files

------

MobSF has limited capabilities for iOS applications compared to android and it tends to give a higher score to the iOS apps