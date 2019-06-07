---
layout: post
title: Manipulando strings
description: Palíndromos
date: 2019-06-07 16:04:00
---

Neste caso vamos trabalhar com manipulação de strings, e desta vez vamos tratar uma frase ou palavra para saber se é palíndromo(que são palavras/frases que no sentido inverso)

Basicamente vamos criar uma tela com um campo de entrada e um botão, ficando da seguinte forma:

``` xml
<LinearLayout
    android:layout_width="match_parent" android:layout_height="match_parent"               android:orientation="vertical" android:background="@color/colorPrimary"
    xmlns:android="http://schemas.android.com/apk/res/android">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/title"
        android:textSize="25sp"
        android:textColor="#FFF"
        android:textStyle="bold"
        android:layout_marginTop="10sp"
        android:textAlignment="center"
        />

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Informe a palavra ou frase"
        android:textColor="#FFF"
        android:textAlignment="center"
        android:layout_marginTop="10sp"/>

    <EditText
        android:layout_width="200sp"
        android:layout_height="wrap_content"
        android:background="#FFF"
        android:id="@+id/edtFrase"
        android:layout_marginTop="10sp"
        android:layout_gravity="center_horizontal"/>

    <Button
        android:layout_width="200sp"
        android:layout_height="wrap_content"
        android:layout_marginTop="20sp"
        android:text="@string/button_text"
        android:onClick="verificar"
        android:layout_gravity="center_horizontal"/>

</LinearLayout>
```

Partindo para a lógica a ser feita no `**MainActivity.java**` temos o seguinte:

Atribuimos uma variável para o `EditText` e inicializamos ela ao abrir o aplicativo:

``` java
    EditText edtFrase;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        edtFrase = findViewById(R.id.edtFrase);
    }
```

Para verificar eu criei uma função atrelada ao botão da seguinte forma:

``` java
    public void verificar(View view) {
        // Convertendo para string
        String frase = edtFrase.getText().toString()
                .toLowerCase() // Colocando tudo em caixa baixa
                .replace("[a-zA-Z0-9]", ""); // Permitir que tenha somente letras e números
        String fraseInvertida = new StringBuffer(frase).reverse().toString(); // Invertemos os caracteres
        if (fraseInvertida.equals(frase)) {
            Toast.makeText(this, R.string.e_palindromo, Toast.LENGTH_SHORT).show();
        } else {
            Toast.makeText(this, R.string.nao_palindromo, Toast.LENGTH_SHORT).show();
        }
    }
```

Olha como ficou nosso aplicativo no ar:

![yw2u6.gif](https://a.imge.to/2019/06/08/yw2u6.gif)

Meu código esta no meu [git](https://github.com/yuribreion1/Desafio5)
