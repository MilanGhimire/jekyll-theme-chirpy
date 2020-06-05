---
title: Simple Recyclerview
author: Milan Ghimire
date: 2020-06-04 22:32:50 +05:45
categories: [Kotlin]
tags: [recyclerview]
---

### Simple RecyclerView

There are mainly 4 steps:
1. Add RecyclerView (View) in your Activity/Fragment XML
2. Create the XML file for item of recyclerView will showup
3. Create an RecyclerView Adapter
4. Call that Adapter from your Activity/Fragment

I will show you how we write code step by step.
Here I am giving example of Person name RecyclerView.
Also the example is of Activity.

#### Step 1:
Add RecyclerView widget.

> activity_person.xml

```xml
...
<androidx.recyclerview.widget.RecyclerView
      android:id="@+id/rvPerson"
      android:orientation="vertical"
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      android:focusable="true" />
...
```

#### Step 2:
Create new XML for a item for recyclerview like:

> item_person.xml

```xml
<androidx.constraintlayout.widget.ConstraintLayout 
      xmlns:android="http://schemas.android.com/apk/res/android"
      xmlns:app="http://schemas.android.com/apk/res-auto"
      xmlns:tools="http://schemas.android.com/tools"
      android:layout_width="match_parent"
      android:layout_height="64dp"
      android:clickable="true"
      android:focusable="true">

      <TextView
      android:id="@+id/tvFullName"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:text="@string/app_name"/>
</ConstraintLayout>
```

#### Step 3:
Create a RecyclerView Adapter. Here we need to override `onCreateViewHolder()`, `onBindViewHolder()` and `getItemCount()` functions


> PersonAdapter.kt

```kotlin
class PersonAdapter(
    var context: Context,
    private var data: List<String>,
) : RecyclerView.Adapter<PersonAdapter.PersonViewHolder>() {

      private val inflater: LayoutInflater = LayoutInflater.from(context)

      override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): PersonViewHolder {
            val view = inflater.inflate(R.layout.item_person, parent, false)
            return PersonViewHolder(view)
      }

      override fun onBindViewHolder(holder: PersonViewHolder, position: Int) {
            val personItem: String = data[position]
            tvFullName.text = personItem // textview of item_person.xml
      }

      override fun getItemCount() = data.size

      // Inner class for 
      inner class PersonViewHolder(itemView: View) : RecyclerView.ViewHolder(itemView)
}
```

#### Step 4:

Finally, In the Activity file create instance of PersonAdapter.
NOTE: Here I have created a List. You can get list from Local DB or from API.

> PersonActiviy.kt

```kotlin
val personList = mutableListOf<String>("person1", "person2", "person3")

val adapter = PersonAdapter(this, personList)
rvPerson.adapter = adapter // rvPerson is recyclerview from activity_person.xml
rvPerson.layoutManager = LinearLayoutManager(this)
```

Thats it.