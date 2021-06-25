# NetPractice

## Цель данного проекта научиться  настривать межсетевые подключения между компьютерами

<details>
<summary>Level_1</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl1_1.png" alt="Ссылка"></p>
________________________________________________________________
  
 ### Здесь нам нужно настроить компьютеры, в рамках одной домашней сети.
  
 ### Изначально подключение не работает, так как компьютер имеет

  ```
  Interface B1
  IP : 104.39.23.12
  Mask : 255.255.255.0
  ```
  ### Из этого следует что 
  
  ```
  Network:  104.39.23.0
  Diaposon: 104.39.23.1 - 104.39.23.254
  ```
  
  ### А у Компьютера А1  ```104.93.23.17 ``` Что не входит в данный диапозон. 
  
  ###  Поэтому меняем IP у A1 на подходящий из диапозона и вуаля... Анологично со вторым компьютером
  
 
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl1_2.png" alt="Ссылка"></p>

</details>

<details>
<summary>Level_2</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl2_1.png" alt="Ссылка"></p>
________________________________________________________________

 ### Очень похоже на первое задание, только здесь чтобы компьютеры могли коммуницировать между собой, они должны быть в рамках одной сети. 
 ### Чтобы понять какая сеть, возьмем маску от А1  и IP от B1 и подсчитаем какая сеть 
  ```
  IP : 192.168.20.222
  Mask : 255.255.255.224
  ```
### Получается 
  ```
  Network:  192.168.20.192
  Diaposon: 192.168.20.193 - 192.168.20.222
  ```
### Чтобы все заработало берем любой IP из диапозона и ставим в A1, а также  меняем маску у B1 на аналогучную A1  
  
#
  
### Компьютеры С1 и D1 не могут скомуницироваться так как диапозон ```127.0.0.1 - 127.255.255.254``` используется для коммуникации с самим собой (Addresses on Loopback)
  
### Для решения этой проблемы просто берем другое адресное пространство   
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl2_2.png" alt="Ссылка"></p>
  
</details>



<details>
<summary>Level_3</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl3_1.png" alt="Ссылка"></p>
________________________________________________________________

### Здесь у нас появляется новый обьект. Сетевой коммутатор (жарг. свитч, свич от англ. switch — переключатель) — устройство, предназначенное для соединения нескольких узлов компьютерной сети в пределах одного или нескольких сегментов сети.
### Очень важно коммутатор работает в рамках одной сети  
  
### Аналогично предыдущим заданиям берем маску от C1 и  IP от  A1 и строим подходящую сеть

  ### Получается 
  ```
  Network:  104.198.133.0
  Diaposon: 104.198.133.1 - 104.198.133.126
  ```
### Далее просто заполняем любым IP из диапозона и  не забываем про маски:) 

 ________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl3_2.png" alt="Ссылка"></p>
________________________________________________________________
  
</details>

<details>
<summary>Level_4</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl4_1.png" alt="Ссылка"></p>
________________________________________________________________

 ### Здесь добавляется новый обьект Маршрутизатор 
 https://hobbyits.com/naznachenie-i-funkcii-marshrutizatora-v-lokalnoj-seti/
  
   
 ### В данном задании нам нужно Соеденить двух клиентов между собой и также каждый клиент с роутером, для нас доступны 3 интрфейса подключения к роутеру
 
 ### Чтобы все зараюотало, нам нужнл чтобы Оба клиента и интерфейс роутера были все в рамках одной сети (мы берем пустой интрфейс и подбираем ему подходящий  IP и маску, такую чтобы она включала клиента A1)
  
  ________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl4_3.png" alt="Ссылка"></p>
________________________________________________________________

  
</details>

<details>
<summary>Level_5</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl5_1.png" alt="Ссылка"></p>
________________________________________________________________

#### Здесь у нас появилась новая графа, давайте разберемся что это
   
  ```
      client A: Machine A
      Routes :
      ... => ...
   ```
#### Эта штука называется статическим маршрутом
#### Статический маршрут используется, когда компьютер хочет связаться с кем-то вне своей сети.
Если пункт назначения соответствует левой части (0.0.0.0/0 в этом примере, что является "по умолчанию", что означает, что он соответствует всему), он попросит правую часть (192.168.0.254 здесь) переслать сообщение  
  
#### Вот пример как это работает
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl5_1.png" alt="Ссылка"></p>  
  
</details>



