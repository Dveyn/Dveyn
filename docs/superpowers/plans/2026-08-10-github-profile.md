# GitHub Profile (hiring-first) Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Оформить GitHub-профиль Dveyn под найм (HR/тимлиды): README + bio/homepage + descriptions + pinned.

**Architecture:** Один публичный profile-repo `Dveyn/Dveyn` хранит README профиля. Meta профиля и descriptions репозиториев обновляются через GitHub API/`gh`. Pinned задаются GraphQL mutation `updateUserRepositories` / `pinRepository` (или UI-fallback). Визуальная проверка на `https://github.com/Dveyn`.

**Tech Stack:** Markdown README, shields.io badges, github-readme-stats, GitHub CLI (`gh`), GitHub REST + GraphQL API.

**Spec:** `docs/superpowers/specs/2026-08-10-github-profile-design.md`

## Global Constraints

- Язык профиля: только русский
- Опыт везде: `5 лет` (никогда `3+`)
- Позиционирование: Middle+ / Senior-ready Frontend
- Тон: hiring-first, без waving capsule-render, без стены badges
- Контакты: `i@ananievds.ru`, Telegram `@dveyn`, сайт `https://ananievds.ru`
- Не трогать приватные репозитории (кроме отсутствия в pin)
- Не пушить без явной команды пользователя (локальные коммиты ок; `git push` / публичные API-изменения meta - только после согласия на выполнение плана)
- В текстах для пользователя не использовать длинное тире «—», только дефис «-»

---

## File map

| Файл / ресурс | Ответственность |
|---------------|-----------------|
| `README.md` | Profile README на github.com/Dveyn |
| GitHub user profile (`bio`, `blog`) | Шапка профиля |
| Descriptions 7 public repos | Карточки в profile/pins |
| Pinned items (6) | Закрепы на главной профиля |
| Spec/plan в `docs/superpowers/` | Документация процесса (уже есть) |

---

### Task 1: Переписать profile README

**Files:**
- Modify: `README.md` (полная замена содержимого)
- Spec reference: `docs/superpowers/specs/2026-08-10-github-profile-design.md`

**Interfaces:**
- Consumes: утверждённые тексты из spec (5 лет, Middle+, кейсы, контакты)
- Produces: финальный `README.md`, готовый к пушу в `main`

- [ ] **Step 1: Заменить `README.md` целиком на содержимое ниже**

```markdown
<h1 align="center">Дмитрий · Frontend Developer</h1>

<p align="center">
  <b>Middle+ · React · Next.js · TypeScript</b>
</p>

<p align="center">
  <a href="https://ananievds.ru"><img src="https://img.shields.io/badge/сайт-ananievds.ru-0F172A?style=flat-square" alt="сайт" /></a>
  <a href="mailto:i@ananievds.ru"><img src="https://img.shields.io/badge/email-i%40ananievds.ru-1E293B?style=flat-square&logo=gmail&logoColor=EA4335" alt="email" /></a>
  <a href="https://t.me/dveyn"><img src="https://img.shields.io/badge/Telegram-%40dveyn-1E293B?style=flat-square&logo=telegram&logoColor=26A5E4" alt="telegram" /></a>
</p>

## Snapshot

- `5 лет` коммерческой frontend-разработки
- Основной стек: `React`, `Next.js`, `TypeScript`
- Фокус: интерфейсы, удобные пользователю и удобные в поддержке
- Открыт к сильным командам и интересным продуктам

## Стек

<p>
  <img src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB" alt="React" />
  <img src="https://img.shields.io/badge/Next.js-0F172A?style=flat-square&logo=nextdotjs&logoColor=ffffff" alt="Next.js" />
  <img src="https://img.shields.io/badge/TypeScript-1E293B?style=flat-square&logo=typescript&logoColor=3178C6" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Vite-1E293B?style=flat-square&logo=vite&logoColor=646CFF" alt="Vite" />
  <img src="https://img.shields.io/badge/Tailwind_CSS-1E293B?style=flat-square&logo=tailwindcss&logoColor=38BDF8" alt="Tailwind CSS" />
  <img src="https://img.shields.io/badge/TanStack_Query-1E293B?style=flat-square&logo=reactquery&logoColor=FF4154" alt="TanStack Query" />
</p>

<p>
  <img src="https://img.shields.io/badge/Zustand-1E293B?style=flat-square" alt="Zustand" />
  <img src="https://img.shields.io/badge/Redux_Toolkit-1E293B?style=flat-square&logo=redux&logoColor=764ABC" alt="Redux Toolkit" />
  <img src="https://img.shields.io/badge/React_Hook_Form-1E293B?style=flat-square&logo=reacthookform&logoColor=EC5990" alt="React Hook Form" />
  <img src="https://img.shields.io/badge/Zod-1E293B?style=flat-square&logo=zod&logoColor=3E67B1" alt="Zod" />
  <img src="https://img.shields.io/badge/Framer_Motion-1E293B?style=flat-square&logo=framer&logoColor=0055FF" alt="Framer Motion" />
  <img src="https://img.shields.io/badge/ESLint-1E293B?style=flat-square&logo=eslint&logoColor=4B32C3" alt="ESLint" />
  <img src="https://img.shields.io/badge/Prettier-1E293B?style=flat-square&logo=prettier&logoColor=F7B93E" alt="Prettier" />
</p>

## Кейсы

| Проект | О чём |
|--------|--------|
| [scroll-cinema-demo](https://github.com/Dveyn/scroll-cinema-demo) | Scroll-driven анимации (GSAP/Lenis), практика UX/motion |
| [nextjs-lead-frontend](https://github.com/Dveyn/nextjs-lead-frontend) | Next.js / React / TypeScript: архитектура, git-flow, CI/CD |
| [products-admin-test](https://github.com/Dveyn/products-admin-test) | Тестовое Aiti Guru: admin UI на TypeScript |
| [ananievds.ru](https://ananievds.ru) | Личный сайт-портфолио |

## Как работаю

- Беру фичу от макета/ТЗ до релиза, не бросаю «на полпути»
- Держу код читаемым: компоненты, типы, понятные границы модулей
- Работаю с API, ошибками, loading-состояниями и формами без сюрпризов для пользователя
- Думаю про UX и перфоманс, а не только про «чтобы собралось»
- Комфортно в команде: ревью, договорённости, git-flow

## Контакты

- Email: [i@ananievds.ru](mailto:i@ananievds.ru)
- Telegram: [@dveyn](https://t.me/dveyn)
- Сайт: [ananievds.ru](https://ananievds.ru)

---

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=Dveyn&show_icons=true&theme=transparent&hide_border=true&title_color=0F172A&icon_color=2563EB&text_color=334155&bg_color=00000000" alt="GitHub stats" />
</p>

<p align="center">
  <b>Открыт к сильным frontend-командам и интересным продуктам.</b>
</p>
```

