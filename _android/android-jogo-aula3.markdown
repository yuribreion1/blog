---
layout: post
title: Android para a PS - Parte 3
description: Jogando dados
date: 2019-06-06 21:53:00
---

Avançando no Android vamos lidar com um caso um pouco mais complexo, vamos montar um jogo de dados onde dois jogadores disputam para saber quem tira o número maior. 

Seguindo como já temos feito, vamos montar a tela para este caso seguindo a seguinte estrutura: 

- LinearLayout
    - TextView -> **Titulo da pagina**
    - ImageView -> **Imagem do primeiro dado** 
    - TextView -> **Label de jogador 1**
    - ImageView -> **Imagem do segundo dado**
    - TextView -> **Label do jogador 2**
    - Button -> **Onde vamos executar a lógica do jogo**

O código do `activity_main.xml` vai ficar montado da seguinte forma:

``` xml
    <LinearLayout android:layout_width="match_parent" android:layout_height="match_parent" android:orientation="vertical" android:background="@color/colorPrimary"
        xmlns:android="http://schemas.android.com/apk/res/android">

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="@string/title"
            android:textSize="30sp"
            android:textColor="#FFF"
            android:textStyle="bold"
            android:layout_marginTop="20sp"
            android:textAlignment="center"
            />

        <ImageView
            android:layout_width="wrap_content"
            android:layout_marginTop="20sp"
            android:id="@+id/jogador1"
            android:layout_gravity="center_horizontal"
            android:layout_height="wrap_content"
            android:src="@drawable/d1"
            android:background="#FFF"
            />

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="@string/player_1"
            android:textSize="20sp"
            android:layout_marginTop="10sp"
            android:textColor="#FFF"
            android:textStyle="bold"
            android:textAlignment="center"/>

        <ImageView
            android:layout_width="wrap_content"
            android:layout_marginTop="20sp"
            android:id="@+id/jogador2"
            android:layout_gravity="center_horizontal"
            android:layout_height="wrap_content"
            android:src="@drawable/d6"
            android:background="#FFF"
            />

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="@string/player_2"
            android:textSize="20sp"
            android:layout_marginTop="10sp"
            android:textColor="#FFF"
            android:textStyle="bold"
            android:textAlignment="center"/>

        <Button
            android:layout_width="200sp"
            android:layout_height="wrap_content"
            android:layout_gravity="center_horizontal"
            android:text="@string/play"
            android:onClick="jogar"
            android:layout_marginTop="20sp"
            />
    </LinearLayout>
```

Partindo para a lógica do jogo no `**MainActivity.java**`:

Seguimos o que já tinhamos feito antes, como inicializar as variáveis e as atribuindo aos seus id's, que são invocados ao inicar a Activity, porém aqui temos algo a mais que não tinhamos visto antes, estamos usando um _array_ para guardar as imagens de cada uma das faces do dado. Elas serão sorteadas mais a frente.

``` java
    public class MainActivity extends AppCompatActivity {

    ImageView imgJogador1;
    ImageView imgJogador2;

    int[] imagens = {
            R.drawable.d1,
            R.drawable.d2,
            R.drawable.d3,
            R.drawable.d4,
            R.drawable.d5,
            R.drawable.d6
    };

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imgJogador1 = findViewById(R.id.jogador1);
        imgJogador2 = findViewById(R.id.jogador2);
    }
```

Com tudo mapeado, podemos criar nosso método **jogar** para que ele faça o sorteio e atribua as imagens corretas do dado: 

Para trabalhar com manipulação aleatória inicializamos o **Random**: 

``` java
    Random r = new Random();
```

Em seguida, temos que armazenar o valor retornado após a manipulação aleatória de números do Random, deixando da seguinte forma:

``` java
    // Jogador 1
    int a = r.nextInt(imagens.length);
    // Jogadar 2
    int b = r.nextInt(imagens.length);
```

Após feito o sorteio, temos que trocar a imagem do dado correspondente ao número sorteado, vamos usar o `.setImageResource` que usamos no [exercício passado](https://yuribreion1.github.io/blog/android/android-manipulando-img-aula2/):

``` java
// Definindo as imagens para cada jogador
    imgJogador1.setImageResource(imagens[a]);
    imgJogador2.setImageResource(imagens[b]);
```

E como vamos retornar o ganhador? Temos que montar esta lógica, e com o valor sorteado podemos facilmente saber, segue como podemos fazer isto: 

``` java
    if (a > b) {
        Toast.makeText(this, "Jogador 1 venceu", Toast.LENGTH_SHORT).show();
    } else if (b > a){
        Toast.makeText(this, "Jogador 2 venceu", Toast.LENGTH_SHORT).show();
    } else {
        Toast.makeText(this, "Due empate!", Toast.LENGTH_SHORT).show();
    }
```

No fim, o jogo fica desta forma:

![ydhIW.gif](https://a.imge.to/2019/06/07/ydhIW.gif)

Segue meu código no [git](https://github.com/yuribreion1/Desafio3)