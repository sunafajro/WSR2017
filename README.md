# WSR2017

Configs for WorldSkills 2017 Cisco Lab

## Таблица 1
Устройство | Интерфейс (Сеть) | IPv4-адрес  |
 :---: | :---: | :---: |
HQ1 | G0/0 (LAN) | 172.16.138.254/24 |
HQ1 | S0/1/0 (INET1) | 20.18.64.2/29 |
HQ1 | Loopback 101 | 11.11.11.11/32 |
HQ1 | Tunnel 100 | - |
ISP | S0/1/0 (INET1) | 20.18.64.1/29 |
ISP | VT1 (INET3) | 20.18.64.13/29 | 
ISP | Loopback 100 | 8.8.8.8/32 |
ISP | Loopback 101 | 33.136.0.1/16 |
ISP | Loopback 102 | 161.66.0.1/16 |
BR3 | Dialer1 (INET3) | 20.18.64.14/29 |
BR3 | Loopback 101 | 192.168.33.254/24 |
BR3 | Loopback 102 | 192.168.34.254/24 |
BR3 | Loopback103 | 3.3.3.3/32 |
BR3 | Tunnel100 | - |
