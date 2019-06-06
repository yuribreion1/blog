---
layout: post
title: Android para a PS - Parte 1
description: Se preparando para a ultima prova do primeiro semestre
date: 2019-06-16 20:29:00
---

Vamos começar com um exemplo de código no Android dado logo no começo do semestre, algo bem basico como fazer uma soma de dois valores:

No arquivo `activity_main.xml` vamos seguir os seguintes passos: 

-   Abrir a tag `linear layout` definindo altura, comprimento e orientação:

``` xml
<LinearLayout android:layout_width="match_parent" android:layout_height="match_parent" android:orientation="vertical"
    android:background="@color/colorPrimary"
    xmlns:android="http://schemas.android.com/apk/res/android">
```