---
tags:
  - xamarin
  - cordova
---

This post documents the different technologies investigated for cross-platform mobile development.

# Background

This post documents the findings related to each technology investigated for cross-platform mobile development. As more features are investigated, this post will be updated in consequence.

# Comparison Matrix

|Features|Xamarin|Apache Cordova|Winner|
|---|---|---|---|
|IDE|Visual Studio Community Edition <br/> [Xamarin Platform](https://www.xamarin.com/platform)<br/>Some serious work was made to integrate Xamarin in Visual Studio. Very streamline. |Visual Studio Community Edition <br/> [Tools for Apache Cordova](https://www.visualstudio.com/vs/cordova/)<br/>I found the integration a bit buggy. For instance, I had to delete the generated file and rebuilt the app to avoid errors.|Xamarin|
|Language|XAML and C#<br/>This comes down to preference. I'm a .NET developer so I'm more incline to XAML and C#|HTML and JavaScript<br/> Web developer would find themselves at home.|Tie|
|Pricing|~~1 year trial and 25$ per month~~ <br/> ~~1000$ per year for Visual Studio Integration~~ <br/> Xamarin now provides a free version for students, oss development and small non-enterprise teams.|Free|Tie|
|Shared UI|[Xamarin.Forms](https://www.xamarin.com/forms)<br/>Paid solution available such as Telerik and ComponentOne. Components are translated to native UI element so they work for sure.|HTML Elements <br/> Third party libraries like [Onsen](https://onsen.io/) and [Ionic](http://ionicframework.com/)<br/>This is where HTML really shine. The web is filled with communities providing UI element for free. However, cares must be taken with choosing elements since they may not work with all browsers.|Apache Cordova|
|Shared Business Logic|C# <br/> [Shared Project](https://developer.xamarin.com/guides/cross-platform/application_fundamentals/shared_projects/) <br/> [Portable Class Libraries](https://developer.xamarin.com/guides/cross-platform/application_fundamentals/pcl/introduction_to_portable_class_libraries/)Xamarin's magic make sure the code run on any platforms.|JavaScript<br/>Just like any JavaScript file running on any browser.|Tie|
|Libraries|[Xamarin Components Store](https://components.xamarin.com/) <br/> More might be found on NuGet but you need to make sure it works on the platform of your choice.<br/>Choice is limited.|Since it is classic JavaScript, packages found on [Bower](https://bower.io/) are working so far.<br/>Choice are immense. But often browser dependent.|Apache Cordova|
|Emulation|Visual Studio Emulators<br/>Emulators for Windows and Android worked right off the box.|Visual Studio Emulators<br/>Emulators for Windows worked right off the box. For Android, I haven't been able to make it work.|Xamarin|
|Community|[Dedicated Forums](http://forums.xamarin.com/)<br/>When a question is asked there, you know the answer is in the context of Xamarin.|[StackOverflow](http://stackoverflow.com/questions/tagged/cordova)<br/>Support is trickier. Often posts would refer to vanilla Android development and you would need to 'translate' it to Apache Cordova's context|Xamarin|
|Native Features|Access via [Dependency Service](https://developer.xamarin.com/guides/xamarin-forms/dependency-service/)<br/>Xamarin has done an amazing job wrapping native feature such that creating custom plugins is done in C#.|Access via [Plugins](https://cordova.apache.org/docs/en/latest/guide/hybrid/plugins/)<br/>[Apache Cordova Plugins](https://cordova.apache.org/plugins/)<br/>Creating your own plugins in Cordova is more challenging. It must be done in Java for Android, and JavaScript for Windows Phone 8.|Xamarin|
|UI Styling|[Styling](https://developer.xamarin.com/guides/xamarin-forms/user-interface/styles/) in Xamarin.Forms is similiar to XAML Styling <br/> Xamarin.Forms renders elements using native element. If you want to change the look and feel, you will need [Custom Renderer](https://developer.xamarin.com/guides/xamarin-forms/custom-renderer/)<br/>Since Xamarin translate to native UI, the styling is often correct. Otherwise, customer renderer can help.|Classic CSS Style Sheets<br/>Make sure your CSS is supported equally among all browsers, which could be quite challenging. Remember the days of making sure it works with IE, Netscape, Firefox, Chrome? It's the same thing.|Xamarin|
|Updates|Notice via the system tray|Notice via Visual Studio's notification|Tie|

# Decision Tree

.NET developer should be favouring Xamarin over Apache Cordova whereas JavaScript developer should be doing the opposite. The only time I used Apache Cordova over Xamarin was when a third party provider started to include HTML construct in the response of its web service. Needless to say that it's not a good practice. However, if the amount of HTML is fairly limited, you can still use Xamarin by integrating a WebView component.