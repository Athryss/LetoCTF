# Grafana + Prometheus + SpringBoot+ node exporter monitor

Сконфигурированная система мониторинга для отслеживания состояния докеров и хостового-сервера.

В Grafana заранее настроены следующие дашборды

## JVM Dashboard
- Память процесса (предоставляется [micrometer-jvm-extras](https://github.com/mweirauch/micrometer-jvm-extras))
- Использование ЦП, Нагрузка, Потоки, Состояния потоков, Дескрипторы файлов, События журнала
- Пулы памяти JVM (кучи, без кучи)
- Вывоз мусора/давление
- Классная загрузка
- Direct-/Mapped-Buffer
- Минималистичный обзор ввода-вывода
    - HTTP - Скорость, Ошибки, Продолжительность
    - TOMCAT/JETTY - Утилизация

## Monitore via node
Данный Dashboard визуализирует состояние системы, развернутой в Docker-контейнерах. Он использует Prometheus для сбора метрик и Node Exporter 0.16 для мониторинга хостовых метрик. 
На главной странице дашборда представлен общий обзор состояния системы, включая количество запущенных контейнеров, использование CPU и RAM, а также нагрузку на сеть. 
Далее следуют отдельные разделы, посвященные мониторингу различных компонентов системы, таких как базы данных, веб-серверы и прочие сервисы. В каждом разделе представлены соответствующие графики, отображающие изменение ключевых метрик во времени. 
Также на дашборде присутствуют уведомления о возможных проблемах в работе системы, например, если какой-то контейнер перестал отвечать на запросы или если возникла проблема с доступностью базы данных. 
В целом, данный Dashboard обеспечивает операторам системы полный контроль над состоянием всех компонентов системы, позволяя быстро реагировать на возможные проблемы и сбои в работе.

# installation
```
docker network create external-network
docker-compose up -d
```
# How to use
```
http://localhost:3000

or 

http://{server_ip}:3000
```


