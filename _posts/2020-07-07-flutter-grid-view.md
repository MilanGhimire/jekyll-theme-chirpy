---
title: Flutter - Flutter Equivalent of Match parent and Wrap Content
author: Milan Ghimire
date: 2020-07-07 23:09:19 +05:45
categories: [Flutter]
tags: [untaged]
---


So to create Grid view in flutter its easy.

I would like to go for code directly. Just like picture speaks it self.

```java
GridView.count(
  // Create a grid with 2 columns. If you change the scrollDirection to
  // horizontal, this produces 2 rows.
  crossAxisCount: 2,
  // Generate 100 widgets that display their index in the List.
  children: List.generate(100, (index) {
    return Center(
      child: Text(
        'Item $index',
        style: Theme.of(context).textTheme.headline5,
      ),
    );
  }),
);
```

So I copied this code from documentaiton. Here `crossAxisCount: 2` is the total items per row is 2.
We also can specify the our items like:

```java
GridView.count(
  crossAxisCount: 3,
  children: ListView(
        ...........
        // keep your widgets here
  ),
);
```

Thats it.

References:

(Documentation)[https://flutter.dev/docs/cookbook/lists/grid-lists]
