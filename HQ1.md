1. Задайте имя устройства в соответствии с топологией
```
#(config) hostname HQ1
```
2. Назначьте доменное имя wsr2017.ru
```
#(config) ip domain-name wsr2017.ru
```
3. Создайте пользователя wsr2017 с паролем cisco
  - Пароль пользователя должен храниться в конфигурации в виде результата хэш-функции.
  - Пользователь должен обладать максимальным уровнем привилегий.
```
#(config) username wsr2017 privilege 15 secret cisco
```
4. Для ВСЕХ устройств реализуйте модель AAA.
  - Аутентификация на удаленной консоли должна производиться с использованием локальной базы данных
  - После успешной аутентификации при входе с удаленной консоли пользователь сразу должен попадать в режим с максимальным уровнем привилегий.
  - Настройте необходимость аутентификации на локальной консоли.
  - При успешной аутентификации на локальной консоли пользователь должен попадать в режим с минимальным уровнем привилегий.
```
#(config) aaa new model
#(config) aaa authentication login CONSOLE local
#(config) aaa authentication login SSH local
#(config) line console 0
#(config-line) login authentication CONSOLE
#(config-line) privilege 1
#(config) line vty 0 15
#(config-line) login authentication SSH
#(config-line) privilege 15
```
5. Установите пароль wsr на вход в привилегированный режим. 
  - Пароль должен храниться в конфигурации НЕ в виде результата хэш-функции.
  - Настройте режим, при котором все пароли в конфигурации хранятся в зашифрованном виде.
```
#(config) enable password wsr
#(config) service password-encryption
```
7. Устройство должно быть доступно для управления по протоколу SSH версии 2.
```
#(config) crypto key generate rsa
#(config) ip ssh version 2
#(config) line vty 0 15
#(config-line) transport input ssh
```
8. Установите правильное локальное время
```
# clock set 13:32:00 23 July 2017
# clock timezone MSK 3 
```
