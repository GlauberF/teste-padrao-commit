# teste-padrao-commit

Passos Instalação
- npm i commitizen @glauberfunez/cz-conventional-changelog-for-jira/types
- npm i simple-git-hooks --save-dev
- npm i prettier --save-dev
- npm i lint-staged --save-dev
- Configurando simple-git-hooks
```json
//package-json
"simple-git-hooks": {
    "pre-commit": "lint-staged && git add .",
    "prepare-commit-msg": "exec < /dev/tty && git cz --hook || true",
    "commit-msg": "commitlint -E HUSKY_GIT_PARAMS",
    "pre-push": ""
},
```
- Na raiz do projeto
```bash
# [Optional] These 2 steps can be skipped for non-husky users
git config core.hooksPath .git/hooks/
rm -rf .git/hooks

# Update ./git/hooks
npx simple-git-hooks
```
Sempre que atualizar o simple-git-hooks, executar o comando `npx simple-git-hooks`.
