# teste-padrao-commit

Passos Instalação/Configuração
- npm i commitizen https://github.com/GlauberF/cz-conventional-changelog-for-jira-a --save-dev
- npm i simple-git-hooks --save-dev
- npm i prettier --save-dev
- npm i lint-staged --save-dev
- Criar um arquivo `czrc` e incluir o path e configs necessárias.
```bash
{
    "path": "./node_modules/@glauberfunez/cz-conventional-changelog-for-jira"
}
```
- Configurando simple-git-hooks
```json
//package-json
"simple-git-hooks": {
    "pre-commit": "lint-staged && git add .",
    "prepare-commit-msg": "exec < /dev/tty && git cz --hook || true",
    "commit-msg": "",
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
Sempre que atualizar o simple-git-hooks no package, executar o comando `npx simple-git-hooks`.
