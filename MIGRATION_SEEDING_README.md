# News Service with TypeORM Migrations and Seeding

Цей проєкт було доробано згідно з технічними вимогами для додавання міграцій та seeding з використанням TypeORM.

## Що було додано

### 🔄 Міграції
- **Нова міграція**: `AddDeletedFieldAndRenameTitle1699000000002`
- Додає поле `deleted` (boolean, default: false) до таблиць `posts` та `users`
- Перейменовує колонку `title` на `header` у таблиці `posts`
- Додає оптимізовані індекси для покращення продуктивності

### 🌱 Seeding
- **Новий seeding скрипт**: `scripts/seedDatabase.ts`
- Створює стандартного користувача: `admin@example.com` (пароль: `password123`)
- Генерує 20 новин з використанням:
  - Faker.js для генерації контенту
  - JSONPlaceholder API як альтернативний джерело
- Автоматичні slug'и, теги, категорії та метадані

### 📊 Індекси для оптимізації
Додані індекси для колонок:
- `users.deleted`, `users.email`, `users.created_at`
- `posts.deleted`, `posts.header`, `posts.published_at`, `posts.views_count`, `posts.likes_count`, `posts.is_featured`

## 🚀 Запуск проєкту

### Повний запуск (production)
```bash
npm run start:app
```

### Розробка
```bash
npm run start:dev
```

### Тільки міграції
```bash
npm run typeorm:migration:run
```

### Тільки seeding
```bash
npm run load:demo-data
```

## 📋 Структура команд

- `npm run prod:client` - збірка клієнта
- `npm run prod:server` - збірка сервера  
- `npm run setup:db` - налаштування БД + seeding
- `npm run run:server` - запуск продакшн сервера

## 🔧 Зміни в API

### Переймений
- `title` → `header` у всіх POST ендпоінтах

### Додано
- `deleted` поле для soft delete функціональності
- Фільтрація видалених записів в усіх запитах

## 👤 Тестовий користувач
- **Email**: admin@example.com  
- **Пароль**: password123

## 📁 Нові файли
- `server/migrations/0000000000002-AddDeletedFieldAndRenameTitle.ts`
- `server/scripts/seedDatabase.ts`

Проєкт готовий до використання! 🎉
