---
layout: post
title: Android para a PS - Parte 2
description: Mais um passo dado nos estudos de Android nativo
date: 2019-06-06 21:11:00
---

Neste próximo passo vamos criar um aplicativo que manipula imagens, onde cada botão que é clicado troca a imagem da pessoa.

Como no caso anterior, vamos começar no **`activity_main.xml`**, colocamos uma `ImageView` que vai receber a referencia da imagem:

``` xml
    <ImageView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:src="@drawable/p1"
        android:layout_marginTop="20sp"
        android:id="@+id/imgPessoa"
        />
```

Agora teremos três botões que vão executar cada um o seu método de trocar a foto:

``` xml
    <Button
        android:layout_width="200sp"
        android:layout_height="wrap_content"
        android:layout_marginTop="20sp"
        android:layout_gravity="center_horizontal"
        android:onClick="pessoa01"
        android:text="@string/pessoa_1"/>

    <Button
        android:layout_width="200sp"
        android:layout_height="wrap_content"
        android:layout_marginTop="20sp"
        android:layout_gravity="center_horizontal"
        android:onClick="pessoa02"
        android:text="@string/pessoa_2"/>

    <Button
        android:layout_width="200sp"
        android:layout_height="wrap_content"
        android:layout_marginTop="20sp"
        android:layout_gravity="center_horizontal"
        android:onClick="pessoa03"
        android:text="@string/pessoa_3"/>
```

**Note que cada botão tem o seu método onClick que será usado posteriormente no `MainActivity.java`**

Precisamos adicionar as nossas fotos, elas devem estar na pasta **res/drawable** como mostra abaixo:

![ydQW0.png](https://a.imge.to/2019/06/07/ydQW0.png)

É momento de codificar nossos métodos usados em cada `onClick` no **`MainActivity.java`**

Antes temos que atribuir uma variável a `ImageView`, e logo em sequencia atribui-la ao id na inicialização da Activity(tela):

``` java
    public class MainActivity extends AppCompatActivity {

    ImageView imgPessoa;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imgPessoa = findViewById(R.id.imgPessoa);
    }
```

Em posse do método **setImageResource** vamos definir as imagens de cada um da seguinte forma:

``` java
    public void pessoa01(View view) {
        imgPessoa.setImageResource(R.drawable.p1);
    }

    public void pessoa02(View view) {
        imgPessoa.setImageResource(R.drawable.p2);
    }

    public void pessoa03(View view) {
        imgPessoa.setImageResource(R.drawable.p3);
    }
```

**Pronto**, agora ao clicar em cada botão teremos a imagem sendo trocada, segue uma prévia de como ficou o aplicativo

![ydMLO.gif](https://a.imge.to/2019/06/07/ydMLO.gif)

Segue também o código no meu [git](https://github.com/yuribreion1/Desafio2)
