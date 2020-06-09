---
title: Things to know for your interview of Kotlin
author: Milan Ghimire
date: 2020-06-05 20:32:05 +05:45
categories: [Kotlin]
tags: []
---


The below code is for the Internet checking. Note: From Android M there is new way to check android permission.

```java
private fun hasInternetConnection(): Boolean {
      val connectivityManager = getApplication<CovidApplication>().getSystemService(
      Context.CONNECTIVITY_SERVICE
      ) as ConnectivityManager
      if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.M) {
      val activeNetwork = connectivityManager.activeNetwork ?: return false
      val capabilities = connectivityManager.getNetworkCapabilities(activeNetwork) ?: return false
            return when {
                  capabilities.hasTransport(TRANSPORT_WIFI) -> true
                  capabilities.hasTransport(TRANSPORT_CELLULAR) -> true
                  capabilities.hasTransport(TRANSPORT_ETHERNET) -> true
                  else -> false
            }
      } else {
            connectivityManager.activeNetworkInfo?.run {
                  return when(type) {
                        TYPE_WIFI -> true
                        TYPE_MOBILE -> true
                        TYPE_ETHERNET -> true
                        else -> false
                  }
            }
      }
      return false
}
```