## Fastlane
- Currently, fastlane is officially supported to run on macOS.  

[Fastlane](https://github.com/fastlane/fastlane) automates building and releasing your mobile apps.  It can handle all tedious tasks, like generating screenshots, dealing with code signing, and releasing your application.
    
The Fastlane files are generated under the `fastlane` folder at the root of the project.  When running Fastlane, the outcome depends on the platform:  
 - For iOS, provisioning profiles are checked/updated, the app is built, signed with release keys, uploaded to Testflight, and released to beta testers.
 - For Android, the app is built, signed with release keys, uploaded to Google Play, and released to a beta track. 

### Fastlane Config
#### Appfile
Contains information identifying your app.

#### Fastfile
Fastlane uses a "lane" concept, which is basically a function.  A lane contains logic for building and uploading your app to the app stores.  The generated Fastfile contains two lanes, one for each platform (iOS and Android).

#### Matchfile
Used for [Fastlane Match](https://docs.fastlane.tools/actions/match/), which shares one code signing identity across your development team to simplify your codesigning setup and prevent code signing issues. 


### Running Fastlane
To run the iOS lane: 
```bash
fastlane ios build
```
To run the Android lane:
```bash
fastlane android build
```
 - **Note**: You must upload the first AAB/APK file to Google Play manually before using Fastlane.

For more information on configuration for Fastlane, check the [official Fastlane documentation](https://docs.fastlane.tools/).