# auntification

# Протокол HTTP. Основы работы с консолью разработчика в браузере.

## Цель:
получить практические навыки работы с HTTP протоколом. На практике проанализировать процесс аутентификации пользователей в двух произвольных web-ресурсах.

## Постановка задачи:
написать эссе, в котором анализируется процесс аутентификации пользователей в двух произвольных web-ресурсах.

## Эссе

В качестве первого истояника рассмотрим https://www.hackster.io/ и процесс аунтификации через Google.
<br><br>Послен нажатия на кнопку "Войти через Google" просиходит GET запрос на https://www.hackster.io/users/auth/google_oauth2?login_locale=en&redirect_to=%2F&setup=true&location=signin_dialog&source=nav.
<br><br>В ходе запроса унстанавливается немного печенек и происходит перенаправление по адресу https://accounts.google.com/o/oauth2/auth?access_type=offline&client_id=194136473933-bh5c4avsnut4s8j4tt1hutvc5klohsak.apps.googleusercontent.com&redirect_uri=https%3A%2F%2Fwww.hackster.io%2Fusers%2Fauth%2Fgoogle_oauth2%2Fcallback&response_type=code&scope=email+profile&state=8b8aae9f4eea5d8cf00f7f9913f46d99526a15849ee308b6.
<br><br>После презапроса устанавливаем ещё немного печенек и опять перенаправляемся в https://www.hackster.io/users/auth/google_oauth2/callback?state=8b8aae9f4eea5d8cf00f7f9913f46d99526a15849ee308b6&code=4%2F0AX4XfWioScXim2vy2NDt-qNlcOKKzHFqoxFgHrcWB_ER5GNcNlDFcLSnVY45wQELH3BeXw&scope=email+profile+https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fuserinfo.email+https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fuserinfo.profile+openid&authuser=0&prompt=none.
<br><br>Все мы знаем что печенек мало не бывает, поэтому возьмём ещё печенек и перенаправимся дальше в https://www.hackster.io/?f=1.
<br><br>Там мы получим ETag ну, и конечно ЕЩЁ БОЛЬШЕ ПЕЧЕНЬЯ ДЛЯ БОГА ПЕЧЕНЬЯ!!! И на этом наш паровозик редиректов заканчивается и мы залогиненые идёи обмазываться печеньками<br>
![КТО УКРАЛ МОИ ПЕЧЕНЬКИ!!!](https://i.pinimg.com/736x/46/b2/d9/46b2d9cf4a26e1b6cf9a866b637fd603--chocolate-chip-cookies-chocolate-chips.jpg)

<br>

В качестве второго сайта я взял https://stepik.org/ с авторизацией через логин и пароль.
<br><br>
После нажатия кнопки войти у нас посылается куча различных AJAX запросов большая часть из которых это различные отслеживания яндекса, но нас интересует POST запрос с названием login.
По сути он перекидывает JSON с моим логином и паролем, а следом приходит GET запроc, который логинит меня на сайте. 
<br><br>
В ходе лабороторноя мы рассмотрели два разных способа авторизации, которые координально отличаются друг от друга. В одном мы катались на паровозике редиректов и собирали печеньки для cookie монстра, а другом мы предали свой логин и пароль иполучили ответ, который пустил нас на сайт.

