# teste-padrao-commit

Passos Instalação
- npm install commitizen @digitalroute/cz-conventional-changelog-for-jira
- npm install --save-dev husky
- npm i prettier --save-dev
- npm i lint-staged --save-dev
- Configurando husky
```json
"husky": {
        "hooks": {
            "pre-commit": "lint-staged && git add .",
            "prepare-commit-msg": "exec < /dev/tty && git cz --hook || true",
            "commit-msg": "commitlint -E HUSKY_GIT_PARAMS",
            "pre-push": "find . -type f -iname \\*.rej -delete"
        }
    },
```
