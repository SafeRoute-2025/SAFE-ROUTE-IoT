# SAFE-ROUTE-IoT

## Descrição

Sistema IoT para monitoramento do nível de água e intensidade da chuva utilizando ESP32 e sensores simulados. Os dados são enviados via MQTT para o Node-RED, que exibe um dashboard em tempo real.

# Projeto IoT - Monitoramento de Nível de Água e Chuva

- Quando o nível de água ultrapassa 75%, um LED é acionado como alerta.
- A intensidade da chuva é usada para indicar a possibilidade do aumento do nível de água.

## Hardware ()

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

## Imagens

- `imagens/diagrama_iot.png` - Esquema básico do hardware e fluxo de dados

---

## Autor

Seu Nome - Data
