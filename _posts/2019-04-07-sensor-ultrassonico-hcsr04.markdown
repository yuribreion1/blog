---
layout: post
title:  Sensor Ultrasonico HC-SR04
date:   2019-04-07 19:00:16
description: conhecendo mais sobre sensores
---

<img src="https://uploads.filipeflop.com/2017/07/9SS01-3.jpg" alt="sensor" style="width:500px;"/>

#### **O que é?**
<br>
O HC-SR04 se aplica a classe de _**sensores de distância**_, que no sentido geral visa medir a disância de referencia a um objeto desejado. Isso pode ser usado para controlar posicionamento e evitar falhas de produto. O HC-SR04 se aplica aos _**sensores ultrassonicos**_ que através do pulso ultrassonico, consegue determinar a distância de um elemento dado um tempo determinado. 

Esse  sensor  utiliza  sinais  ultrasônicos  (40  Khz,  acima  da capacidade  de  audição  do  ouvido  humano, que é de 20 Khz). Ele pode medir  distâncias entre 2 cm e 4 m, com precisão de 3mm. Seu ângulo de detecção é de aproximadamente 15 graus.

#### **Funcionamento**
<br>
Tudo começa pela emissão de um pequeno pulso sonoro de alta frequência que se propagará na velocidade do som do meio em questão. Quando este pulso atingir um objeto, um sinal de eco será refletido para  o  sensor. A distância entre o sensor e o objeto pode então ser calculada se soubermos o tempo entre a emissão e a recepção do sinal e a velocidade do som no meio em questão. 

<img src="https://uploads.filipeflop.com/2011/07/HC_SR04_Trigger_Echo.jpg" alt="sensor" style="width:500px;"/>

#### **Onde é usado?**
<br>
O sensor ultrassom é amplamente utilizado em aplicações onde se deseja medir distâncias ou evitar colisões, como na robótica móvel e de reabilitação. Nesse tutorial utilizaremos o sensor ultrassom HC-SR04

O sensor pode  ser  utilizado  como  um  detector  de  objetos  ou  na área  de  robótica  um  componente  que  pode  ser  usado  para  encontrar/evitar  obstáculos  ou corrigir rotas na movimentação do robô.

<img src="http://blog.eletrogate.com/wp-content/uploads/2017/07/20170706_121345-1024x576.jpg" style="width:500px;"> 

Um exemplo do seu uso com a ajuda do sino(_buzzer_) para saber a distância real do objeto: 

<img src="http://blogmasterwalkershop.com.br/wp-content/uploads/2016/10/esquem%C3%A1tico.png" style="width:500px;">

#### **Referencias praticas**
<br/>
<iframe width="600" height="450" src="https://www.youtube.com/embed/HynLoCtUVtU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br/>
<iframe width="600" height="450" src="https://www.youtube.com/embed/I5-gq7J7lM4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br/>
#### **Especificações técnicas:**
<br/>

<object data="https://www.mouser.com/ds/2/813/HCSR04-1022824.pdf" type="application/pdf" width="700px" height="700px">
    <embed src="https://www.mouser.com/ds/2/813/HCSR04-1022824.pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="https://www.mouser.com/ds/2/813/HCSR04-1022824.pdf">Download PDF</a>.</p>
    </embed>
</object>