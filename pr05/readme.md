# Praktikum 05 - ANTLR & Visitor Pattern | Äquivalenzklassen & Grenzwerte | Mocking

## 1. [ANTLR & Visitor Pattern](a01.md)



## 2. [Äquivalenzklassen & Grenzwerte - Cycle Chronicles](a02.md)

### <u>A2.1 Analyse der Äquivalenzklassen & Grenzwerte</u>

#### __Äquivalenzklassen:__


| Input | valid EC | invalid EC |
|-|-|-|
bicycleType | vEC1 = { RACE , SINGLE_SPEED , FIXIE } | iEC1.1 = GRAVEL <br> iEC1.2 = EBIKE
Customer.pendingOrder | vEC2 = { false } | iEC2 = { true }
Shop.pendingOrders | vEC3 = [ 0 , 4 ] | iEC3 = [ 5 , $\infty$ ]

#### __Grenzwerte:__

|Input|valid EC|invalid EC|
|-|-|-|
Shop.pendingOrders | vEC3b = 0<br> vEC3a = 4  | iEC3a = 5 <br> iEC3b = 6 

<br>

- xECYa = above
- xECYb = below

<br>

$\rightarrow$ iEC3 wird durch iEC3a repräsentiert


#### __Test:__

|Test Case #|1|2|3|4|5|6|7|8|
|-|-|-|-|-|-|-|-|-|
Tested EC #|vECs 1, 2, 3|iEC1.1|iEC1.2|iEC2|vEC3b|vEC3a|iEC3b|iEC3a
bicycleType|__RACE__|__GRAVEL__|__EBIKE__|FIXIE|FIXIE|FIXIE|FIXIE|FIXIE
Customer.pendingOrder|__false__|false|false|__true__|false|false|false|false
Shop.pendingOrders|__1__|2|3|4|__0__|__4__|__5__|__6__
Expected Result|true|false|false|false|true|true|false|Exception


## 3. [Mocking](a03.md)