# FitFlow — Данные для анализа

## О продукте
FitFlow — мобильное приложение для фитнеса по подписке. Пользователи получают доступ к видео-тренировкам (йога, HIIT, силовые, кардио, медитации) с профессиональными тренерами.

Платформы: iOS, Android, Web
Монетизация: подписка (trial → monthly → annual)
Рынок: Россия
Период данных: январь — декабрь 2025

## Файлы

### fitflow_events.csv
События продукта. Колонки:
- `event_id` — уникальный ID события
- `user_id` — ID пользователя (формат U00001)
- `event_name` — название события:
  - `registration` — регистрация
  - `onboarding_step_1_profile` — заполнение профиля
  - `onboarding_step_2_goals` — выбор целей
  - `onboarding_complete` — завершение онбординга
  - `subscription_started` — начало подписки
  - `workout_started` — начало тренировки
  - `subscription_cancelled` — отмена подписки
- `event_timestamp` — время события (ISO 8601)
- `platform` — платформа (ios / android / web)
- `properties` — JSON с дополнительными данными

### fitflow_feedback.csv
Обратная связь пользователей. Колонки:
- `feedback_id` — ID отзыва
- `user_id` — ID пользователя
- `feedback_date` — дата отзыва
- `channel` — канал (app_store_review, google_play_review, support_ticket, nps_survey, in_app_feedback)
- `rating` — оценка (1-5)
- `text` — текст отзыва на русском языке
- `platform` — платформа

## Ключевые метрики для анализа
- Retention (Day 1, Day 7, Day 30)
- Конверсия в завершение онбординга
- Конверсия trial → paid
- Churn rate по когортам
- Частота тренировок (workouts per week)
- NPS / средний рейтинг
