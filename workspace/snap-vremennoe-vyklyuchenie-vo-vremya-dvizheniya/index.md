# Snap - временное выключение во время движения

_Дата публикации: 13.01.2014_

**Внимание:** данный хук можно применить с помощью программы [CdrTuning](http://cdrpro.ru/macros/) (без ручного редактирования файла).

Во время движения точки или фигуры можно временно выключать **snap** (ранее включенный) нажатием и удержанием клавиши **Alt**. Удобство работы повышается на порядок.

Напоминание: **Alt** надо нажимать после начала движения.

Предварительная единоразовая настройка одного файла:  
_c:\Program Files\Corel\CorelDRAW Graphics Suite 13\Programs\UIConfig\CorelDRAW\DrawUI.xml_

1\. делаем копию этого файла на всякий случай!  
2\. редактируем исходный **DrawUI.xml**  
3\. ищем **modifierKeyTables**  
4\. добавляем указанный текст после **table tableID=...**

```xslt
<keySequence guid="3bdee6d4-b8fb-4d2a-8153-de70a596192e">
    <key>VK_MENU</key>
</keySequence>
```

5\. теперь секция должна выглядеть в Х3 (в Х4 немного отличается) так:

```xslt
<modifierKeyTables>
    <table tableID="49efc5c9-e012-42eb-9c83-208db2166df3">
        <keySequence guid="3bdee6d4-b8fb-4d2a-8153-de70a596192e">
            <key>VK_MENU</key>
        </keySequence>
        <keySequence guid="656AF17B-7ACE-4e67-B12D-8ACD2F14D788">
            <key ctrl="true"></key>
            <!--Constraint Snowflake using Corel Keys-->
        </keySequence>
        <keySequence guid="5778B802-89B9-4b1e-8FFE-C83E6F710586">
            <key shift="true"></key>
            <!--Constraint Snowflake-->
        </keySequence>
    </table>
</modifierKeyTables>
```

p.s. клавиши можно указать другие, их синтакс: A..Z, VK_F1... и т.д. гуглить по "список клавиш VK_MENU". Ну и для порядка: трюк стал известен благодаря кор-кодеру корела.

Актуально для CorelDRAW X3 и выше.

Источник: [forum.rudtp.ru](http://forum.rudtp.ru/showthread.php?t=38571&highlight=snap)
