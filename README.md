# teste-padrao-commit

Passos Instalação
- npm i commitizen @digitalroute/cz-conventional-changelog-for-jira
- npm i simple-git-hooks --save-dev
- npm i prettier --save-dev
- npm i lint-staged --save-dev
- Configurando simple-git-hooks
```json
"simple-git-hooks": {
    "pre-commit": "lint-staged && git add .",
    "prepare-commit-msg": "exec < /dev/tty && git cz --hook || true",
    "commit-msg": "commitlint -E HUSKY_GIT_PARAMS",
    "pre-push": ""
},
```
- npx simple-git-hooks
