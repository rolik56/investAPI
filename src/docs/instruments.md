

 <!-- range HasServices -->






# InstrumentsService
Сервис предназначен для получения:</br> **1**.  информации об инструментах;</br> **2**.
расписания торговых сессий;</br> **3**. календаря выплат купонов по облигациям;</br> **4**.
размера гарантийного обеспечения по фьючерсам;</br> **5**. дивидендов по ценной бумаге.

##Методы сервиса


### TradingSchedules
Метод получения расписания торгов торговых площадок

- Тело запроса — [TradingSchedulesRequest](#tradingschedulesrequest)

- Тело ответа — [TradingSchedulesResponse](#tradingschedulesresponse)


### BondBy
Метод получения списка облигаций

- Тело запроса — [InstrumentRequest](#instrumentrequest)

- Тело ответа — [BondResponse](#bondresponse)


### Bonds
Метод получения облигации по её идентификатору

- Тело запроса — [InstrumentsRequest](#instrumentsrequest)

- Тело ответа — [BondsResponse](#bondsresponse)


### CurrencyBy
Метод получения списка валют

- Тело запроса — [InstrumentRequest](#instrumentrequest)

- Тело ответа — [CurrencyResponse](#currencyresponse)


### Currencies
Метод получения валюты по её идентификатору

- Тело запроса — [InstrumentsRequest](#instrumentsrequest)

- Тело ответа — [CurrenciesResponse](#currenciesresponse)


### EtfBy
Метод получения списка инвестиционных фондов

- Тело запроса — [InstrumentRequest](#instrumentrequest)

- Тело ответа — [EtfResponse](#etfresponse)


### Etfs
Метод получения инвестиционного фонда по его идентификатору

- Тело запроса — [InstrumentsRequest](#instrumentsrequest)

- Тело ответа — [EtfsResponse](#etfsresponse)


### FutureBy
Метод получения списка фьючерсов

- Тело запроса — [InstrumentRequest](#instrumentrequest)

- Тело ответа — [FutureResponse](#futureresponse)


### Futures
Метод получения фьючерса по его идентификатору

- Тело запроса — [InstrumentsRequest](#instrumentsrequest)

- Тело ответа — [FuturesResponse](#futuresresponse)


### StockBy
Метод получения списка акций

- Тело запроса — [InstrumentRequest](#instrumentrequest)

- Тело ответа — [StockResponse](#stockresponse)


### Stocks
Метод получения акции по её идентификатору

- Тело запроса — [InstrumentsRequest](#instrumentsrequest)

- Тело ответа — [StocksResponse](#stocksresponse)


### GetAccruedInterests
Метод получения календаря выплат купонов по облигациям

- Тело запроса — [GetAccruedInterestsRequest](#getaccruedinterestsrequest)

- Тело ответа — [GetAccruedInterestsResponse](#getaccruedinterestsresponse)


### GetFuturesMargin
Метод получения размера гарантийного обеспечения по фьючерсам

- Тело запроса — [GetFuturesMarginRequest](#getfuturesmarginrequest)

- Тело ответа — [GetFuturesMarginResponse](#getfuturesmarginresponse)

 <!-- range .Methods -->
 <!-- range .Services -->

##Сообщения методов



### TradingSchedulesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| exchange |  [string](#string) | Наименование биржи или расчетного календаря. </br>Если не передаётся, возвращается информация по всем доступным торговым площадкам |
| from |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Начало периода по часовому поясу UTC |
| to |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Окончание периода по часовому поясу UTC |
 <!-- end Fields -->
 <!-- end HasFields -->


### TradingSchedulesResponse



| Field | Type | Description |
| ----- | ---- | ----------- |
| exchanges | Массив объектов [TradingSchedule](#tradingschedule) | Список торговых площадок и режимов торгов |
 <!-- end Fields -->
 <!-- end HasFields -->


### TradingSchedule
Данные по торговой площадке


| Field | Type | Description |
| ----- | ---- | ----------- |
| exchange |  [string](#string) | Наименование торговой площадки |
| days | Массив объектов [TradingDay](#tradingday) | Массив с торговыми и неторговыми днями |
 <!-- end Fields -->
 <!-- end HasFields -->


### TradingDay
Информация о времени торгов


| Field | Type | Description |
| ----- | ---- | ----------- |
| date |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата |
| is_trading_day |  [bool](#bool) | Признак торгового дня на бирже |
| start_time |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Время начала торгов по часовому поясу UTC |
| end_time |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Время окончания торгов по часовому поясу UTC |
| market_order_start_time |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Время начала подачи заявки по часовому поясу UTC |
| market_order_end_time |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Время окончания подачи заявки по часовому поясу UTC |
 <!-- end Fields -->
 <!-- end HasFields -->


### InstrumentRequest
Запрос получения инструмента по идентификатору


| Field | Type | Description |
| ----- | ---- | ----------- |
| id_type |  [InstrumentIdType](#instrumentidtype) | Тип идентификатора инструмента. Возможные значения: figi, ticker, isin. Подробнее об идентификации инструментов: [Идентификация инструментов](https://tinkoffcreditsystems.github.io/invest-openapi/faq_identification/) |
| class_code |  [string](#string) | Идентификатор class_code. Обязателен при id_type = ticker |
| id |  [string](#string) | Идентификатор запрашиваемого инструмента |
 <!-- end Fields -->
 <!-- end HasFields -->


### InstrumentsRequest
Запрос получения инструментов


| Field | Type | Description |
| ----- | ---- | ----------- |
| instrument_status |  [InstrumentStatus](#instrumentstatus) | Статус запрашиваемых инструментов. Возможные значения: [InstrumentStatus](#instrumentstatus) |
 <!-- end Fields -->
 <!-- end HasFields -->


### BondResponse
Информация об облигации


| Field | Type | Description |
| ----- | ---- | ----------- |
| instrument |  [Bond](#bond) | Информация об облигации |
 <!-- end Fields -->
 <!-- end HasFields -->


### BondsResponse
Список облигаций


| Field | Type | Description |
| ----- | ---- | ----------- |
| instruments | Массив объектов [Bond](#bond) | Массив облигаций |
 <!-- end Fields -->
 <!-- end HasFields -->


### CurrencyResponse
Данные по валюте


| Field | Type | Description |
| ----- | ---- | ----------- |
| instrument |  [Currency](#currency) | Информация о валюте |
 <!-- end Fields -->
 <!-- end HasFields -->


### CurrenciesResponse
Данные по валютам


| Field | Type | Description |
| ----- | ---- | ----------- |
| instruments | Массив объектов [Currency](#currency) | Массив валют |
 <!-- end Fields -->
 <!-- end HasFields -->


### EtfResponse
Данные по фонду


| Field | Type | Description |
| ----- | ---- | ----------- |
| instrument |  [Etf](#etf) | Информация о фонде |
 <!-- end Fields -->
 <!-- end HasFields -->


### EtfsResponse
Данные по фондам


| Field | Type | Description |
| ----- | ---- | ----------- |
| instruments | Массив объектов [Etf](#etf) | Массив фондов |
 <!-- end Fields -->
 <!-- end HasFields -->


### FutureResponse
Данные по фьючерсу


| Field | Type | Description |
| ----- | ---- | ----------- |
| instrument |  [Future](#future) | Информация о фьючерсу |
 <!-- end Fields -->
 <!-- end HasFields -->


### FuturesResponse
Данные по фьючерсам


| Field | Type | Description |
| ----- | ---- | ----------- |
| instruments | Массив объектов [Future](#future) | Массив фьючерсов |
 <!-- end Fields -->
 <!-- end HasFields -->


### StockResponse
Данные по акции


| Field | Type | Description |
| ----- | ---- | ----------- |
| instrument |  [Stock](#stock) | Информация об акции |
 <!-- end Fields -->
 <!-- end HasFields -->


### StocksResponse
Данные по акциям


| Field | Type | Description |
| ----- | ---- | ----------- |
| instruments | Массив объектов [Stock](#stock) | Массив акций |
 <!-- end Fields -->
 <!-- end HasFields -->


### Bond
Объект передачи информации об облигации.


| Field | Type | Description |
| ----- | ---- | ----------- |
| figi |  [string](#string) | Figi-идентификатор инструмента. |
| ticker |  [string](#string) | Тикер инструмента. |
| class_code |  [string](#string) | Класс-код (секция торгов). |
| isin |  [string](#string) | Isin-идентификатор инструмента. |
| lot |  [int32](#int32) | Лотность инструмента. Возможно совершение операций только на количества ценной бумаги, кратные параметру *lot*. Подробнее: [лот](/doctest/glossary#lot) |
| currency |  [string](#string) | Валюта расчётов. |
| klong |  [double](#double) | Коэффициент ставки риска длинной позиции по инструменту. |
| kshort |  [double](#double) | Коэффициент ставки риска короткой позиции по инструменту. |
| dlong |  [double](#double) | Ставка риска минимальной маржи в лонг. Подробнее: [ставка риска в лонг](https://help.tinkoff.ru/margin-trade/long/risk-rate/) |
| dshort |  [double](#double) | Ставка риска минимальной маржи в шорт. Подробнее: [ставка риска в шорт](https://help.tinkoff.ru/margin-trade/short/risk-rate/) |
| dlong_min |  [double](#double) | Ставка риска начальной маржи в лонг. Подробнее: [ставка риска в лонг](https://help.tinkoff.ru/margin-trade/long/risk-rate/) |
| dshort_min |  [double](#double) | Ставка риска начальной маржи в шорт. Подробнее: [ставка риска в шорт](https://help.tinkoff.ru/margin-trade/short/risk-rate/) |
| short_enabled_flag |  [bool](#bool) | Признак доступности для операций в шорт. |
| name |  [string](#string) | Название инструмента. |
| exchange |  [string](#string) | Торговая площадка. |
| coupon_quantity_per_year |  [int32](#int32) | Количество выплат по купонам в год |
| maturity_date |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата погашения облигации в часовом поясе UTC |
| nominal |  [MoneyValue](#moneyvalue) | Номинал облигации |
| state_reg_date |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата выпуска облигации в часовом поясе UTC |
| placement_date |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата размещения в часовом поясе UTC |
| placement_price |  [MoneyValue](#moneyvalue) | Цена размещения |
| coupon_period_base |  [string](#string) | Периодичность выплаты купонов |
| aci_value |  [MoneyValue](#moneyvalue) | Значение НКД (накопленного купонного дохода) на дату |
| country_of_risk |  [string](#string) | Код страны эмитента |
| country_of_risk_name |  [string](#string) | Наименование страны эмитента |
| sector |  [string](#string) | Сектор экономики |
| issue_kind |  [string](#string) | Форма выпуска. Возможные значения: </br>**documentary** — документарная; </br>**non_documentary** — бездокументарная. |
| issue_size |  [int64](#int64) | Размер выпуска. |
| issue_size_plan |  [int64](#int64) | Плановый размер выпуска. |
| trading_status |  [SecurityTradingStatus](#securitytradingstatus) | Текущий режим торгов инструмента. |
| otc_flag |  [bool](#bool) | Признак внебиржевой ценной бумаги. |
| buy_available_flag |  [bool](#bool) | Признак доступности для покупки. |
| sell_available_flag |  [bool](#bool) | Признак доступности для продажи. |
 <!-- end Fields -->
 <!-- end HasFields -->


### Currency
Объект передачи информации о валюте.


| Field | Type | Description |
| ----- | ---- | ----------- |
| figi |  [string](#string) | Figi-идентификатор инструмента. |
| ticker |  [string](#string) | Тикер инструмента. |
| class_code |  [string](#string) | Класс-код (секция торгов). |
| isin |  [string](#string) | Isin-идентификатор инструмента. |
| lot |  [int32](#int32) | Лотность инструмента. Возможно совершение операций только на количества ценной бумаги, кратные параметру *lot*. Подробнее: [лот](/doctest/glossary#lot) |
| currency |  [string](#string) | Валюта расчётов. |
| klong |  [double](#double) | Коэффициент ставки риска длинной позиции по инструменту. |
| kshort |  [double](#double) | Коэффициент ставки риска короткой позиции по инструменту. |
| dlong |  [double](#double) | Ставка риска минимальной маржи в лонг. Подробнее: [ставка риска в лонг](https://help.tinkoff.ru/margin-trade/long/risk-rate/) |
| dshort |  [double](#double) | Ставка риска минимальной маржи в шорт. Подробнее: [ставка риска в шорт](https://help.tinkoff.ru/margin-trade/short/risk-rate/) |
| dlong_min |  [double](#double) | Ставка риска начальной маржи в лонг. Подробнее: [ставка риска в лонг](https://help.tinkoff.ru/margin-trade/long/risk-rate/) |
| dshort_min |  [double](#double) | Ставка риска начальной маржи в шорт. Подробнее: [ставка риска в шорт](https://help.tinkoff.ru/margin-trade/short/risk-rate/) |
| short_enabled_flag |  [bool](#bool) | Признак доступности для операций в шорт. |
| name |  [string](#string) | Название инструмента. |
| exchange |  [string](#string) | Торговая площадка. |
| nominal |  [MoneyValue](#moneyvalue) | Номинал. |
| country_of_risk |  [string](#string) | Код страны эмитента. |
| country_of_risk_name |  [string](#string) | Наименование страны эмитента. |
| trading_status |  [SecurityTradingStatus](#securitytradingstatus) | Текущий режим торгов инструмента. |
| otc_flag |  [bool](#bool) | Признак внебиржевой ценной бумаги. |
| buy_available_flag |  [bool](#bool) | Признак доступности для покупки. |
| sell_available_flag |  [bool](#bool) | Признак доступности для продажи. |
| iso_currency_name |  [string](#string) | Строковый ISO-код валюты. |
 <!-- end Fields -->
 <!-- end HasFields -->


### Etf
Объект передачи информации об инвестиционном фонде.


| Field | Type | Description |
| ----- | ---- | ----------- |
| figi |  [string](#string) | Figi-идентификатор инструмента. |
| ticker |  [string](#string) | Тикер инструмента. |
| class_code |  [string](#string) | Класс-код (секция торгов). |
| isin |  [string](#string) | Isin-идентификатор инструмента. |
| lot |  [int32](#int32) | Лотность инструмента. Возможно совершение операций только на количества ценной бумаги, кратные параметру *lot*. Подробнее: [лот](/doctest/glossary#lot) |
| currency |  [string](#string) | Валюта расчётов. |
| klong |  [double](#double) | Коэффициент ставки риска длинной позиции по инструменту. |
| kshort |  [double](#double) | Коэффициент ставки риска короткой позиции по инструменту. |
| dlong |  [double](#double) | Ставка риска минимальной маржи в лонг. Подробнее: [ставка риска в лонг](https://help.tinkoff.ru/margin-trade/long/risk-rate/) |
| dshort |  [double](#double) | Ставка риска минимальной маржи в шорт. Подробнее: [ставка риска в шорт](https://help.tinkoff.ru/margin-trade/short/risk-rate/) |
| dlong_min |  [double](#double) | Ставка риска начальной маржи в лонг. Подробнее: [ставка риска в лонг](https://help.tinkoff.ru/margin-trade/long/risk-rate/) |
| dshort_min |  [double](#double) | Ставка риска начальной маржи в шорт. Подробнее: [ставка риска в шорт](https://help.tinkoff.ru/margin-trade/short/risk-rate/) |
| short_enabled_flag |  [bool](#bool) | Признак доступности для операций в шорт. |
| name |  [string](#string) | Название инструмента. |
| exchange |  [string](#string) | Торговая площадка. |
| fixed_commission |  [double](#double) | Размер фиксированной комиссии фонда. |
| focus_type |  [string](#string) | Возможные значения: </br>**equity** — акции;</br>**fixed_income** — облигации;</br>**mixed_allocation** — смешанный;</br>**money_market** — денежный рынок;</br>**real_estate** — недвижимость;</br>**commodity** — товары;</br>**specialty** — специальный;</br>**private_equity** — private equity;</br>**alternative_investment** — альтернативные инвестиции. |
| released_date |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата выпуска в часовом поясе UTC. |
| num_shares |  [double](#double) | Количество акций фонда в обращении. |
| country_of_risk |  [string](#string) | Код страны эмитента. |
| country_of_risk_name |  [string](#string) | Наименование страны эмитента. |
| sector |  [string](#string) | Сектор экономики. |
| rebalancing_freq |  [string](#string) | Частота ребалансировки. |
| trading_status |  [SecurityTradingStatus](#securitytradingstatus) | Текущий режим торгов инструмента. |
| otc_flag |  [bool](#bool) | Признак внебиржевой ценной бумаги. |
| buy_available_flag |  [bool](#bool) | Признак доступности для покупки. |
| sell_available_flag |  [bool](#bool) | Признак доступности для продажи. |
 <!-- end Fields -->
 <!-- end HasFields -->


### Future
Объект передачи информации о фьючерсе.


| Field | Type | Description |
| ----- | ---- | ----------- |
| figi |  [string](#string) | Figi-идентификатор инструмента. |
| ticker |  [string](#string) | Тикер инструмента |
| class_code |  [string](#string) | Класс-код (секция торгов). |
| lot |  [int32](#int32) | Лотность инструмента. Возможно совершение операций только на количества ценной бумаги, кратные параметру *lot*. Подробнее: [лот](/doctest/glossary#lot) |
| currency |  [string](#string) | Валюта расчётов. |
| klong |  [double](#double) | Коэффициент ставки риска длинной позиции по клиенту. |
| kshort |  [double](#double) | Коэффициент ставки риска короткой позиции по клиенту. |
| dlong |  [double](#double) | Ставка риска минимальной маржи в лонг. Подробнее: [ставка риска в лонг](https://help.tinkoff.ru/margin-trade/long/risk-rate/) |
| dshort |  [double](#double) | Ставка риска минимальной маржи в шорт. Подробнее: [ставка риска в шорт](https://help.tinkoff.ru/margin-trade/short/risk-rate/) |
| dlong_min |  [double](#double) | Ставка риска начальной маржи в лонг. Подробнее: [ставка риска в лонг](https://help.tinkoff.ru/margin-trade/long/risk-rate/) |
| dshort_min |  [double](#double) | Ставка риска начальной маржи в шорт. Подробнее: [ставка риска в шорт](https://help.tinkoff.ru/margin-trade/short/risk-rate/) |
| short_enabled_flag |  [bool](#bool) | Признак доступности для операций шорт. |
| name |  [string](#string) | Название инструмента. |
| exchange |  [string](#string) | Торговая площадка. |
| first_trade_date |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата начала обращения контракта в часовом поясе UTC. |
| last_trade_date |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата в часовом поясе UTC, до которой возможно проведение операций с фьючерсом. |
| futures_type |  [string](#string) | Тип фьючерса. Возможные значения: </br>**physical_delivery** — физические поставки; </br>**cash_settlement** — денежный эквивалент. |
| asset_type |  [string](#string) | Тип актива. Возможные значения: </br>**commodity** — товар; </br>**currency** — валюта; </br>**security** — ценная бумага; </br>**index** — индекс. |
| basic_asset |  [string](#string) | Основной актив. |
| basic_asset_size |  [double](#double) | Размер основного актива. |
| country_of_risk |  [string](#string) | Код страны эмитента. |
| country_of_risk_name |  [string](#string) | Наименование страны эмитента. |
| sector |  [string](#string) | Сектор экономики. |
| expiration_date |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата истечения срока. |
| trading_status |  [SecurityTradingStatus](#securitytradingstatus) | Текущий режим торгов инструмента. |
| otc_flag |  [bool](#bool) | Признак внебиржевой ценной бумаги. |
| buy_available_flag |  [bool](#bool) | Признак доступности для покупки. |
| sell_available_flag |  [bool](#bool) | Признак доступности для продажи. |
 <!-- end Fields -->
 <!-- end HasFields -->


### Stock
Объект передачи информации об акции.


| Field | Type | Description |
| ----- | ---- | ----------- |
| figi |  [string](#string) | Figi-идентификатор инструмента. |
| ticker |  [string](#string) | Тикер инструмента. |
| class_code |  [string](#string) | Класс-код (секция торгов). |
| isin |  [string](#string) | Isin-идентификатор инструмента. |
| lot |  [int32](#int32) | Лотность инструмента. Возможно совершение операций только на количества ценной бумаги, кратные параметру *lot*. Подробнее: [лот](/doctest/glossary#lot) |
| currency |  [string](#string) | Валюта расчётов. |
| klong |  [double](#double) | Коэффициент ставки риска длинной позиции по инструменту. |
| kshort |  [double](#double) | Коэффициент ставки риска короткой позиции по инструменту. |
| dlong |  [double](#double) | Ставка риска минимальной маржи в лонг. Подробнее: [ставка риска в лонг](https://help.tinkoff.ru/margin-trade/long/risk-rate/) |
| dshort |  [double](#double) | Ставка риска минимальной маржи в шорт. Подробнее: [ставка риска в шорт](https://help.tinkoff.ru/margin-trade/short/risk-rate/) |
| dlong_min |  [double](#double) | Ставка риска начальной маржи в лонг. Подробнее: [ставка риска в лонг](https://help.tinkoff.ru/margin-trade/long/risk-rate/) |
| dshort_min |  [double](#double) | Ставка риска начальной маржи в шорт. Подробнее: [ставка риска в шорт](https://help.tinkoff.ru/margin-trade/short/risk-rate/) |
| short_enabled_flag |  [bool](#bool) | Признак доступности для операций в шорт. |
| name |  [string](#string) | Название инструмента. |
| exchange |  [string](#string) | Торговая площадка. |
| ipo_date |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата IPO акции в часовом поясе UTC. |
| issue_size |  [int64](#int64) | Размер выпуска. |
| country_of_risk |  [string](#string) | Код страны эмитента. |
| country_of_risk_name |  [string](#string) | Наименование страны эмитента. |
| sector |  [string](#string) | Сектор экономики. |
| issue_size_plan |  [int64](#int64) | Плановый размер выпуска. |
| nominal |  [MoneyValue](#moneyvalue) | Номинал. |
| trading_status |  [SecurityTradingStatus](#securitytradingstatus) | Текущий режим торгов инструмента. |
| otc_flag |  [bool](#bool) | Признак внебиржевой ценной бумаги. |
| buy_available_flag |  [bool](#bool) | Признак доступности для покупки. |
| sell_available_flag |  [bool](#bool) | Признак доступности для продажи. |
 <!-- end Fields -->
 <!-- end HasFields -->


### GetAccruedInterestsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| figi |  [string](#string) | Figi-идентификатор инструмента |
| from |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Начало запрашиваемого периода в часовом поясе UTC. |
| to |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Окончание запрашиваемого периода в часовом поясе UTC |
 <!-- end Fields -->
 <!-- end HasFields -->


### GetAccruedInterestsResponse



| Field | Type | Description |
| ----- | ---- | ----------- |
| accrued_interests | Массив объектов [AccruedInterest](#accruedinterest) | Массив операций начисления купонов |
 <!-- end Fields -->
 <!-- end HasFields -->


### AccruedInterest
Операция начисления купонов


| Field | Type | Description |
| ----- | ---- | ----------- |
| date |  [google.protobuf.Timestamp](#googleprotobuftimestamp) | Дата и время выплаты в часовом поясе UTC |
| value |  [Quotation](#quotation) | Величина выплаты |
| value_percent |  [float](#float) | Величина выплаты в процентах от номинала |
| nominal |  [Quotation](#quotation) | Номинал облигации |
 <!-- end Fields -->
 <!-- end HasFields -->


### GetFuturesMarginRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| figi |  [string](#string) | Идентификатор инструмента |
 <!-- end Fields -->
 <!-- end HasFields -->


### GetFuturesMarginResponse



| Field | Type | Description |
| ----- | ---- | ----------- |
| initial_margin_on_buy |  [MoneyValue](#moneyvalue) | Гарантийное обеспечение при покупке |
| initial_margin_on_sell |  [MoneyValue](#moneyvalue) | Гарантийное обеспечение при продаже |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

## Enums


### InstrumentIdType
Тип идентификатора инструмента. Подробнее об идентификации инструментов: [Идентификация инструментов](https://tinkoffcreditsystems.github.io/invest-openapi/faq_identification/)

| Name | Number | Description |
| ---- | ------ | ----------- |
| INSTRUMENT_ID_UNSPECIFIED | 0 | Значение не определено. |
| INSTRUMENT_ID_TYPE_FIGI | 1 | Figi. |
| INSTRUMENT_ID_TYPE_TICKER | 2 | Ticker. |
| INSTRUMENT_ID_TYPE_ISIN | 3 | Isin. |




### InstrumentStatus
Статус запрашиваемых инструментов.

| Name | Number | Description |
| ---- | ------ | ----------- |
| INSTRUMENT_STATUS_UNSPECIFIED | 0 | Значение не определено. |
| INSTRUMENT_STATUS_BASE | 1 | Базовый список инструментов (по умолчанию). |
| INSTRUMENT_STATUS_QUALIFIED | 2 | Список инструментов, доступный только квалифицированным инвесторам. |
| INSTRUMENT_STATUS_ALL | 3 | Список всех инструментов. |


 <!-- range .Enums -->
 <!-- range HasServices -->
 <!-- range .Files -->

## Нестандартные типы данных

### MoneyValue
Денежная сумма в определенной валюте

| Field | Type | Description |
| ----- | ---- | ----------- |
| currency |  [string](#string) | Строковый ISO-код валюты |
| units |  [int64](#int64) | Целая часть суммы, может быть отрицательным числом |
| nano |  [int32](#int32) | Дробная часть суммы, может быть отрицательным числом |


### Quotation
Котировка - денежная сумма без указания валюты

| Field | Type | Description |
| ----- | ---- | ----------- |
| units |  [int64](#int64) | Целая часть суммы, может быть отрицательным числом |
| nano |  [int32](#int32) | Дробная часть суммы, может быть отрицательным числом |
