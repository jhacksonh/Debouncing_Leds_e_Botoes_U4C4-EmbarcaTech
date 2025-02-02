# **Documentação do Projeto - Debolcing_Leds_e_Botoes_U4C4-EmbarcaTech**

## **Objetivo**
Este projeto visa criar um sistema de exibição de números utilizando uma matriz de LEDs WS2812, controlada por um Raspberry Pi Pico. O sistema permite a exibição de números de 0 a 9, com controle via botões para incrementar e decrementar os valores exibidos, enquanto um LED RGB pisca 5 vezes por segundo. O projeto também implementa debouncing para garantir a precisão na leitura dos botões.

## **Link de Demonstração**
- **Vídeo Demonstrativo**: [Clique Aqui Para Ver](https://youtu.be/Mgh2OSupwrk)

## **Objetivos do Projeto**
- Aprender a utilizar interrupções em microcontroladores.
- Implementar debouncing de botões via software.
- Controlar LEDs WS2812.
- Usar resistores de pull-up internos em botões.
- Desenvolver um sistema completo integrando hardware e software.

## **Componentes Utilizados**
- **Raspberry Pi Pico**
- **Matriz de LEDs WS2812 5x5** (controlada pela GPIO 7)
- **LED RGB** (conectado às GPIOs 11, 12 e 13)
- **Botão A** (conectado à GPIO 5)
- **Botão B** (conectado à GPIO 6)

## **Funcionalidades Implementadas**
1. **LED RGB Piscante**: O LED vermelho do LED RGB pisca 5 vezes por segundo, indicando que o sistema está funcionando.
2. **Controle de Números**: 
   - O **botão A** incrementa o número exibido na matriz de LEDs.
   - O **botão B** decrementa o número exibido.
3. **Exibição de Números**: A matriz WS2812 exibe números de 0 a 9 em formato digital fixo.
4. **Debouncing de Botões**: Implementação de debouncing por software para evitar leituras incorretas dos botões.

## **Configuração do Hardware**
O projeto utiliza os seguintes pinos do Raspberry Pi Pico:
- **LEDs Individuais**:
  - **PIN_LED_R** (GPIO 13) - LED vermelho.
- **Botões**:
  - **PIN_BUTTON_A** (GPIO 5) - Botão para incrementar o número.
  - **PIN_BUTTON_B** (GPIO 6) - Botão para decrementar o número.
- **Matriz de LEDs WS2812**:
  - **PIN_LEDS** (GPIO 7) - Controle dos LEDs endereçáveis.

## **Estrutura do Projeto**
O código-fonte está organizado da seguinte maneira:

```
DEBOUNCING LEDS E BOTOES U4...
│── includes/
│   ├── draws/
│   │   ├── numbers0_9.h
│   ├── utils/
│   │   ├── leds.h
│── pios/
│   ├── ws2812.pio
│── src/
│   ├── draws/
│   │   ├── numbers0_9.c
│   ├── utils/
│   │   ├── leds.c
│── tarefa/
│   ├── 10.37M2 - U4C4O12T - Tarefa WLS.pdf
│── .gitignore
│── CMakeLists.txt
│── diagram.json
│── main.c
│── pico_sdk_import.cmake
│── README.md
│── wokwi-project.txt
│── wokwi.toml
```

### **Descrição dos Diretórios e Arquivos**
- **`includes/`**: Arquivos de cabeçalho com definições de funções e interfaces.
  - **`draws/`**: Arquivo `numbers0_9.h` define os padrões de exibição dos números.
  - **`utils/`**: Arquivo `leds.h` define funções para controle dos LEDs.
- **`pios/`**: Arquivos de controle do hardware via PIO.
  - **`ws2812.pio`**: Configuração do PIO para controle dos LEDs WS2812.
- **`src/`**: Arquivos de código-fonte com a implementação das funcionalidades.
  - **`draws/`**: Implementação da exibição dos números (`numbers0_9.c`).
  - **`utils/`**: Implementação do controle dos LEDs (`leds.c`).
- **`tarefa/`**: Contém a tarefa proposta em formato PDF.
- **Arquivos de configuração**:
  - **`.gitignore`**: Define quais arquivos não serão incluídos no versionamento.
  - **`CMakeLists.txt`**: Configuração do CMake para gerenciamento da compilação.
  - **`diagram.json`**: Arquivo de configuração para a simulação no Wokwi.
  - **`main.c`**: Código principal que inicializa os componentes e gerencia o sistema.
  - **`pico_sdk_import.cmake`**: Importação do SDK do Raspberry Pi Pico.
  - **`README.md`**: Documentação do projeto.
  - **`wokwi-project.txt`** e **`wokwi.toml`**: Arquivos de configuração para integração com Wokwi.

## **Como Rodar o Projeto no VSCode**
1. Clone o repositório:
   ```sh
   git clone https://github.com/jhacksonh/Debouncing_Leds_e_Botoes_U4C4-EmbarcaTech.git
   ```
2. Configure o VSCode para trabalhar com o Raspberry Pi Pico.
3. Compile e execute o código no ambiente simulado (Wokwi) ou na placa física.

## **Simulação no Wokwi**
O projeto já está configurado para simulação no **Wokwi**. Após clonar o repositório e configurar o VSCode, você pode compilar e executar a simulação diretamente usando o arquivo **diagram.json**.

**Nota**: Certifique-se de ter a extensão Wokwi instalada no VSCode.

## **Conclusão**
Este projeto mostra como integrar hardware e software para criar um sistema funcional de exibição numérica com LEDs WS2812 controlados por um Raspberry Pi Pico. A implementação de interrupções e debouncing assegura o controle preciso dos botões. A estrutura modular facilita a manutenção e expansão do projeto.