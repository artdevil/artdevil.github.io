---
layout: post
title: 'Extending web app to api mobile app'
date: '2023-09-24 13:25:00 0000'
categories: ['api', 'ruby on rails']
---

Since android OS and iOS releases, mobile development has taken a position in user experiences. After continuing the old monolith rails project and the founder having new funding, sometimes requirements get involved to make a mobile app for users.

As a full-stack web developer, you need to choose the best way to implement it. Luckily today there are several options :

1. Wrapping the mobile app with web view or using PWA
2. Create mobile app using hybrid mode eg [react native](https://reactnative.dev/) and [strada](https://strada.hotwired.dev/)
3. Create cross platform mobile app eg [flutter](https://flutter.dev/)
4. Create app using native language example android using [kotlin](https://developer.android.com/kotlin) or [java](https://developer.android.com/studio/write/java8-support?hl=id) and iOS using [swift](https://www.apple.com/id/swift/) or [objective-C](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/Introduction/Introduction.html).

So which one is suit for extending your web app to a mobile app? There are a few steps that may help you to decide.

### 1. Asking for a mobile app designer (UI / UX)
Mobile phones are really small screens, so there is not much space for turning ideas into it. Need to decide which features from the web app are going to the mobile app.

Hired mobile app designer (UI / UX) is the best way, you can't improve so much using templates to reposition all your features so better to know what the goal visualization of features is.

Also, UI can help you to decide more details like how big the image is, what size of the font, and also what font type to make it better.

### 2. Check features in design
The ability for screening features is important in this step. Take a look at the design, it asks asking permission like Bluetooth access or Wi-Fi access? how about the camera and location ? checking phone addresses are sensitive in mobile app.

if the mobile app design only needs location or camera without feeling so native. may consider using PWA or wrapping webview. Since our web full-stack developers skills are enough in here. 

In the modern web framework, there are features to detect whether the request comes from a desktop or phone. You can do [server-side rendering](https://stackoverflow.com/questions/1284169/mobile-version-of-views-for-ruby-on-rails) to show different templates based on request. example in rails :

<script src="https://gist.github.com/stereoscott/4609375.js"></script>

How if the client wants to feel native? well, we can use react native or Strada for this. But understand limitations like animation and graph showing may you consider using Flutter for that case, the big plus is all options are cross-platform!

If It needs access Bluetooth or Wi-Fi access example for an IoT project you may consider using a native language like Kotlin and Swift. But wait, I see some of Flutter libraries have a function to access. I can say yes but limitations like accessing the BLE signal may need to tweak the Java library (and you don't want it, believe me !), Also consider versioning of the mobile OS app may give you a headache.

### 3. Client budgets
[The number 1 reason](https://www.investopedia.com/articles/personal-finance/040915/how-many-startups-fail-and-why.asp#:~:text=Key%20Takeaways&text=According%20to%20business%20owners,%20reasons,the%20work,%20and%20not%20quitting.) why startups fail is budget. I really feel sorry if one of my clients gets into this situation when I am still on board.

If native feeling is not a priority may consider using PWA or wrapping webview, as it is easy to set and can quickly launch and free your mind about the mobile OS version since it actually runs your browser on a mobile phone, and the affects client budgets are safe and may you get bonus :D

Turning a web app into a mobile app to feel native is mostly burning money. You need to hire a mobile developer and causing of the mobile OS version, you need to consider updating it or supporting the old version. It takes time to debug your app to run smoothly in every version or at least your setting minimal versioning.

And you as a full-stack web developer need to provide API. Building API takes almost the same time as building a new app since you need to provide API documentation so mobile developers understand how it works. Rarely does a good developer write good API documentation so maybe you can consider using Swagger or openAPI to help you format it.

Time for debugging also improving since we only send our response to the mobile app and the mobile app also has its own way how to parse the data. As a good fullstack developer you need to consider writing unit test code for API response to be less drama.