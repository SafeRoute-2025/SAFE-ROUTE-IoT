# SAFE-ROUTE-IoT

Sistema IoT para monitoramento do nível de água e intensidade da chuva utilizando ESP32 e sensores simulados. Os dados são enviados via MQTT para o Node-RED, que exibe um dashboard em tempo real.

## Descrição

Este projeto faz parte da solução SafeRoute — uma plataforma de alertas inteligentes e evacuação segura. O objetivo da SafeRoute é otimizar a comunicação e organizar rotas seguras de evacuação durante eventos climáticos extremos, como enchentes e tempestades severas.

Para demonstrar um exemplo funcional desse conceito, desenvolvemos um protótipo IoT que simula a medição de níveis de chuva e água, com acionamento de um alerta visual (LED) quando a situação atinge níveis críticos.

O sistema utiliza sensores simulados (potenciômetros no Wokwi) para representar a intensidade da chuva e o nível da água. Esses dados são enviados via protocolo MQTT para um broker e exibidos em tempo real em um dashboard no Node-RED.

A lógica funciona da seguinte forma:

A leitura da chuva é apenas informativa, simulando o aumento potencial do nível da água.

Quando o nível da água ultrapassa 75%, o sistema aciona um LED no simulador e exibe a informação no painel do dashboard, simulando um alerta visual de perigo ou evacuação.

Essa abordagem foi escolhida para ilustrar de forma didática e funcional como uma solução baseada em IoT pode ser aplicada para monitoramento ambiental e emissão automatizada de alertas de risco, integrando hardware, protocolos de comunicação e visualização em tempo real.

# Projeto IoT - Monitoramento de Nível de Água e Chuva

- Quando o nível de água ultrapassa 75%, um LED é acionado como alerta.
- A intensidade da chuva é usada para indicar a possibilidade do aumento do nível de água.

## Hardware 

- ESP32 (simulado no Wokwi ou hardware real)
- 2 potenciômetros (simulando sensores de nível de água e chuva)
- LED conectado ao pino 26

## Software

- Código Arduino para ESP32
- Node-RED para gateway e dashboard com MQTT

## Configuração e Execução

### Arduino

1. Utilize a rede WiFi que está no `esp32_agua_chuva.ino`
2. Compile e envie para o ESP32
3. Verifique no monitor serial as leituras de "Chuva" e "Nível de Água"

### Node-RED

1. Importe o fluxo do arquivo `flow_node_red.json`
2. Configure o broker MQTT (exemplo usado: test.mosquitto.org)
3. Abra o dashboard para visualizar os dados e receber alertas

## Fluxo Node-RED

- Node MQTT subscribe para os tópicos `projeto/nivelagua` e `projeto/chuva`
- Processamento para acionar alerta quando nível de água > 75%
- Dashboard para mostrar dados em tempo real e status do LED

## Autores

- RM553542 Luiz Otávio Leitão Silva - 2TDSPR
- RM553748 Mauricio Vieira Pereira - 2TDSPC
- RM553483 Vitor de Melo Marques - 2TDSPR