- [ ] **Step 2: Проверить, что в файле нет `3+` и нет `capsule-render`**

Run:

```bash
rg -n '3\+|capsule-render' README.md || true
```

Expected: пустой вывод (совпадений нет).

- [ ] **Step 3: Проверить, что есть `5 лет`**

Run:

```bash
rg -n '5 лет' README.md
```

Expected: минимум одна строка со Snapshot.

- [ ] **Step 4: Commit**

```bash
git add README.md
git commit -m "$(cat <<'EOF'
docs: rewrite profile README for hiring-first Middle+

EOF
)"
```

---

### Task 2: Обновить meta профиля (bio + homepage)

**Files:**
- Remote: GitHub user profile fields `bio`, `blog` (через API)

**Interfaces:**
- Consumes: тексты из spec
- Produces: обновлённая шапка на `https://github.com/Dveyn`

- [ ] **Step 1: Обновить bio и blog**

Run:

```bash
gh api user -X PATCH -f bio='Frontend · React / Next.js / TypeScript · Middle+ · открыт к сильным командам' -f blog='https://ananievds.ru'
```

Expected: JSON пользователя без ошибки.

- [ ] **Step 2: Проверить значения**

Run:

```bash
gh api user --jq '{bio,blog,name,login}'
```

Expected:

```json
{
  "bio": "Frontend · React / Next.js / TypeScript · Middle+ · открыт к сильным командам",
  "blog": "https://ananievds.ru",
  "name": "Дмитрий",
  "login": "Dveyn"
}
```

- [ ] **Step 3: Зафиксировать в локальном логе (коммит не нужен - remote-only)**

Если API вернул 403/401: остановиться и сообщить пользователю, что нужен scope `user` / повторный `gh auth refresh -s user`.

---

### Task 3: Обновить descriptions публичных репозиториев

**Files:**
- Remote: repo metadata для:
  - `Dveyn/scroll-cinema-demo`
  - `Dveyn/nextjs-lead-frontend`
  - `Dveyn/products-admin-test`
  - `Dveyn/my-sait-portfolio`
  - `Dveyn/middle.messenger.praktikum.yandex`
  - `Dveyn/AI-Scout`
  - `Dveyn/Dveyn`

**Interfaces:**
- Consumes: таблица descriptions из spec
- Produces: заполненные description на GitHub

- [ ] **Step 1: Применить descriptions**

Run (последовательно):

```bash
gh api repos/Dveyn/scroll-cinema-demo -X PATCH \
  -f description='Demo: scroll-driven анимации (WebP + GSAP/Lenis). Учебный / pet-проект'

gh api repos/Dveyn/nextjs-lead-frontend -X PATCH \
  -f description='Next.js / React / TypeScript: архитектура, git-flow, CI/CD'

gh api repos/Dveyn/products-admin-test -X PATCH \
  -f description='Тестовое Aiti Guru: admin UI на TypeScript'

gh api repos/Dveyn/my-sait-portfolio -X PATCH \
  -f description='Личный сайт-портфолио · ananievds.ru' \
  -f homepage='https://ananievds.ru'

gh api repos/Dveyn/middle.messenger.praktikum.yandex -X PATCH \
  -f description='Мессенджер на TypeScript (Яндекс Практикум)'

gh api repos/Dveyn/AI-Scout -X PATCH \
  -f description='MyAI: B2B-аутрич и AI-маркетинг (Scout + Office, Python)'

gh api repos/Dveyn/Dveyn -X PATCH \
  -f description='GitHub profile README'
```

