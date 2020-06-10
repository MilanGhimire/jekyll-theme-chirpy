---
title: Loading data to spinner with item click listner
author: Milan Ghimire
date: 2020-06-09 23:44:44 +05:45
categories: [Kotlin]
tags: [untaged]
---


So to load data to the spinner there are 2 ways.

#### Static data loading
First add the data to `.xml` file. Into `string.xml` or `array.xml` or anyname you want. 
I prefer to use `array.xml`. Inside it create `string-array` and add items to it. 

```xml
<string-array name="gender_list">
      <item>male</item>
      <item>female</item>
      <item>other</item>
</string-array>
```

Then in `Spinner` in layout/spinner_test.xml

```xml
<Spinner
      android:id="@+id/spinnerGender"
      android:layout_width="120dp"
      android:layout_height="wrap_content"
      android:entries="@array/gender_list"
/>
```
Thats it.

#### Dynamic data loading

```java
customeList = listOf("male", "female", "other")
val dataAdapter =
      ArrayAdapter<String>(context, R.layout.simple_spinner_item, customeList)
genderSpinner.adapter = dataAdapter
```


#### Adding Onclick Listner to Spinner

```java
spinnerMunicipality.onItemSelectedListener = object : AdapterView.OnItemSelectedListener {
      override fun onNothingSelected(adapterView: AdapterView<*>?) {
            // no thing to do yet
      }

      override fun onItemSelected(
            adapterView: AdapterView<*>?,
            view: View?,
            position: Int,
            id: Long
      ) {
            Log.d(TAG, "You selected ${adapterView?.getItemAtPosition(position).toString()}")
      }
}
```
