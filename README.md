# 🌱 Estufa Automatizada com NodeMCU

Este projeto consiste em uma estufa automatizada de baixo custo, capaz de monitorar e controlar variáveis ambientais como umidade do solo e luminosidade, utilizando sensores, atuadores e um microcontrolador ESP8266 (NodeMCU). O sistema permite o cultivo de diferentes tipos de plantas de forma mais eficiente e sustentável, com suporte a monitoramento local e remoto.

## 🔧 Tecnologias Utilizadas

- **NodeMCU ESP8266**
- **C++ / Arduino IDE**
- **Sensores:**
  - Umidade do solo (resistivo)
  - Temperatura/pressão (BMP280)
  - Luminosidade (BH1750)
- **Atuadores:**
  - Bomba d'água (via módulo relé)
  - Lâmpada LED (via módulo relé)
- **Display LCD I²C**
- **Joystick digital**
- **Servidor Flask (Python)**
- **Blynk (monitoramento remoto via app)**

## 📦 Funcionalidades

- Leitura contínua da umidade do solo, temperatura e luminosidade.
- Acionamento automático da bomba d’água e lâmpada com base em parâmetros ideais.
- Seleção da planta cultivada via joystick com exibição no LCD.
- Requisição dinâmica de parâmetros via API Flask em formato JSON.
- Visualização remota dos dados via aplicativo Blynk.

## 📲 Exemplo de Endpoint

O NodeMCU requisita os dados de configuração da planta selecionada via HTTP:

```
GET http://192.168.0.100:5000/plantas/1
```

Resposta esperada:

```json
{
  "id": 1,
  "name": "Erva-mate",
  "temperatura_min": "20.00",
  "temperatura_max": "35.00",
  "umidade_solo_min": "60.00",
  "umidade_solo_max": "80.00",
  "tempo_luminosidade": 12
}
```

## 🛠 Como Rodar

### 1. Código NodeMCU

- Instale o [Arduino IDE](https://www.arduino.cc/en/software)
- Instale a placa ESP8266 via gerenciador de placas
- Instale as bibliotecas:
  - `Adafruit BMP280`
  - `BH1750`
  - `Blynk`
  - `ArduinoJson`
- Configure o arquivo `config.h` com seu Wi-Fi e token Blynk
- Faça upload para o NodeMCU via USB

### 2. Servidor Flask

```bash
cd servidor-flask
pip install -r requirements.txt
python app.py
```

A API estará disponível em `http://localhost:5000` ou no IP da sua rede local.

## 📷 Imagens do Projeto

![image](https://github.com/user-attachments/assets/5479c800-ee01-4d86-aff9-6093218286d2)


## ✅ Status

✅ Projeto finalizado e funcionando com todos os objetivos atingidos.

---

💡 Desenvolvido como parte de um Trabalho de Conclusão de Curso (TCC).
