# Google Developers Challenge Scholarship

(notas de https://github.com/wookupmaker/GDCS Thanks!)

##### Table of Contents  
[Stage 1](#stage1)  
[Stage 2](#stage2)  


<a name="stage1"/>

## Stage 1 [06-11-2017]

*So why not just set the minSDK to 1 and support everyone? Generally, you’ll want to target as many users as you can, but there's a cost associated with supporting older versions - things like creating different execution paths around deprecated or updated APIs, or presenting a different UX to devices with different features. You need to balance the opportunity of expanding your audience, with the cost of supporting those users.*

**Also remember that each release introduced new APIs and hardware support, so it may not make sense to make your app available to devices that don’t support your minimum feature set. Here are some examples of hardware support and features, tied to releases.**

1. Home screen widgets (Cupcake)
2. Multiple finger tracking (Froyo)
3. Tablet (Honeycomb)
4. Android Beam (Jellybean)
5. Android TV, Auto, Wear (Lollipop)
6. Pro Audio (Marshmallow)

**Setting targetSDK**
*By comparison, the targetSDK is NOT a high pass filter -- it’s used only to declare which platform version you've tested your app on. An app targeted to a certain API or Android version will continue to be forward compatible on future releases -- the platform uses the target SDK values in case a future release makes a significant change to expected behavior, ensuring your app doesn’t break when a user’s phone gets upgraded.  
Android Studio by-default targets the latest release. If you’re developing a new app, there’s really no reason to target anything but the latest Android version, and once your app has been released, make it a point to update your target SDK and test as soon as possible when new platform releases roll out, so your app can take advantage of every new platform optimization and improvement.**

>Your app runs within its own instance of the run time using the classes and services provided here in the application framework. 

**The first thing that happens when you hit RUN is your code gets compiled into byte code that can be run in the run time on the device. In Android Studio is done using Gradle, a build tool kit manages dependencies and allows you to define custom build logic. For now, not that we start with your project, whic Gradle builds and then packages the byte code along with your applications resources, externalized images, UI, XML, into an Android Application Package file. An APK whic is especially formatted ZIP file. Once you got a APK ready to go Android Studio signs it through JAR Signer and then pushes it to the device using the Androdi Debug Bridge or ADB

>On Windows and Mac, the x86 emulator relies on a special kernel driver called HAXM for hardware virtualization

>A gradle task represents a single, atomic piece of work for a build. To see a list of tasks, you can open the tasks window in Android Studio by clicking on the gradle button on the far right. Clicking on the name of the task runs that task.

*Run gradle build task from the command line*
`./gradlew tasks`

*For example, to start your android app from the command line, you could type:*

`adb shell am start -n com.package.name/com.package.name.ActivityName`

**What is an Android Application**
*A collection of components that work with each other, and with the Android Framework. There are four types of components that make up apps*
1. Activity
2. Services
3. Broadcast Receiver
4. Content Providers

*Android knows about each of these components because they are registered in Android Manifest*  
*The Android Manifest is used to register components with the Android framework.*

**Activity**  
*Single focused thing that the user can do.*  
*Activities are responsible for creating the window that your application uses to draw and receive events from the system such as touch event from the system*

**Type of Views in Android**  
1. UI Components
  1. TextView
  2. EditText
  3. ImageView
  4. Button
  5. Chronometer

2. Container View
  1. LinearLayout
  2. RelativeLayout
  3. Framework
  4. ScrollView
  5. ConstraintLayout

**A word about id**
`@+id/tv_toy_names`
*The @ sign tells the tools not to treat the stuff inside the quotes as a string literal. And to instead, look for the contents inside of the Android resources. While the plus sign tells the tool to create the id if it doesn't yet exist. The id preceding the slash, lets the tools know that we're creating an id rather than a reference to something like a style, string or image drawable*

*Well the R class is autogenerated by the Android tool chain. But because Java doesn't allow for slashes in variable names the tools replace the slash after the id with a period*

#### Stage 1 Completed!

<a name="stage2"/>

## Stage 2 [7-11-2017]

**Message logging display levels**  
1. Error
2. Warn
3. INFO
4. Debug
5. Verbose
> In term of increasing verboseness in severity
>Error, Warn and Info level messages are always preserved in release versions
> During development you can also use DEBUG and VERBOSE log messages

**Android has another very special logging level that is more severe than ERROR**  
*It is called WTF for What a Terrible Failure. The WTF level is for errors that should never, ever, ever happen and most developers should never ever, ever use it. On a debug build of a device, a WTF error may force the device to halt and output a debug report. Because the behaviour of WTF isn't clearly defined, it might be best to only use the knowledge of this sepecial log level to impress your friends ;)*

>R is a static class that is generated by aapt (Android Asset Packing Tool) for us to reference resources in Java Code

*We also allow applications to specify menu items as actions. If there's enough horizontal space, those actions appear on the action bar as buttons. To do this in our menu XML, we add the show as action attribute. We're doing this in the app namespace because we're using AppCompat to make our app compatible with API Level 10 Gingerbread devices.*

**Toast**  
*Provides simple feedback about an operation in a small popup*

>use the showAsAction XML attribute. You can actually add a button to the Toolbar layout, but that's making a custom toolbar rather than making a menu item show up as a button.

*We can take advantage of the Android URI framework class. It allows us to create a well-formed URI without having to worry about the particular of URI components. For example, adding ampersands between query parameters and encoding invalid character with a percent followed by the character code*

**UTF-8**  
*Is used by JSON and JavaScript*  
**UTF-16**  
*Is the format used by android*

>While declaring a permission is required for using the camera, directly dialing the phone, and directly accessing the contact database - you can do each of these things by using a system app as an intermediator. Because the camera app, dialer, and contacts app will be used to provide the data you request - users have the chance to cancel the action you initiated, giving them runtime ability to refuse your app access.

**Your app can only access the user’s location if it explicitly declares a uses-permission.**


>NetworkOnMainThreadException only occur if your app is running in device over Gingerbread version of android if the version is Gingerbread or lower it would work fine but its a bad practice to do network stuff on Main Thread

*To run at an ideal 60 frames per second We need to make sure that all the computations between draws takes  less than 17 milliseconds*  

>After five second of ignoring user input, Android would actually prompt the user to close your app. 

**AsyncTask**  
*Allows you to run a task on a background thread, while publishing results to the UI thread*  

>AsyncTask is a generic class. Meaning it takes parameterized types in its constructor. Each one of these generic parameters is to find as a Java variable argument with the three dots, which means that it is technically passed as an array in Java world.

**The three types used by an AsyncTask are the following**  
1. Params -> Parameter type sent to the task upon execution
2. Progress -> Type published to update progress dueing the background computation
3. Result -> The type of the result of the background computation

**There is a list of menthods and which runs on UI thread of background thread, got it varun!!!**  
1. execute() -> UI thread
2. onPreExecute() -> UI thread
3. doInBackground() -> Background thread
5. publishProgress() -> Background thread (called from inside the doInBackground())
6. onProgressUpdate() -> UI thread
7. onPostExecute() -> UI thread

**JSON**  
*Primary method for data exchange on the web because it's format is syntactically identical to the code for creating JavaScript objects, this means that JavaScript programs can use standard JavaScript functions to read JSON data since it's essentially native JavaScript*

**Why JSON**  
1. Human readable
2. More compact
3. Easier to write
4. Allows for declaration of arrays 

