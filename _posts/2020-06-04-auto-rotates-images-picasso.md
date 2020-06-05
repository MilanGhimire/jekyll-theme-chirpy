---
title: Auto Rotates Images Picasso
author: Milan Ghimire
date: 2020-06-04 19:34:00 +05:45
categories: [Kotlin]
tags: [glide, picasso]
---

Today I found one problem in Picasso. Which is if the EXIF data is greater than 3264 x 2448 is found the picasso automatically rotates the Image 90 degree anticlockwise.

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

#### Links I found useful

[GitHub issue report](https://github.com/square/picasso/issues/846)

[Stackoverflow](https://stackoverflow.com/questions/42411409/why-image-auto-rotate-when-set-to-imageview-with-picasso)


