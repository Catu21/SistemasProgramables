# OMNISERVE — Estacion de bebidas



\# Proyecto Omniserve - Dispensador Automatizado IoT



\- Diego Jahzeel Méndez Martínez (23240829)

\- Joshua Maximiliano Anguiano Contreras (23240329)



\## Descripción del Proyecto

Omniserve es un sistema IoT automatizado para dispensar líquidos y sólidos, controlado localmente mediante el protocolo MQTT. El sistema utiliza un ESP32 programado en MicroPython, integrando módulos de relés para el control de bombas de agua, servomotores para la dispensación de sólidos, y diversos sensores para monitorear el estado.



\## Sprint 1: Hardware y Tabla HAL

A continuación se presenta la asignación de pines y tópicos MQTT del firmware actual\[cite: 9]:



| #  | Componente         | Tipo     | Pin ESP32   | Tópico Publicación         | Tópico Suscripción     | Unidad | Rango  |

| :  |                    |          |             |                            |                        |        |        |

| 1  | DHT11              | Sensor   | GPIO 4      | `omniserve/temp`           | -                      | °C     | 0-50   |

| 2  | Ultrasónico        | Sensor   | GPIO 13, 34 | `omniserve/distancia`      | -                      | cm     | 2-400  |

| 3  | HX711              | Sensor   | GPIO 35, 32 | `omniserve/peso`           | -                      | g      | 0-5000 |

| 4  | Pantalla OLED      | Display  | GPIO 21, 22 | -                          | `omniserve/pantalla`   | -      | -      |

| 5  | Bomba 1 / rele     | Actuador | GPIO 23     | -                          | `omniserve/bomba1/cmd` | -      | ON/OFF |

| 6  | Bomba 2 / rele     | Actuador | GPIO 26     | -                          | `omniserve/bomba2/cmd` | -      | ON/OFF |

| 7  | Bomba 3 / rele     | Actuador | GPIO 27     | -                          | `omniserve/bomba3/cmd` | -      | ON/OFF |

| 8  | Bomba 4 / rele     | Actuador | GPIO 14     | -                          | `omniserve/bomba4/cmd` | -      | ON/OFF |

| 9  | Servo 1            | Actuador | GPIO 18     | -                          | `omniserve/servo1/cmd` | °      | 0-180  |

| 10 | Servo 2            | Actuador | GPIO 19     | -                          | `omniserve/servo2/cmd` | °      | 0-180  |

| 11 | ESP32-CAM          | Cámara   | -           | `omniserve/cam/frame`      | -                      | JPEG   | -      |