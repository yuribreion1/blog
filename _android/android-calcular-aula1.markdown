---
layout: post
title: Android para a PS - Parte 1
description: Se preparando para a ultima prova do primeiro semestre
date: 2019-06-06 20:29:00
---

Vamos começar com um exemplo de código no Android dado logo no começo do semestre, algo bem basico como fazer uma soma de dois valores:

No arquivo `activity_main.xml` vamos seguir os seguintes passos:

- Abrir a tag `linear layout` definindo altura, comprimento e orientação:

``` xml
<LinearLayout android:layout_width="match_parent" android:layout_height="match_parent" android:orientation="vertical"
    android:background="@color/colorPrimary"
    xmlns:android="http://schemas.android.com/apk/res/android">
```

_lá na frente vamos fechar esta tag `linearlayout`_

- Logo em seguida vem um `textview` para usarmos como um título para nosso programa:

``` xml
    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/titulo"
        android:textSize="20sp"
        android:textAlignment="center"
        android:layout_marginTop="10sp"
        android:textColor="#FFF"
        android:textStyle="bold"/>
```

- Agora teremos o seguinte formato: um `textview` e um `edittext` para cada campo a ser digitado em nosso programa, em regra eles serão manipulados para fazer o calculo, então o código vai ficar assim:

``` xml
    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/first_field"
        android:textColor="#FFF"
        android:inputType="number"
        android:layout_marginTop="15sp"
        android:textAlignment="center"/>

    <EditText
        android:layout_width="200sp"
        android:layout_height="wrap_content"
        android:id="@+id/edtNum1"
        android:layout_gravity="center_horizontal"
        android:layout_marginTop="10sp"
        android:background="#FFF"
        />

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/second_field"
        android:textColor="#FFF"
        android:inputType="number"
        android:layout_marginTop="15sp"
        android:textAlignment="center"/>

    <EditText
        android:layout_width="200sp"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal"
        android:id="@+id/edtNum2"
        android:layout_marginTop="10sp"
        android:background="#FFF"
        />
```

É importante notar que colocar um id para cada `edittext` para que estes sejam manipulados mais a frente.

Para fechar, vamos colocar um botão que vai chamar este processo de calcular:

``` xml
    <Button
        android:layout_width="200sp"
        android:layout_height="wrap_content"
        android:layout_marginTop="20sp"
        android:text="@string/calcular"
        android:onClick="somar"
        android:layout_gravity="center_horizontal"/>
```

Segue o código completo da `activity_main.xml`:

``` xml
    <LinearLayout android:layout_width="match_parent" android:layout_height="match_parent" android:orientation="vertical"
    android:background="@color/colorPrimary"
    xmlns:android="http://schemas.android.com/apk/res/android">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/titulo"
        android:textSize="20sp"
        android:textAlignment="center"
        android:layout_marginTop="10sp"
        android:textColor="#FFF"
        android:textStyle="bold"/>

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/first_field"
        android:textColor="#FFF"
        android:inputType="number"
        android:layout_marginTop="15sp"
        android:textAlignment="center"/>

    <EditText
        android:layout_width="200sp"
        android:layout_height="wrap_content"
        android:id="@+id/edtNum1"
        android:layout_gravity="center_horizontal"
        android:layout_marginTop="10sp"
        android:background="#FFF"
        />

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/second_field"
        android:textColor="#FFF"
        android:inputType="number"
        android:layout_marginTop="15sp"
        android:textAlignment="center"/>

    <EditText
        android:layout_width="200sp"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal"
        android:id="@+id/edtNum2"
        android:layout_marginTop="10sp"
        android:background="#FFF"
        />

    <Button
        android:layout_width="200sp"
        android:layout_height="wrap_content"
        android:layout_marginTop="20sp"
        android:text="@string/calcular"
        android:onClick="somar"
        android:layout_gravity="center_horizontal"/>
    </LinearLayout>
```

**Legal** nossa tela já esta montada, agora temos que configurar a lógica disso tudo, e isso precisa ser feito em `MainActivity.java`

No primeiro momento vamos mapear os campos que foram usados como `EditText`:

``` java
    EditText edtNum1;
    EditText edtNum2;
```

Logo em seguida atribuimos estes caras aos id's criados lá no arquivo xml, isto tudo dentro do método `onCreate` para que seja carregado ao iniciar:

``` java
    edtNum1 = findViewById(R.id.edtNum1);
    edtNum2 = findViewById(R.id.edtNum2);
```

No final, vamos criar o método que efetivamente faz a soma ficando da seguinte forma:

``` java
    public void somar(View view) {
        int num1 = Integer.parseInt(edtNum1.getText().toString());
        int num2 = Integer.parseInt(edtNum2.getText().toString());

        int soma = num1 + num2;

        Toast.makeText(this, "A soma é: " + soma, Toast.LENGTH_SHORT).show();
    }
```

**Note que usamos um _Toast_ para lançar um alerta com o resultado da soma após o botão ser clicado**

É importante ressaltar que esta função somente será invocada porque colocamos o método **`onClick`** lá no arquivo xml dentro da tag `Button`

``` xml
    android:onClick="somar"
```

Se liga como ficou o aplicativo no ar:

![ydzdx.gif](https://a.imge.to/2019/06/07/ydzdx.gif)
