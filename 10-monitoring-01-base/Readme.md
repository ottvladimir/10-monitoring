# Домашнее задание к занятию "10.01. Зачем и что нужно мониторить"

## Обязательные задания

1. Вас пригласили настроить мониторинг на проект. На онбординге вам рассказали, что проект представляет из себя 
платформу для вычислений с выдачей текстовых отчетов, которые сохраняются на диск. Взаимодействие с платформой 
осуществляется по протоколу http. Также вам отметили, что вычисления загружают ЦПУ. Какой минимальный набор метрик вы
выведите в мониторинг и почему?
Если брать минимум то:  
-	CPU, диски(нагрузка, свободное место),RAM хоста на котором крутится приложение;   
- Коды ответа приложения (код 200, 500 и тп);  
-	Проверка доступности входа в приложение (логин);  
-	Количество коннектов на сервис;  
Дополнительно можно мониторить таймауты (зависания) приложения.

2. Менеджер продукта посмотрев на ваши метрики сказал, что ему непонятно что такое RAM/inodes/CPUla. Также он сказал, 
что хочет понимать, насколько мы выполняем свои обязанности перед клиентами и какое качество обслуживания. Что вы 
можете ему предложить?
- Отчет о количестве предотвращенных "теоретических" отказов.(Из-за конца диска(место, inod'ы), RAM)
- Можно предложить мониторить выполнение SLA:
   -	На количество отчетов завершившихся неудачно;
   -	На доступность приложения;
   - Время реакции на недоступность приложения.


3. Вашей DevOps команде в этом году не выделили финансирование на построение системы сбора логов. Разработчики в свою 
очередь хотят видеть все ошибки, которые выдают их приложения. Какое решение вы можете предпринять в этой ситуации, 
чтобы разработчики получали ошибки приложения?  

   1. У Zabbix есть возможность создать свой item почти на каждый чих, поэтому делаем на логи приложения items и отслеживаем ошибки,с Prometheus не работал но думаю такая возможность есть.  
   2. Если есть Grafana, в ней тоже можно натравить dashboard на syslog.
  
4. Вы, как опытный SRE, сделали мониторинг, куда вывели отображения выполнения SLA=99% по http кодам ответов. 
Вычисляете этот параметр по следующей формуле: summ_2xx_requests/summ_all_requests. Данный параметр не поднимается выше 
70%, но при этом в вашей системе нет кодов ответа 5xx и 4xx. Где у вас ошибка?

 Мы не учли коды 3xx (Redirection)
