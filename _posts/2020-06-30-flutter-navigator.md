---
title: Flutter - Navigation
author: Milan Ghimire
date: 2020-06-30 22:25:48 +05:45
categories: [Flutter]
tags: [untaged]
---

SO its been couple months I have started working with flutter.

Today I learn't about the flutter navigation.

One thing I loved about is Flutter documentation is awesome.

Till now I have find out 3 ways to Navigate to another page.

NOTE: All these uses the Navigator.

1. Routes - First register then implement it.

```java
routes: <String, WidgetBuilder>{
      '/login': (BuildContext context) => LoginScreen(),
      '/register': (BuildContext context) =>
      RegistrationScreen(),
}
```
and in other page implement like from login to register:
```java
Navigator.of(context)
      .pushReplacementNamed("/register");
```
2. Use page as the sub page. Which has back button. Which pushes to the stack.

In this official [Documentation](https://flutter.dev/docs/cookbook/navigation/navigation-basics) its shown clearly.

```java
Navigator.push(
    context,
    MaterialPageRoute(builder: (context) => SecondRoute()),
);
```
This code keeps the "SecondRoute" screen to top of the stack. And Below code pops from the stack.

Then in SecondRoute use:
```java
Navigator.pop(context);
```

3. Use to redirect. Not stack but remove existing and add the another.

I found the (doucumentaion)[https://api.flutter.dev/flutter/widgets/Navigator/pushReplacement.html]

```java
Navigator.pushReplacement(
      context, MaterialPageRoute(builder: (BuildContext context) => MyHomePage()));
```

This replaced the screen in the stack.

Here is the (StackOverflow example)[https://stackoverflow.com/questions/61180040/flutter-listview-on-click-navigate-to-another-screen] (Example 2)[https://stackoverflow.com/questions/50037710/flutter-move-to-a-new-screen-without-back]