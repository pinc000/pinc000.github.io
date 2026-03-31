[<img _ngcontent-c2="" src="https://raw.githubusercontent.com/pinc000/pinc000.github.io/main/pinc000.png" width="100" height="100" style="background-color: transparent;">](https://pinc000.github.io)

[English ](ChangesLog.md)\|[ Chinese ](ChangesLog_ZH.md)\|[ Russian](ChangesLog_RU.md)

# API Changelog

## Ноябрь 2025 -- API для ставок

##### 1. <span>Функция</span> -- Новая версия API для ставок `/v4`. Новый API:
  + `/v4/bets/place`
  + `/v4/bets/special`
  + `/v4/bets/parlay`
  + `/v4/bets/teaser`

## Август 2025 – Линии API

##### 1. <span>УСТАРЕВАНИЕ</span> – Устаревание нескольких свойств в `v1/periods` endpoint. Свойства, которые будут удалены:
  + spreadDescription
  + moneylineDescription
  + totalDescription
  + team1TotalDescription
  + team2TotalDescription
  + spreadShortDescription
  + moneylineShortDescription
  + totalShortDescription
  + team1TotalShortDescription
  + team2TotalShortDescription


## Июль 2025 – Линии API

##### 1. <span>Нововведение</span> – Новая версия для получения коэффициентов – `v4/odds`, добавлена поддержка Buy/Sell рынков для Team Totals.

##### 2. <span>Нововведение</span> – Новая версия для получения коэффициентов экспрессов – `v4/odds/parlay`, добавлена поддержка Buy/Sell рынков для Team Totals.


