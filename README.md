# Arduino_PWM_Controller
### Introdução ao PWM (Pulse Width Modulation)
   PWM, ou Modulação por Largura de Pulso, é uma técnica utilizada para controlar a quantidade de energia fornecida a um dispositivo eletrônico. Através da variação da largura dos pulsos em uma sequência de sinais de controle, é possível ajustar a potência média enviada ao dispositivo, sem alterar a frequência do sinal.
   
  No exemplo de aplicação utilizado abaixo foram usados os seguintes componentes:
  
  ## Arduino Nano: 
  O Arduino Nano é uma pequena, completa e amigável placa de desenvolvimento   microcontrolada   baseada no ATmega328. Desenvolvido pela plataforma Arduino, o Nano é ideal para projetos que exigem um microcontrolador potente em um espaço compacto.
  
  ## CELL: 
  O processador CELL, também conhecido como Cell Broadband Engine Architecture (CBEA), é um microprocessador desenvolvido em conjunto pela Sony, Toshiba e IBM (STI). Lançado em 2005, o CELL foi projetado para fornecer alto desempenho em aplicações de computação intensiva, como gráficos, jogos e processamento multimídia.
  
  ## L293D: 
  O L293D é um driver de ponte H, amplamente utilizado em projetos de eletrônica para controlar motores DC e motores de passo. Este circuito integrado permite que microcontroladores e outras fontes de controle de baixa potência dirijam motores de maior potência de maneira eficiente e segura.
  
  ## Motor:
  Motores DC (corrente contínua) e motores de passo são comumente utilizados em projetos de eletrônica e robótica. Quando combinados com controladores como o Arduino Nano e drivers como o L293D, eles permitem a construção de sistemas de movimento precisos e eficientes.

  ![image](https://github.com/GabrielCardoso18/Arduino_PWM_Controller/assets/126261772/37df7d04-ae7e-4dc5-87f0-050c0c82d77d)

## Código Utilizado:
'''C++
#include <Arduino.h>
const int button = 4;

int buttonState = LOW;
int lastButtonState = LOW;
int qtdeClick = 0;
void setup() {
  pinMode(button, INPUT_PULLUP);
}
void loop() {
  buttonState = digitalRead(button);
  if(lastButtonState == LOW && buttonState == HIGH){
    qtdeClick++;
    if(qtdeClick == 0) {
      analogWrite(9, 255);
    } else if (qtdeClick == 1) {
      analogWrite(9, 191);
    } else if (qtdeClick == 2) {
      analogWrite(9, 127);
    } else if(qtdeClick == 3) {
      analogWrite(9, 64);
    } else if(qtdeClick == 4) {
      analogWrite(9, 0);
    } else if (qtdeClick == 5){
      analogWrite(9, 255);
      qtdeClick = 0;
    }
  }
  lastButtonState = buttonState;
}
'''
  

