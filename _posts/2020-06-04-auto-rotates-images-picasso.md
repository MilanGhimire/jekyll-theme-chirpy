---
title: Auto Rotates Images Picasso
author: Milan Ghimire
date: 2020-06-04 19:34:00 +05:45
categories: [Kotlin]
tags: [glide, picasso]
---

Today I found one problem in Picasso. Which is if the EXIF greater than 0000 X 0000 is found the picasso automatically rotates the Image 90 degree anticlockwise.

So I used the library named Glide by bumptech.

### Dependiency of Glide

```kotlin
implementation "com.github.bumptech.glide:glide:4.11.0"
annotationProcessor "com.github.bumptech.glide:compiler:4.11.0"
```

### How to use Glide

To use glide first we need to add the dependencies to the app level `gradle`.

```gradle
Glide.with(context).load(pathToUri).into(yourView)
```