# Design: GitHub-профиль Dveyn (hiring-first)

Дата: 2026-08-10  
Аудитория: HR / тимлиды (найм)  
Позиционирование: Middle+ / Senior-ready Frontend  
Язык: русский  
Визуальный тон: современный tech-профиль (аккуратные badges + лёгкие stats, без перегруза)

## Цель

Сделать профиль [github.com/Dveyn](https://github.com/Dveyn) читаемым за 20 секунд: кто, уровень, стек, доказательства в коде, как связаться.

## Scope

Входит:
1. Переписать `README.md` в репозитории `Dveyn/Dveyn`
2. Обновить meta профиля: bio, homepage
3. Закрепить (pin) до 6 публичных репозиториев
4. Обновить descriptions выбранных публичных репозиториев

Не входит:
- Рефакторинг кода проектов
- Английская версия профиля
- Новые демо-репозитории с нуля
- Приватные коммерческие репозитории (содержимое не публикуем)

## Подход

Hiring-first README + лёгкий profile pack (bio / homepage / pins / descriptions).

## Структура README

Порядок блоков сверху вниз:

1. **Hero** - имя + роль
2. **Snapshot** - 4 факта для сканирования
3. **Стек** - 1–2 ряда badges, без дублей
4. **Кейсы** - 2–3 публичных проекта + сайт
5. **Как работаю** - 4–5 буллетов про ответственность Middle+
6. **Контакты** - email, Telegram, сайт
7. **Stats** - один компактный блок GitHub stats

Убрать из текущего README:
- waving capsule-render header/footer
- длинные секции «умею / специализация / экосистема» с повторами
- стену badges в 3+ секциях

## Тексты (утверждённые)

### GitHub bio

`Frontend · React / Next.js / TypeScript · Middle+ · открыт к сильным командам`

### Homepage

`https://ananievds.ru`

### Hero

- Заголовок: `Дмитрий · Frontend Developer`
- Подзаголовок: `Middle+ · React · Next.js · TypeScript`

### Snapshot

- `5 лет` коммерческой frontend-разработки
- Основной стек: `React`, `Next.js`, `TypeScript`
- Фокус: интерфейсы, которые удобны пользователю и удобны в поддержке
- Открыт к сильным командам и интересным продуктам

### Стек (badges)

React · Next.js · TypeScript · Vite · Tailwind · TanStack Query · Zustand · Redux Toolkit · React Hook Form · Zod · Framer Motion · ESLint/Prettier

### Кейсы

1. `scroll-cinema-demo` - scroll-driven анимации (GSAP/Lenis), практика UX/motion
2. `nextjs-lead-frontend` - Next/React/TS, архитектура, git-flow, CI/CD
3. `products-admin-test` - тестовое Aiti Guru: admin UI на TypeScript
4. Сайт: [ananievds.ru](https://ananievds.ru)

### Как работаю

- Беру фичу от макета/ТЗ до релиза, не бросаю «на полпути»
- Держу код читаемым: компоненты, типы, понятные границы модулей
- Работаю с API, ошибками, loading-состояниями и формами без сюрпризов для пользователя
- Думаю про UX и перфоманс, а не только про «чтобы собралось»
- Комфортно в команде: ревью, договорённости, git-flow

### Контакты

- Email: `i@ananievds.ru`
- Telegram: `@dveyn`
- Сайт: `ananievds.ru`

### Stats

Один блок GitHub stats (например github-readme-stats), без tropy/стены графиков.

## Pinned repositories

| # | Репозиторий | Роль в профиле |
|---|-------------|----------------|
| 1 | `scroll-cinema-demo` | свежий frontend / motion |
| 2 | `nextjs-lead-frontend` | Next + практика инженерии |
| 3 | `products-admin-test` | тестовое задание |
| 4 | `my-sait-portfolio` | визитка / сайт |
| 5 | `middle.messenger.praktikum.yandex` | TypeScript-проект |
| 6 | `AI-Scout` | шире стека (бонус) |

## Descriptions публичных реп

| Репозиторий | Description |
|-------------|-------------|
| `scroll-cinema-demo` | Demo: scroll-driven анимации (WebP + GSAP/Lenis). Учебный / pet-проект |
| `nextjs-lead-frontend` | Next.js / React / TypeScript: архитектура, git-flow, CI/CD |
| `products-admin-test` | Тестовое Aiti Guru: admin UI на TypeScript |
| `my-sait-portfolio` | Личный сайт-портфолио · ananievds.ru |
| `middle.messenger.praktikum.yandex` | Мессенджер на TypeScript (Яндекс Практикум) |
| `AI-Scout` | MyAI: B2B-аутрич и AI-маркетинг (Scout + Office, Python) |
| `Dveyn` | GitHub profile README |

## Критерии готовности

- README читается без скролла «стены» badges
- Везде указано `5 лет` опыта (не 3+)
- Bio + homepage обновлены
- 6 pinned выставлены
- Descriptions у pinned/публичных кейсов заполнены
- Профиль открывается на https://github.com/Dveyn без битых ссылок

## Риски

- Мало публичных коммерческих кейсов - компенсируем качеством описаний и ссылкой на сайт
- Pinning через API может потребовать GraphQL mutation - проверить права токена
- Pin API / token scopes могут ограничить обновление pinned - тогда дам точные шаги вручную в UI
