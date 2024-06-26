**Хранилище данных** ([англ.](https://ru.wikipedia.org/wiki/%D0%90%D0%BD%D0%B3%D0%BB%D0%B8%D0%B9%D1%81%D0%BA%D0%B8%D0%B9_%D1%8F%D0%B7%D1%8B%D0%BA "Английский язык") Data Warehouse) — предметно-ориентированная информационная [база данных](https://ru.wikipedia.org/wiki/%D0%91%D0%B0%D0%B7%D0%B0_%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 "База данных"), специально разработанная и предназначенная для подготовки отчётов и бизнес-анализа с целью поддержки принятия решений в организации. Строится на базе [систем управления базами данных](https://ru.wikipedia.org/wiki/%D0%A1%D0%A3%D0%91%D0%94 "СУБД") и [систем поддержки принятия решений](https://ru.wikipedia.org/wiki/%D0%A1%D0%9F%D0%9F%D0%A0 "СППР"). Данные, поступающие в хранилище данных, как правило, доступны только для чтения.

Обычно данные в организациях хранятся «разрозненно». В бухгалтерии одна система хранения, в логистике и прочих отделах — другая. Желательно, чтобы эти системы хранения не пересекались — и в этом есть логика. Так, например, информация о финансовых поступлениях и налоговых отчислениях не будет доступна никому, кроме сотрудников отдела бухгалтерии.

Но эта «разрозненность» вызывает много вопросов. Например, как подготовить аналитику состояния компании за год? Как объединить данные из разных источников и информационных систем в одном месте? Ведь база данных (БД) склада хранит только информацию о складских запасах, а база отдела кадров — данные о сотрудниках. Как их очистить, структурировать и анализировать? На помощь приходит Data Warehouse.

**Признаки и особенности DWH:**

- **Аналитику не нужно запрашивать доступы к базам данных разных отделов.** Все хранится в одном месте, при этом в DWH могут храниться агрегированные данные за десятки лет.

- **Данные в хранилище добавляются, удаляются, очищаются, выгружаются.** К этому хранилищу выполняются запросы, также с ним производятся другие манипуляции.

- **При использовании систем бизнес-аналитики (BI) совместно с DWH у пользователей появляется возможность искать закономерности и взаимосвязи в данных, аналитически обрабатывать и визуализировать информацию.** Аналитик изучает данные из хранилища, формирует отчет, подкрепляя статистической информацией, визуализирует.


## Полная архитектура хранилища данных

Одна из моделей проектирования Data Warehouse — «слоеный пирог», построенный по архитектуре [LSA, Layered Scalable Architecture](https://help.sap.com/saphelp_SCM700_ehp02/helpdata/en/4a/124597ca771b41e10000000a42189c/frameset.htm). Она реализует логическое деление структур с данными на несколько функциональных уровней: 

1. **Стейджинг (Primary Data Layer)** — уровень, на котором подгружаются данные из внешних источников. Например, из таблиц, ERP-системы или биллинговой системы.

2. **Ядро хранилища (Core Data Layer)** — центральный уровень, который подгоняет данные к единым структурам и ключам. На этом слое обеспечивается целостность и качество данных. 

3. **Аналитические витрины (Data Mart Layer)** — слой, который преобразует данные к структурам, удобным для анализа и использования в BI-дашбордах и других аналитических системах. 

4. **Сервисный слой (Service Layer)** — уровень, на котором обеспечивается управление предыдущими слоями, мониторинг и диагностика ошибок.  

Визуально LSA-архитектуру Data Warehouse можно представить так:


![[DWH - LSA structure.png]]

## Для чего крупному бизнесу хранилище данных

Мы уже определили, что хранилище данных — это информационная система, предназначенная для подготовки отчетов и бизнес-анализа. Наряду с этим DWH помогает: 

- безопасно хранить данные в одном месте из множества источников,
- создавать специальные отчеты и работать со сложными запросами,
- преобразовывать данные в стандартный формат даже из устаревших систем,
- очищать и удалять некачественную информации, обнаруживать повторяющиеся, поврежденные или неточные наборы данных,
- сократить общее время обработки для анализа и отчетности,
- хранить большое количество исторических данных.