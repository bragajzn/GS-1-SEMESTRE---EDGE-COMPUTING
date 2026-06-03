# Monitor de Sinais Vitais com Arduino Uno

## Descrição do Projeto

Este projeto consiste no desenvolvimento de um sistema embarcado utilizando Arduino Uno para monitoramento de parâmetros simulados de sinais vitais e proximidade. O sistema é capaz de exibir a temperatura corporal, a frequência cardíaca e a distância de um objeto em tempo real por meio de um display LCD.

Além disso, o projeto conta com um botão para ligar e desligar o sistema e um LED indicador de funcionamento. Os valores de temperatura e frequência cardíaca são simulados através de potenciômetros na plataforma Wokwi, enquanto a distância é medida por um sensor ultrassônico HC-SR04.

---

## Objetivo da Solução

O objetivo deste projeto é desenvolver um protótipo de monitoramento de sinais vitais utilizando conceitos de eletrônica embarcada e programação em Arduino para demonstrar como será o monitoramento no traje espacial OverSpace.

A solução busca:

* Simular a leitura de temperatura corporal.
* Simular a leitura de frequência cardíaca.
* Medir a distância de um objeto utilizando sensor ultrassônico.
* Exibir as informações em um display LCD.
* Permitir que o usuário ligue e desligue o sistema por meio de um botão.
* Indicar visualmente o estado de funcionamento do sistema através de um LED.

---

## Componentes Utilizados

| Componente                          | Quantidade          |
| ----------------------------------- | ------------------- |
| Arduino Uno                         | 1                   |
| Display LCD 20x4 (I2C)              | 1                   |
| Sensor Ultrassônico HC-SR04         | 1                   |
| Potenciômetro (Temperatura)         | 1                   |
| Potenciômetro (Frequência Cardíaca) | 1                   |
| Botão Push Button                   | 1                   |
| LED Verde                           | 1                   |
| Resistores                          | 1                   |
| Protoboard                          | 1                   |
| Jumpers                             | Diversos            |

---

## Explicação do Funcionamento

O sistema inicia desligado, exibindo a mensagem "Sistema OFF" no display LCD.

Ao pressionar o botão:

1. O sistema é ativado.
2. O LED indicador é aceso.
3. O Arduino realiza a leitura dos sensores.

### Temperatura Corporal

A temperatura é simulada por um potenciômetro conectado à entrada analógica A0.

Os valores são convertidos para uma faixa entre:

* 35,0 °C
* 42,0 °C

### Frequência Cardíaca

A frequência cardíaca é simulada por um potenciômetro conectado à entrada analógica A1.

Os valores são convertidos para uma faixa entre:

* 60 BPM
* 180 BPM

### Distância

A distância é medida pelo sensor ultrassônico HC-SR04.

O sensor emite um pulso ultrassônico e mede o tempo necessário para que o sinal retorne após atingir um objeto. Com base nesse tempo, o Arduino calcula a distância em centímetros.

### Display LCD

O display LCD apresenta:

* Temperatura corporal simulada.
* Frequência cardíaca simulada.
* Distância medida pelo sensor ultrassônico.

### Botão Liga/Desliga

O botão conectado ao pino digital D2 permite alternar o estado do sistema entre ligado e desligado.

### LED Indicador

O LED conectado ao pino D7 permanece:

* Aceso quando o sistema está ligado.
* Apagado quando o sistema está desligado.

---

## Estrutura do Circuito

### LCD I2C

| LCD | Arduino |
| --- | ------- |
| VCC | 5V      |
| GND | GND     |
| SDA | A4      |
| SCL | A5      |

### Potenciômetro de Temperatura

| Potenciômetro    | Arduino  |
| ---------------- | -------- |
| Terminal Central | A0       |
| Laterais         | 5V e GND |

### Potenciômetro de Frequência Cardíaca

| Potenciômetro    | Arduino  |
| ---------------- | -------- |
| Terminal Central | A1       |
| Laterais         | 5V e GND |

### Sensor HC-SR04

| HC-SR04 | Arduino |
| ------- | ------- |
| VCC     | 5V      |
| GND     | GND     |
| TRIG    | D9      |
| ECHO    | D10     |

### Botão

| Botão      | Arduino |
| ---------- | ------- |
| Terminal 1 | D2      |
| Terminal 2 | GND     |

Configuração utilizada:

```cpp
pinMode(buttonPin, INPUT_PULLUP);
```

### LED

| LED    | Arduino                   |
| ------ | ------------------------- |
| Anodo  | D7                        |
| Catodo | GND (através de resistor) |

---

## Instruções de Execução

### 1. Abrir o Projeto

Abra o projeto na plataforma Wokwi ou carregue o código na IDE do Arduino.

### 2. Montar o Circuito

Realize as conexões conforme descritas na seção "Estrutura do Circuito".

### 3. Iniciar a Simulação

Clique no botão **Start Simulation**.

### 4. Ligar o Sistema

Pressione o botão para ativar o monitor.

### 5. Simular Leituras

* Ajuste o potenciômetro da temperatura para alterar a temperatura corporal simulada.
* Ajuste o potenciômetro da frequência cardíaca para alterar os BPM simulados.
* Modifique a distância do sensor HC-SR04 através da interface do Wokwi.

### 6. Visualizar os Dados

Os valores serão exibidos em tempo real no display LCD.

---

## Tecnologias Utilizadas

* Arduino Uno
* Linguagem C++
* Wokwi Simulator
* Biblioteca Wire
* Biblioteca LiquidCrystal_I2C

---

## Resultados Esperados

Ao executar o projeto, o usuário deverá ser capaz de:

* Ligar e desligar o sistema.
* Visualizar a temperatura simulada.
* Visualizar a frequência cardíaca simulada.
* Visualizar a distância medida pelo sensor ultrassônico.
* Observar o LED indicando o estado de funcionamento do sistema.

---

## Integrantes do Grupo

Preencher com os nomes completos dos integrantes:

1. Fabrício Zanzarine de Oliveira Leme RM: 57263
2. Messias Macedo de Souza             RM: 573247
3. João Pedro da Cruz                  RM: 571827
4. Kaue Herculano Guimaraes de Barros  RM: 570699
5. Lucca Schemid Braga                 RM: 571044

---

## Licença

Projeto desenvolvido para fins acadêmicos e educacionais.
