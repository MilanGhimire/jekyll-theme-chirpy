---
title: Flutter - Mixed ListView (Advance)
author: Milan Ghimire
date: 2020-07-07 22:17:22 +05:45
categories: [Flutter]
tags: [untaged]
---

This article will be about the `ListView` which not only treats as List of Widgets but also for the purpose of a kind of RecyclerView. If you are familar with Java/Kolin (Android).

Here I will be talking about `ListView.builder()`

The builder`() constructor constructs a repeating list of items. The constructor takes two main parameters: An itemCount for the number of items in the list and an itemBuilder for constructed each list item.

```java
child: ListView.builder(
      itemCount: items.length,
            itemBuilder: (context, index) {
            final item = items[index];
            return Text(item);
      },
),
```

To explore more:
This is the official (documentation)[https://flutter.dev/docs/cookbook/lists/mixed-list] for mixed list

Here is the (medium post)[https://medium.com/flutter-community/flutter-listview-and-scrollphysics-a-detailed-look-7f0912df2754]
