# PickAgentDemo
First repository I've created... 

ENGLISH VERSION COMING SOON... (i don't recommend to google translate that)

В общем, решил позаливать свои "программистические" наработки на GitHub, так как посчитал нужным уже сейчас копить портфолио, что может аукнуться в дальнейшем, когда мне придётся думать о чём-то типа устройства на работу. 

Этот проект - альтернатива существующей в FL Studio фиче "Plugin Picker". Plugin Picker позволяет вывести список VST и не-VST плагинов на весь экран, а затем drag'n'drop'ом перетягивать нужный в нужное место (микшер, Channel rack, плейлист). Но есть одна проблема: плагины вываливаются сразу кучей; снизу, конечно, можно выбрать группу плагинов, но водить каждый раз вниз мышкой не очень охота, тем более группа "активируется" при НАВЕДЕНИИ на соответствующий пункт, а не НАЖАТИИ, что кому-то может показаться некомфортным (например, мне).

Моё творение основывается на меню закупки CS:GO: всё по категориям, всё под рукой, и если приноровиться, то будешь знать на интуитивном уровне, где какой предмет находится. 

Как по идее должно выглядеть использование программы:
1) Пользователь как-то удобно запускает программу (или вызывает из трея). Пока не придумано, как оно будет "удобно" вызываться, но для тестов я забиндил на своей Logitech G102 запуск exe-шника программы на среднюю кнопку мыши, переключающую по умолчанию чувствительность сенсора. В FL Studio Plugin Picker вызывается либо f8, либо колесом мыши по пустой области, что весьма удобно, потому что этой самой "свободной областью" считается верхний край программы (экрана).
[пока писал этот файл, придумал: вызов программы происходит, когда мышь находится в верхнем крае и юзер нажимает ПКМ. Надо будет затестить...]
2) После вызова на весь экран появится интерфейс программы. Окно программы Top-most, а также затемняет все открытые окна сзади. На начальной "пицце" появятся те папки, которые были выбраны пользователем заранее.
3) Пользователь проходит по папкам, нажимая на них, и в конце концов добирается до нужного файла. 
4) Пользователь зажимает кнопку мыши за нужный сегмент и перетягивает в нужное место. После начала "перетягивания" окно программы закрывается.

Если человек передумал добавлять плагин, он нажимает Escape (ну или alt+f4 :) )

Если количество элементов на "пицце" перевалит за 16, снизу появятся кнопки для прокрутки страниц (на одной странице 16 элементов). Также можно переключаться между страницами с помощью нажатий правой кнопкой по левой/правой части программы, что очень удобно.

Снизу справа будет строка поиска, где можно будет ввести название нужного плагина. Можно сделать активацию этой строки по началу ввода с клавиатуры (без необходимости переводить фокус ввода).

Слева будут располагаться вкладки-варианты наборов начальных папок на начальной "пицце".

Справа - какая-нибудь информация о плагине. Можно сделать выход в интернет, чтобы узнать год выпуска плагина, вывести описание, кликабельную ссылку на сайт разработчика и т.д.

Программа, к сожалению, не доделана, но, тем не менее, можно попытаться её использовать, если кому интересно... Я даже поленился сделать окно для выбора папок, поэтому вам придётся компилировать этот проект самому, изменив кое-что в файле класса Directories "Models\Directories.cs". А именно: в функции FillTest() уже будет две строчки кода с путями файлов, и нужно заменить то, что в кавычках, на пути ваших папок, которые должны быть на главной "пицце". Также можно дублировать эти строчки; по идее можно добавлять их бесконечно, хотя в некоторых ситуациях я замечал вылеты. Можно добавлять любые папки, не только FL'овские "Plugin Database\Effects" и "Plugin Database\Generators".
Я не делал оптимизацию под разные экраны, нормально оно работает только с разрешением 1920x1080. Надеялся на обещанные "условные пикселы" в WPF, но, видимо, что-то пошло не так. В общем, оно неправильно отображается на разных мониторах. 
Фактически, приложение после нажатия на нужный сегмент с файлом вызывает событие копирования с помощью Drag'n'drop. Поэтому, можно не только, например, добавлять плагины в DAW-программы, но и бесконечно сидеть и копировать какой-нибудь файл :)

Необходимость в подобном проекте отпала, когда с FL 21 завезли обновлённый Browser, где можно начать писать название плагина, как сразу выведется плагин, чтобы его "перенести" на нужное место. Но, если я соберусь с силами, то, в принципе, вполне реально это доделать, к тому же, это можно использовать не только с FL-кой, но и с другими программами.

В общем, как-то так, пойду дальше готовиться к КР по матану, к зачёту по методам оптимизации и делать ДЗ по матлогике...

-------------
