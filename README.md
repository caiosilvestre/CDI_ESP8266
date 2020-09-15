<h1 align="center"> CDI_ESP8266 </h1>

###### Esse projeto tem o objetivo de criar um CDI programável utilizando um micro controlador (ESP8266 NODEMCU V3 LOLIN).

  A ideia de iniciar o projeto foi devido a  bobina de pulso da minha moto ter quebrado, as dificuldade de encontrar peças para a mesma, decidir então criar o meu próprio CDI.

   <img src="https://drive.google.com/uc?export=view&id=1uNPNGEr_eZZ1yfOkmCtowzFnZrnbi0g1" width="380"> <img src="https://drive.google.com/uc?export=view&id=14dv0OtyFJAYJr2Z8cLEEWsXQN53cSgDs" width="380">

## V 1.0

### OBJETIVO

- Ler o sinal enviado pela bobina de pulso e tratar o dado.
- Criar um programa capaz de acionar a centelha no ponto morto superior do pistão (PMS).

### DIA 1
- Procurar saber como funciona o CDI e  o modo que ele atua para funcionar o motor.
 <img src="https://drive.google.com/uc?export=view&id=1xrzxdKU5Hh9qFmGJ3sBvr6kDVCEp6kam" width="380">  <img src="https://drive.google.com/uc?export=view&id=1-J0ooS4_DMW8MFDcys4HGXEoFrcj4oPQ" width="380">
- O CDI recebe um sinal positivo da bobina de pulso quando o resalto do magneto passa na frente dela e um sinal negativo quando ele acaba, como podemos observar nas imagens acima.
- Assim o CDI pode calcular o RPM do motor e saber quando é o PMS(Ponto Morto Superior) do motor. O PMS é a onde a centelha deve ocorrer.
- Com todas essas informações desenvolvi um código capaz de imitar o magneto com resalto e utilizei um LM324 para fazer a saida de 5V para 3.3V.
#### PROGRAMA
```c
void setup() {
  pinMode(3,OUTPUT);
  pinMode(4,OUTPUT);
}
void loop() {
    digitalWrite(3,LOW);
    delay(1);
    digitalWrite(3,HIGH);
    delay(1);   // tempo que vai demorar para chegar no final do resalto
    digitalWrite(4,LOW);
    delay(1); 
    digitalWrite(4,HIGH);
delay(17); // tempo que vai dar 1 volta completa 
}
```
Com esse programa imitamos a bobina de pulso da moto.(Utilizei as portas do ESP8266 em PULL UP por isso a lógica invertida) 
### DIA 2
- Criar um código para ler o sinal do magneto e calcular o momento da centelha.
- O dia inteiro tentando implementar códigos, devido a minha falta de afinidade com o ESP8266 tive dificuldades para criar um código que funcione liso sem dar erros. Então parti para o modo bruto, que é entender como cada ferramenta dele funciona e a biblioteca(Ticker).
### DIA 3

### DIA 4
- criar um programa com interface para melhorar a comunicação homem maquina.
- Escolhi o C# com windows form, porem devido as minhas dificuldades com a linguagem meu rendimento cai muito, devo demorar alguns dias para terminar esse programa.

<img src="https://drive.google.com/uc?export=view&id=1Jx_dV1MzsSvxoWCeDKq5cFIpwHBXXvsJ" width="450">  <img src="https://drive.google.com/uc?export=view&id=129ywuzouK2ByC2FRgyxI6IcR32rpWUX6" width="450">
- Escolhi fazer o programa num designer mais clean, por gosto e facilidade.