Expected: каждый вызов возвращает JSON репозитория без ошибки.

- [ ] **Step 2: Сверить descriptions**

Run:

```bash
for r in scroll-cinema-demo nextjs-lead-frontend products-admin-test my-sait-portfolio middle.messenger.praktikum.yandex AI-Scout Dveyn; do
  echo "### $r"
  gh api "repos/Dveyn/$r" --jq '{description,homepage}'
done
```

Expected: descriptions совпадают со Step 1; у `my-sait-portfolio` homepage `https://ananievds.ru`.

---

### Task 4: Закрепить (pin) 6 репозиториев

**Files:**
- Remote: user pinned items

**Interfaces:**
- Consumes: порядок pin из spec
- Produces: 6 pinned на профиле

Порядок pin:
1. `scroll-cinema-demo`
2. `nextjs-lead-frontend`
3. `products-admin-test`
4. `my-sait-portfolio`
5. `middle.messenger.praktikum.yandex`
6. `AI-Scout`

- [ ] **Step 1: Получить node IDs репозиториев**

Run:

```bash
for r in scroll-cinema-demo nextjs-lead-frontend products-admin-test my-sait-portfolio middle.messenger.praktikum.yandex AI-Scout; do
  echo -n "$r "
  gh api "repos/Dveyn/$r" --jq .node_id
done
```

Expected: 6 строк `name + node_id`.

- [ ] **Step 2: Применить pinned через GraphQL**

Подставить `REPO_NODE_IDS` из Step 1 (массив из 6 ID) в mutation:

```bash
gh api graphql -f query='
mutation($ids:[ID!]!) {
  updateUserRepositories(input:{clientMutationId:"profile-pins",repositoryIds:$ids}) {
    clientMutationId
  }
}' -f ids='["ID1","ID2","ID3","ID4","ID5","ID6"]'
```

Если schema/mutation недоступна или ошибка имени поля, попробовать альтернативу:

```bash
gh api graphql -f query='
mutation {
  pinRepository(input:{repositoryId:"ID1"}) { clientMutationId }
}'
```

для каждого ID по очереди (макс. 6).

Если GraphQL недоступен из-за scopes: дать пользователю точный UI-путь:

1. Открыть https://github.com/Dveyn
2. Customize your pins
3. Выбрать 6 реп в порядке из списка выше
4. Save pins

- [ ] **Step 3: Проверить pinned**

Run:

```bash
gh api graphql -f query='
query {
  user(login:"Dveyn") {
    pinnedItems(first:6) {
      nodes {
        ... on Repository { name }
      }
    }
  }
}'
```

Expected: имена в порядке из списка pin (или тот же набор из 6).

---

### Task 5: Запушить README и финальная проверка профиля

**Files:**
- Push: `README.md` (+ уже закоммиченный spec/plan) в `origin/main`

**Interfaces:**
- Consumes: локальные коммиты Tasks 1 (+ plan commit)
- Produces: живой профиль на https://github.com/Dveyn

- [ ] **Step 1: Получить явное согласие пользователя на `git push`** (если ещё не дано в этом чате)

Без согласия - не пушить. Показать `git status` и список коммитов ahead of origin.

- [ ] **Step 2: Push**

```bash
git push -u origin HEAD
```

Expected: `main -> main` успешен.

- [ ] **Step 3: Проверить README на remote**

Run:

```bash
gh api repos/Dveyn/Dveyn/readme --jq .content | base64 -d | rg -n '5 лет|capsule-render|3\+'
```

Expected: есть `5 лет`, нет `capsule-render`, нет `3+`.

- [ ] **Step 4: Открыть профиль в браузере и сверить чеклист**

Чеклист:
- [ ] Hero: Дмитрий · Frontend Developer / Middle+
- [ ] Snapshot с 5 годами
- [ ] Стек компактный (2 ряда)
- [ ] Таблица кейсов + сайт
- [ ] Контакты рабочие
- [ ] Stats загружаются
- [ ] Bio и homepage в шапке верные
- [ ] 6 pinned видны

URL: https://github.com/Dveyn

- [ ] **Step 5: Сообщить пользователю итог** со ссылкой на профиль и списком сделанных remote-изменений.

---

## Self-review (plan vs spec)

| Spec requirement | Task |
|------------------|------|
| Rewrite README hiring-first | Task 1 |
| 5 years experience | Task 1 + verify |
| Remove waving/badge wall | Task 1 |
| Bio + homepage | Task 2 |
| Descriptions public repos | Task 3 |
| Pin 6 repos | Task 4 |
| Live profile verification | Task 5 |
| AI-Scout description | Task 3 (`MyAI: B2B-аутрич...`) |

Placeholders: none. GraphQL pin имеет UI-fallback без TBD.
