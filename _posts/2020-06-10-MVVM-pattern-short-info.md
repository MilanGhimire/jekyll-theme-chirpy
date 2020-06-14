---
title: MVVM Pattern overview with Room DB
author: Milan Ghimire
date: 2020-06-10 21:10:15 +05:45
categories: [php laravel]
tags: [untaged]
---


Steps to create a MVVM pattern using DB of ShoppingItem list:

1. Create class Entity ShoppingItem (Has every attirbutes)
2. Create interface Dao for ShoppingItem(Has the functions like upsert, delete, getall, get...)
3. Create abstract class ShoppingDatabase (Has the database creating code)
4. Create class ShoppingRepository(ShoppingDatabase) (Implements the Dao interface)
5. Create class ShoppingViewModel(ShoppingRepository) (Uses the repository methods)
6. Create class ShoppingViewModelFactory(ShoppingRepository) (Uses the ShoppingViewModel)
7. Create ShoppingApplication: Application(), KodeinAware() (Used for creating DB, Repository and finally ViewModel instance)
8. Use ViewModel created in ShoppingApplication in ShoppingActivity