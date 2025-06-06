# SAFE-ROUTE-IoT

Sistema IoT para monitoramento do nível de água e intensidade da chuva utilizando ESP32 e sensores simulados. Os dados são enviados via MQTT para o Node-RED, que exibe um dashboard em tempo real.

## Projeto IoT - Monitoramento de Nível de Água e Chuva

Este projeto faz parte da solução SafeRoute — uma plataforma de alertas inteligentes e evacuação segura. O objetivo da SafeRoute é otimizar a comunicação e organizar rotas seguras de evacuação durante eventos climáticos extremos, como enchentes e tempestades severas.

Para demonstrar um exemplo funcional desse conceito, desenvolvemos um protótipo IoT que simula a medição de níveis de chuva e água, com acionamento de um alerta visual (LED) quando a situação atinge níveis críticos.

O sistema utiliza sensores simulados (potenciômetros no Wokwi) para representar a intensidade da chuva e o nível da água. Esses dados são enviados via protocolo MQTT para um broker e exibidos em tempo real em um dashboard no Node-RED.

A lógica funciona da seguinte forma:

A leitura da chuva é apenas informativa, simulando o aumento potencial do nível da água.

Quando o nível da água ultrapassa 75%, o sistema aciona um LED no simulador e exibe a informação no painel do dashboard, simulando um alerta visual de perigo ou evacuação.

Essa abordagem foi escolhida para ilustrar de forma didática e funcional como uma solução baseada em IoT pode ser aplicada para monitoramento ambiental e emissão automatizada de alertas de risco, integrando hardware, protocolos de comunicação e visualização em tempo real.

## Integrantes

- RM553542 Luiz Otávio Leitão Silva - 2TDSPR
- RM553748 Mauricio Vieira Pereira - 2TDSPC
- RM553483 Vitor de Melo Marques - 2TDSPR

  graph TD
    A[Sensores Simulados] -->|Dados| B(ESP32)
    B -->|MQTT| C[Broker Mosquitto]
    C --> D[Node-RED]
    D --> E[Dashboard]
    D --> F[Alertas]

## Tecnologias Utilizadas 

- Wokwi (Simulador de Arduino/ESP32)
- ESP32
- Node-RED
- Node-RED Dashboard
- MQTT Broker

## Configuração e Execução

### Wokwi

1. Instale as bibliotecas 'WiFi' e 'PubSubClient' 
2. Utilize a rede WiFi 'Wokwi-GUEST' e senha ''
3. Compile e envie para o ESP32
4. Verifique no monitor serial as leituras de "Chuva" e "Nível de Água"

### Node-RED

1. Abra o CMD e digite 
1. Importe o fluxo do arquivo `flow_node_red.json`
2. Configure o broker MQTT (exemplo usado: test.mosquitto.org)
3. Utilize a porta 1883
4. Rode o projeto no Node-RED
5. Abra o dashboard para visualizar os dados e receber alertas

## Fluxo Node-RED

- Node MQTT subscribe para os tópicos `projeto/nivelagua` e `projeto/chuva`
- Processamento para acionar alerta quando nível de água > 75%
- Dashboard para mostrar dados em tempo real e status do LED



