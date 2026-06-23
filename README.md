# Meta Launch Calculator

Калькулятор окупності та цільових метрик для запусків у Meta Ads.

## Що рахує
- Структуру повних витрат: бюджет + ПДВ + комісія агенції
- Кліки/трафік за поточним CPC
- Транзакції (кліки × CR) та дохід (× середній чек)
- Фактичну і допустиму CPA, ROAS, фактичну ДРР
- Два режими: від бюджету → результат, і від цілі → потрібний бюджет
- Експорт усіх вхідних даних і результатів у .xlsx (кнопка у блоці результатів) для імпорту в Google Sheets

## Локальний запуск
```
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload
```
Відкрити http://localhost:8000

Зупинити сервер: Ctrl+C.

## Railway
Залити репозиторій на GitHub і підключити до Railway. Збірка через Nixpacks,
старт-команда і порт беруться з railway.json / Procfile автоматично.

## Структура
- main.py — FastAPI-сервер, роздає статику
- static/index.html — увесь інтерфейс і логіка розрахунку (чистий JS, без бекенд-залежностей)
- static/vendor/xlsx.full.min.js — SheetJS локально, для експорту в .xlsx
