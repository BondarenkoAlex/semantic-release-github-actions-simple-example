## Как пользоваться.

### Подготовка

1. Склонировать реп `git clone git@github.com:BondarenkoAlex/semantic-release-github-actions-simple-example.git`

1. Установить все зависимости `npm ci`

1. Добавить для `github` - [Personal access token (classic)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic)

   Разрешения должны быть как написано [тут](https://github.com/semantic-release/github?tab=readme-ov-file#github-authentication)

1. Добавить для `npm` - [Access token (classic)](https://docs.npmjs.com/creating-and-viewing-access-tokens#creating-access-tokens)

   Разрешение должно быть `Publish`

### Для публикации из локальной машины 

Запустить команду

`GH_TOKEN=<github_token> NPM_TOKEN=<npm_token> npx semantic-release --no-ci`

где `<github_token>` и `<npm_token>` строки, которые были сгенерированы в предыдущих пунктах соответственно

### Для публикации с помощью `github action (workflows)`

1. Надо дать разрешения `Workflow permissions`. 

   Для этого: `Your repo` → `Settings` tab  → `Actions` tab  → `General` subtab  → `Workflow permissions` → `Read and write permissions` check 

   Почитать можно [Modifying the permissions for the GITHUB_TOKEN](https://docs.github.com/ru/actions/security-guides/automatic-token-authentication#modifying-the-permissions-for-the-github_token)

1. Добавить `Secrets and variables`

   Перейти `Your repo` → `Settings` tab  → `Secrets and variables` → `Actions` → `Repository secrets` → `New repository secret`

   Добавить два ключа:

   - Name: `GH_TOKEN`; Secret: `<строка, которая была сгенерирована в предыдущих пунктах>`

   - Name: `NPM_TOKEN`; Secret: `<строка, которая была сгенерирована в предыдущих пунктах>`

1. Все. Делаем коммит (по [конвенции коммитов](https://www.conventionalcommits.org/ru/v1.0.0/)) и отправляем в репозиторий



