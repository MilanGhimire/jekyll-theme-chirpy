---
title: Flutter - Flutter Equivalent of Match parent and Wrap Content
author: Milan Ghimire
date: 2020-07-07 22:41:22 +05:45
categories: [Flutter]
tags: [untaged]
---

So those who have come from the Android. We always use height and weight attribute as `warp_content` and `match_parent` in our .xml file. But sadly in Flutter we cannot use that. So the solution for equivalent of wrap_content and match_parent are as follows:

You can do with little Trick: Suppose you have requirement of : ( Width,Height )

Wrap_content ,Wrap_content :
```java
 //use this as child
 Wrap(
  children: <Widget>[*your_child*])
```

Match_parent,Match_parent:
```java
 //use this as child
Container(
        height: double.infinity,
    width: double.infinity,child:*your_child*)
```

Match_parent,Wrap_content :
```java
 //use this as child
Row(
  mainAxisSize: MainAxisSize.max,
  children: <Widget>[*your_child*],
);

```
Wrap_content ,Match_parent:
```java
 //use this as child
Column(
  mainAxisSize: MainAxisSize.max,
  children: <Widget>[your_child],
);
```

(Source)[https://stackoverflow.com/questions/42257668/the-equivalent-of-wrap-content-and-match-parent-in-flutter]
