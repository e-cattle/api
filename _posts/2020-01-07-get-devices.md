---
category: Totem
path: '/totem/devices'
title: 'Get sensor devices'
type: 'GET'

layout: nil
---

This method allows users to get all registered sensor devices in BigBoxx.

### Request

* The headers must include a **valid authentication token**.

### Response

Sends back a collection of things.

```Status: 200 OK```
```[
  {
    "enable": true,
    "created": "2019-10-21T19:06:39.254Z",
    "changed": "2019-10-21T19:06:39.254Z",
    "_id": "5dae022aabdb837c1e3374a0",
    "name": "Snooper 1.0",
    "description": "Dispositivo de aferição de dados ambientais.",
    "branch": "Embrapa Gado de Corte",
    "model": "1.17.8",
    "mac": "2c:3a:e8:1b:01:50",
    "local": "No PLEASE Lab para testes em ambiente controlado.",
    "sensors": [
      {
        "_id": "5dae022aabdb837c1e3374a4",
        "type": "type-air-temperature",
        "description": "Temperatura (-40° a 125°C, com precisão de ±0,5°C).",
        "name": "DHT22-TEMPERATURE",
        "label": "DHT22"
      },
      {
        "_id": "5dae022aabdb837c1e3374a3",
        "type": "type-air-temperature",
        "description": "Temperatura (-200°C a 1300°C).",
        "name": "THERMOCOUPLE",
        "label": "Termopar (Tipo K) e MAX31855"
      },
      {
        "_id": "5dae022aabdb837c1e3374a2",
        "type": "type-relative-humidity",
        "description": "Úmidade (0 a 100%, com precisão de 5%).",
        "name": "DHT22-HUMIDITY",
        "label": "DHT22"
      },
      {
        "_id": "5dae022aabdb837c1e3374a1",
        "type": "type-ch4",
        "description": "Gases inflamáveis (de 300 a 10.000ppm).",
        "name": "MQ-2"
      }
    ],
    "version": 1,
    "__v": 0
  },
  {
    "enable": false,
    "created": "2019-10-21T19:06:39.254Z",
    "changed": "2019-10-21T19:06:39.254Z",
    "_id": "5dae0251abdb837c1e3374aa",
    "name": "BalPass 1.0",
    "description": "Balança de passagem para animais à campo.",
    "branch": "Coimma",
    "model": "1.16.3",
    "mac": "4f:21:a8:2b:d1:53",
    "local": "Piquete do Mangueiro Digital.",
    "sensors": [
      {
        "_id": "5da6428fc3424450786c8c84",
        "type": "type-animal-weight",
        "name": "YGX-DYZ011",
        "description": "Massa/peso (até 80t, com precisão de 2%)."
      }
    ],
    "version": 1,
    "__v": 0
  },
  {
    "enable": false,
    "created": "2019-10-21T19:06:39.254Z",
    "changed": "2019-10-21T19:06:39.254Z",
    "_id": "5dae0268abdb837c1e3374ae",
    "name": "BalPass 1.0",
    "description": "Balança de passagem para animais à campo.",
    "branch": "Coimma",
    "model": "1.16.3",
    "mac": "6a:af:d8:3c:f2:9b",
    "local": "Área de iLPF de ambiência e bem-estar.",
    "sensors": [
      {
        "_id": "5da7856b6e00ad51657984e1",
        "type": "type-animal-weight",
        "name": "YGX-DYZ011",
        "description": "Massa/peso (até 80t, com precisão de 2%)."
      }
    ],
    "version": 1,
    "__v": 0
  }
]```

For errors responses, see the [response status codes documentation](#response-status-codes).