---
layout: post
title: Android para a PS - Parte 4
description: Trocando imagens entre si
date: 2019-06-06 21:53:00
---

Este caso é muito parecido com a [manipulação de imagens](https://yuribreion1.github.io/blog/android/android-aula2-manipulando-img/) que já fizemos, porem com um pouco de lógica no meio para fazer a gente pensar mais:

> O objetivo é trocar as imagens entre si uma vez que você clique no botão

Para isto vamos modelar a tela com as duas imagens, um quadrado e um triangulo e um botão, adiantando um pouco nosso trabalho, ela vai ficar da seguinte forma:

``` xml
<LinearLayout android:layout_width="match_parent" android:layout_height="match_parent" android:orientation="vertical" android:background="@color/colorPrimary"
    xmlns:android="http://schemas.android.com/apk/res/android">
    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/title"
        android:textColor="#FFF"
        android:textSize="25sp"
        android:textStyle="bold"
        android:textAlignment="center"
        android:layout_marginTop="20sp"
        />

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/image_1"
        android:layout_marginTop="15sp"
        android:textColor="#FFF"
        android:textAlignment="center"
        android:textSize="20sp"/>

    <ImageView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@drawable/quadrado"
        android:id="@+id/img1"
        android:layout_marginTop="20sp"
        android:layout_gravity="center_horizontal"
        android:background="#FFF"/>

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/image_2"
        android:layout_marginTop="15sp"
        android:textColor="#FFF"
        android:textAlignment="center"
        android:textSize="20sp"/>

    <ImageView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@drawable/triangulo"
        android:id="@+id/img2"
        android:layout_marginTop="20sp"
        android:layout_gravity="center_horizontal"
        android:background="#FFF"/>

    <Button
        android:layout_width="200sp"
        android:layout_height="wrap_content"
        android:layout_marginTop="20sp"
        android:text="@string/button_title"
        android:layout_gravity="center_horizontal"
        android:onClick="trocar"/>
</LinearLayout>
```

Com a tela montada, podemos colocar a nossa lógica no método `trocar`:

Inicializamos variáveis para as ImageView's e suas atribuições de id:

``` java
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        img1 = findViewById(R.id.img1);
        img2 = findViewById(R.id.img2);
    }
```

Criamos uma variavel chamada `cont` que vai funcionar como um contador, que vai nos auxiliar a fazer o caminho de ida e volta das imagens, logo o método trocar vai ficar da seguinte forma:

``` java
    public void trocar(View view) {

        // Logica faz com que a troca sempre volte a seu primeiro estado onde cont é = 0
        if (cont == 0) {
            img1.setImageResource(R.drawable.quadrado);
            img2.setImageResource(R.drawable.triangulo);
            cont++;
        } else {
            img1.setImageResource(R.drawable.triangulo);
            img2.setImageResource(R.drawable.quadrado);
            cont = 0;
        }
    }
```

Segue como ficou nosso aplicativo:

![ydRPi.gif](https://a.imge.to/2019/06/07/ydRPi.gif)

Se quiser, você pode conferir o código no meu [git](https://github.com/yuribreion1/Desafio4)