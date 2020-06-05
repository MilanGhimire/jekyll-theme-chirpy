---
title: How to add Toolbar options
author: Milan Ghimire
date: 2020-06-04 22:30:22 +05:45
categories: [Kotlin]
tags: []
---

![Desktop View]({{ "/assets/img/sample/mockup.png" | relative_url }})

To create Toolbar menu:
1. Create Menu in XML file in menu folder `res/menu/your_menu_name.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
      xmlns:app="http://schemas.android.com/apk/res-auto">
    <item
            android:id="@+id/search"
            android:title="@string/search"
            android:icon="@drawable/ic_search"
            app:showAsAction="ifRoom"  <!-- ifRoom means if free space then only showuo -->
    />
    <item
            android:id="@+id/logout"
            android:title="@string/logout"
            android:icon="@android:drawable/ic_secure"
    />
</menu>
```

2. In activity, Override `onCreateOptionMenu()`

```kotlin
override fun onCreateOptionsMenu(menu: Menu?): Boolean {
      menuInflater.inflate(R.menu.your_menu_name, menu)
      return super.onCreateOptionsMenu(menu)
}
```

3. To access Menu press, Override `onOptionItemSelected()`

```kotlin
override fun onOptionsItemSelected(item: MenuItem): Boolean {
      when (item.itemId) {
      R.id.search -> {
            // do your stuff here
      }

      R.id.logout -> {
            // do your stuff here
      }
      return super.onOptionsItemSelected(item)
}
```