# Gitflow c веткой beta

## Постоянные ветки

- `main` — только стабильные релизы.
- `beta` — кандидат на релиз и тестовый контур.
- `develop` — интеграция текущей разработки.

## Временные ветки

- `feature/*` — от `develop`, обратно в `develop`.
- `release/*` — от `develop`, после стабилизации в `beta`.
- `hotfix/*` — от `main`, затем в `main`, `beta` и `develop`.

## Рекомендуемый цикл

1. Создать `feature/*` от `develop`.
2. Слить `feature/*` в `develop`.
3. Когда нужен общий тестовый прогон, обновить `beta` из `develop`.
4. После приемки влить `beta` в `main`.
5. Если во время релиза были исправления, вернуть их обратно в `develop`.

## Базовые команды

```bash
git checkout develop
git checkout -b feature/my-task

git checkout beta
git merge --no-ff develop

git checkout main
git merge --no-ff beta
```
