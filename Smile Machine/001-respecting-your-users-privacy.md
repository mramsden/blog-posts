# Respecting Your Users Privacy

Going through my usual morning routine casting my eye over Hacker News with the first coffee of the day I saw the headline "[The antisocial network: Path texts my entire phonebook at 6am](http://www.branded3.com/blogs/the-antisocial-network-path-texts-my-entire-phonebook-at-6am/)".

This isn’t the first time that Path has been in the news playing fast-and-loose with user data, in February they were fined $800,000 by the FTC when "[it deceived consumers and improperly collected personal information](http://www.ftc.gov/opa/2013/02/path.shtm)".

Coupling the recent news about Path with stories of concern about Facebook and Google making changes to their privacy policies, it all serves as a stark reminder of the importance of privacy to the user.

This set me off thinking about the importance of respecting user privacy in the apps we create and what we ask the end user to allow us to do on their phone.

As an Android user this is all thrown into sharp focus as there are a number of apps which make requests for distinctly dubious permissions. Why to play [Zynga Poker](https://play.google.com/store/apps/details?id=com.zynga.livepoker) do I need to give them access to my phone book, my call log, and who I am calling? From my reading of the description of the app there is no mention of why they might need to access my phone contacts. It may well be that the permission is requested purely on technical grounds to allow certain functionality within the app, but this should be explained in a clear and upfront manner. Games are particularly guilty of asking for superflous permissions on Play and there have been a number of malware apps that have made their way onto the store and resulted in costing user money and their personal details being stolen.

To me it seems critical that we are up-front and honest with users about how we might use their data to make their lives better.

## It's all about app permissions

At the moment both iOS and Android have differing approaches to app permissions.

### iOS

iOS requests user permissions on the fly on behalf of an app whenever it wants to use sensitive information, specifically it requests permissions when an app wants to;

* Access the user's location
* Access user data including calendars, reminders, contacts and photos

Apple does not disclose what permissions the app requires to run to a user in the App Store, instead the user is only made aware of a permission being required when the user first uses a feature that attempts to use a device facility listed above. Reviewers at Apple will look at your usage of these features and test cases of the user denying permission. It’s important that you factor in the app degrading gracefully in the event of the user denying permission to an app.

The approach that Apple has taken reduces the thought burden on the user. If I just press the find me arrow on an app, I would not be entirely surprised to see a dialog informing me that an app wishes to use my location for the first time.

### Android

Android takes an alternative approach to permissions. Beyond simple execution of an app, if you want to achieve anything else you have to declare these requested permissions within your app. The permissions range from the relatively fundamental, accessing the internet and writing to disk, to the more extreme, such as initiating a phone call for the user.

Google Play scans your app to see what permissions are requested and declares these to the user before they download the app. By downloading an app this is understood as being an approval of all requested permissions and the device will not ask the user any furthur questions about access to these features. The issue with these permissions is some of them can be very unclear to the end user;

> **FULL NETWORK ACCESS**<br>
> Allows the app to create network sockets and use custom network protocols. The browser and other applications provide means to send data to the internet, so this permission is not required to send data to the internet.

Talking to the consumer about network sockets and protocols? I hope they were paying attention during their IT classes at school.

## How can we improve things?

When I work with clients I like to try to remind them of the following principles when it comes to using their potential users’ data.

### Inform users when you are going to use their sensitive data

When you are about to perform a critical operation with the user’s data consider popping up a dialog. iOS already does this for us when requesting certain pieces of data. On the other hand on Android we already received the user’s permission up front, but the user may have paid little notice to the list of permissions the app is approved for when installing your app. Remember that you will need to be a good citizen and respect the user’s wishes if they say no.

Be careful with using too many dialogs at the risk of this happening though;

<iframe src="http://www.youtube.com/embed/FxOIebkmrqs" height="315" width="420" allowfullscreen="" frameborder="0"></iframe>

### Give the user an opportunity to opt out and degrade gracefully when they do

More often then not when designing apps for iOS it is all to easy to forget the situation when the user refuses permission to access the data. Indeed this becomes an issue on Android as well if we are sticking by the dialogs we are showing to the user. For example, you request permission to access the user’s location but they say no, can you still offer the user a basic level of functionality without that data. If you are unable to provide the feature consider a message you might swap the feature’s interface out for explaining to the user why you need their location to function.

### Provide information outside of the app

Whilst Android is overly permissive when it comes to running apps, Google did get it right by declaring permissions up front to the user on the Play store and informing the user before they hit the download button. But I think that the messages are far too generic and risk confusing the user. Apple on the other hand lists nothing in the App Store. Since neither provide a place to clearly state your privacy message consider adding a privacy page to your support site clearly setting out how you use the data that you are requesting access to. Do you hold it for a significant duration off of the device? Whilst you may not be sharing it publically, will it be used to help shape other user’s experiences with your app?

Provide a simple page which lays out how the user’s location, contacts and events will be used. Keep it something short and sweet though just as a quick overview of your broader privacy agreement with the user. Try to keep it non-technical as well, always refer to functions of the device that the user is likely to recognise and explain which of your features the permission facilitates.

## Think about privacy from day one

If you think about these privacy issues from the start it can really help you to form a clear picture of your app. Just by thinking through the user data required by your app you can start to think through the various situations. You can also start to think of how it would affect the smoothe running of your app if the user refuses permission rather than receiving a bug report following your first release.

Concerns about privacy are not going to go away and as technical professionals we have a duty to help the user to make an informed decision about their data. By showing the user that you are committed to their privacy throughout everything you do is a great way of building trust in both your app and your brand.
