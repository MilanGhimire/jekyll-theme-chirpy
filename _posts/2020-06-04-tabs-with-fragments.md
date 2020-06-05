---
title: Tabs with fragments
author: Milan GHimire
date: 2020-06-04 20:45:50 +05:45
categories: [Kotlin]
tags: [fragment]
---


### Creating Tabs
Steps:
1. Create .XML file for each Fragments
2. Create Class and inherit Fragment(). Inside that class inflate the .XML file to each Fragments
3. Now, you need to create an Adapter and pass FragmentManager as parameter and Inherit `FragmentStateManager(supportFragmentManager)` Inside @override getItem(), getCount() and getPageTitle and create a function as e.g. 

```kotlin
fun addFragment(fragment: Fragment, title: String) {
      mFragmentList.add(fragment)
      mFragmentTitleList.add(title)
}
```
Note: you need to declare following items first

```kotlin
private val mFragmentList = ArrayList<Fragment>()
private val mFragmentTitleList = ArrayList<String>()
```
4. Then create a .XML file for the Parent(Root) Activity which contains the Fragments. Here you need AppBarLayout, inside it use Toolbar(not compulsary) and TabLayout(for tab heading). Then use Viewpager in same layer as Appbar for the which swipes. 
5. Then use in Activity create adapter instance that we created. And add Fragments that we created to the adaper. Then setup the Tab. As below code.

```kotlin
val adapter = ViewPagerAdapter(supportFragmentManager)
adapter.addFragment(AllStoryExFragment(), "All Stories")
      adapter.addFragment(MyStoryExFragment(), "My Stories")
      viewPager.adapter = adapter
      tabs.setupWithViewPager(viewPager)
```
