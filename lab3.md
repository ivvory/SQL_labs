## Lab 3, variant 5

Схема таблицы ГОСУДАРСТВА:
-	Название
-	Площадь (км2)
-	Население
-	Язык
-	Денежная единица
-	Религия

**Ограничение уникальности**: название государства.<br>
**Проверочные ограничения**: <br>
    a) религия должна быть из следующего списка: римско-католическая, православная, ислам, буддизм, иудаизм, лютеранская, протестантская.<br> 
    b) площадь и население >0.<br>
**Спецификация представления**: представляемая таблица содержит название государства, площадь, население, религию для государств с 
английским языком общения.<br>
**Спецификация курсора**: результирующая таблица включает все сведения о странах с религией ислам.

## Выполнение работы

> Составить оператор создания таблицы с учетом приведенных в задании ограничений и выполнить данный оператор на SQL сервере в базе данных electr. 

```sql
CREATE TABLE `2016_studentdb`.`ta5_Vladimirskiy_countries` (
    `id` INT NOT NULL AUTO_INCREMENT,
    `name` VARCHAR(45) UNIQUE NULL,
    `area_T` DOUBLE NULL,
    `population_M` DOUBLE NULL,
    `language` VARCHAR(45) NULL,
    `currency_unit` VARCHAR(45) NULL,
    `religion` VARCHAR(45) NULL,    
    PRIMARY KEY (`id`),
    CHECK (`religion` IN ('catholic', 'orthodox', 'islam', 'buddhism', 'judaism', 'lutheran', 'protestant', NULL) AND 
        `area_T` > 0 AND 
        `population_M` > 0))
```

> Заполнить созданную таблицу с использованием оператора включения (6-8 записей). Просмотреть заполненную таблицу.

```sql
INSERT INTO `2016_studentdb`.`ta5_Vladimirskiy_countries` (`id`, `name`, `area_T`, `population_M`, `language`, `currency_unit`, `religion`) VALUES ('1', 'Belarus', '207,6', '9,608', 'belorussian', 'belorussian_ruble', 'orthodox');
INSERT INTO `2016_studentdb`.`ta5_Vladimirskiy_countries` (`id`, `name`, `area_T`, `population_M`, `language`, `currency_unit`) VALUES ('2', 'Ethiopia', '1119,683 ', '96,633', 'ethiopic', 'birr');
INSERT INTO `2016_studentdb`.`ta5_Vladimirskiy_countries` (`id`, `name`, `area_T`, `population_M`, `language`, `currency_unit`) VALUES ('3', 'Finland', '305,470 ', '5,268', 'finland', 'euro');
INSERT INTO `2016_studentdb`.`ta5_Vladimirskiy_countries` (`id`, `name`, `area_T`, `population_M`, `language`, `currency_unit`) VALUES ('4', 'Japan', '364,485 ', '127,103', 'japanease', 'yen');
INSERT INTO `2016_studentdb`.`ta5_Vladimirskiy_countries` (`id`, `name`, `area_T`, `population_M`, `language`, `currency_unit`) VALUES ('5', 'Luxembourg', '2,585', '0,520', 'france', 'euro');
INSERT INTO `2016_studentdb`.`ta5_Vladimirskiy_countries` (`id`, `name`, `area_T`, `population_M`, `language`, `currency_unit`) VALUES ('6', 'Niger', '1266,699 ', '17,466', 'hindi', 'CFA Franc');
INSERT INTO `2016_studentdb`.`ta5_Vladimirskiy_countries` (`id`, `name`, `area_T`, `population_M`, `language`, `currency_unit`, `religion`) VALUES ('7', 'Scotland', '78,772 ', '5,327', 'english', 'British pound sterling', 'catholic');
```
```sql
SELECT * FROM 2016_studentdb.ta5_Vladimirskiy_countries;
```
![sel_all](sel_all.png)