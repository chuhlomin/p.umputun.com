---
title: "Львы на Красной площади"
date: 2014-12-31T14:20:40-05:00
draft: false
tags: ["назад в прошлое"]
---

Сначала анекдот: «На Красной площади мужик, очень странного вида, бегает кругами и истошно вопит. К нему подходит милиционер и спрашивает – вы, что же творите, гражданин? Тот в ответ – львов разгоняю. Милиционер с удивлением осматривается и говорит, что никаких львов не видит, на что мужик отвечает – «потому и не видите, что я всех разогнал.»

Это я к тому, что параноиков (в хорошем смысле этого слова), защищающих свой домашний компьютер различными файрволами, только ленивый не сравнит с тем мужиком из анекдота. Ну и в самом деле, всегда спрашиваешь себя, а кому я нужен со своим железным другом. Неужели в сети нет более привлекательных жертв, для потенциальных хакеров ? И вообще, существуют ли они (хакеры) в природе, или эта просто такая пугалка последних лет ?

Где-то с неделю назад, просматривая логи моего сервера, я с удивлением обнаружил многочисленный следы работы сканеров системы безопасности. Т.е. кто-то проверял на доступность все подряд порты, и на открытых, пробовал разные известные приемы, по взлому и опусканию компьютера. Так, впервые, вопрос защиты из чего-то параноидально-абстрактного, превратился, в реально пугающий. К слову, у меня вся локальная домашняя сеть (из 4х компьютеров) подключена к интернету через linux box, на котором бежит стандартный линкусовый файрвол iptables. Этот зверь, информацию обо всех отбитых атаках заносит в системный лог, и среди всякой полезной информации, там содержится и ip адрес злоумышленника. Вычленив его от-туда, я решил попробовать разобраться с невидимым врагом.

В принципе путей здесь два – административный и технический. В первом случае выяснив через какого провайдера злоумышленник подключен к инету, можно написать ему (провайдеру) письмо с жалобой и приложенными логами. Во втором случае, попытаться разобраться самому. Что я и решил попробовать.

Первым делом я попытался просто зайти по этому адресу обычным веб-браузером. Там оказался, довольно навороченный сайт, продающий что-то, и конечно дешевле всех   Уже хорошо. После этого, я задал сканеру (ShadowSecure) адрес, и запустил его на сканирование. Минут через 10, процесс завершился, и результат был передо мной. Надо сказать, что такого я не ожидал. Обнаружилось 30 (тридцать!) дыр системы безопасность высокого уровня риска. Т.е. через любую из них, я теоретически, мог получить доступ к полному управлению системой. Решив проверить теорию практикой, я полез в первую дыру, и через несколько минут оказался внутри вражеского компьютера. При этом доступ был абсолютный, начиная от удаленного управления сервисами, и кончая возможностью модификации любых системных файлов. Т.е. поверженный противник, лежал у моих ног и тихо ждал своей участи. Побродив по оккупированной территории с пол часа, я понял, что это не просто веб сервер. Он по совместительству оказался и файл сервером всей фирмы, и все проекты разработчиков также лежали на нем. Ну, в общем, на этом я решил свой первый в жизни взлом прекратить и, не нанеся врагу никакого урона, вернутся домой.

Этот случай, поразил меня тем, что оказывается, львы на Красной площади действительно бродят, и кто не будет их разгонять, может запросто оказаться съеденным, и тем, что защите народ, в массе своей, не придает никакого значения.

Другими словами, люди, будьте бдительны, в сети действительно есть придурки, лезущие в чужие системы, и цели их совсем неблагородны

Пока я писал эту заметку, глянул краем глаза в последние логи. Там опять происки врагов, при чем многих сразу. На первый взгляд похоже на распределенную атаку, но надо еще проверить. Во всяком случае, каждые 1-2сек. приходит запрос на обслуживание (с разных адресов), отрубаемый моим файрволом, как некорректный.

Так что, пошел я охотится на львов. Надеюсь, вернусь с победой

_Если вы еще не поняли, что это было – то это был эксперимент под кодовым названием "назад в прошлое", републикации заметки из моего уютного бложика, 13-ти летней выдержки._
