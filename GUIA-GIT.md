# Guia de Git e GitHub — do zero até publicar um projeto

Este guia é para quem já programa (Python, HTML, CSS, JavaScript) mas nunca usou Git/GitHub na prática. Objetivo: entender o que são essas ferramentas, o que pode ser hospedado, e como usar o GitHub como portfólio.

## 1. Git != GitHub

- **Git** é um programa que roda na sua máquina e guarda o *histórico* das alterações de uma pasta de código. Funciona sem internet, sem conta, sem nada — é só controle de versão local.
- **GitHub** é um site que hospeda repositórios Git na nuvem e adiciona camadas sociais/colaborativas em volta: Pull Requests, Issues, perfil público, GitHub Pages, etc.

Analogia: Git é o "Ctrl+Z com superpoderes e histórico completo" da sua pasta. GitHub é o Google Drive + rede social em volta desse histórico.

## 2. O que pode (e o que não deve) ser hospedado no GitHub

**Pode e é o uso normal:**
- Qualquer projeto de código: scripts, sites estáticos, apps web, bibliotecas, jogos, automações.
- Documentação, anotações técnicas, configs de projeto.
- Sites estáticos publicáveis de graça via **GitHub Pages** (HTML/CSS/JS puro, sem backend).

**Não deve:**
- Senhas, tokens de API, chaves de acesso, dados pessoais sensíveis — uma vez commitado, fica no histórico mesmo que você apague depois (um `.gitignore` ajuda a nunca deixar esses arquivos entrarem).
- Arquivos binários muito grandes (vídeos, datasets enormes) — o GitHub não foi feito pra isso, existem outros serviços para isso.

## 3. GitHub como portfólio

Sim — para quem programa, o GitHub funciona como um portfólio público:
- Seu **perfil** (`github.com/seu-usuario`) mostra todos os seus repositórios públicos, um resumo de atividade (aquele "mapa de quadradinhos verdes") e um README especial se você criar um repositório com o mesmo nome do seu usuário.
- O **README.md** de cada repositório é a "vitrine": quem olha o projeto lê ali o que ele faz, como rodar, prints, etc. É a primeira impressão.
- O **histórico de commits** mostra como você evoluiu o projeto — recrutador ou colega técnico consegue ver seu raciocínio, não só o resultado final.
- **GitHub Pages**: para projetos frontend (como o app de lista de tarefas que vamos construir), você pode publicar o site de graça e ter um link funcionando — ótimo para portfólio.

## 4. Conceitos centrais

| Termo | O que é |
|---|---|
| **Repositório (repo)** | A pasta do projeto com todo o histórico de versões |
| **Commit** | Uma "foto" das alterações feitas, com uma mensagem explicando o quê e por quê |
| **Branch** | Uma linha paralela de desenvolvimento — você pode experimentar sem afetar a versão principal (`main`) |
| **Remote** | O endereço do repositório na nuvem (ex: GitHub) associado à sua pasta local |
| **Clone** | Baixar uma cópia completa (com histórico) de um repositório remoto para sua máquina |
| **Push** | Enviar seus commits locais para o remote |
| **Pull** | Baixar commits novos que estão no remote e não estão na sua máquina |
| **Merge** | Juntar as alterações de uma branch em outra (ex: da sua branch para a `main`) |
| **Pull Request (PR)** | Um pedido formal no GitHub para que as alterações de uma branch sejam revisadas e depois mescladas (merge) na branch principal. É o jeito padrão de propor mudanças em equipe. |

## 5. O fluxo básico, passo a passo

Esse é exatamente o fluxo que você já praticou no repositório `meu-primeiro-pr`:

```bash
# 1. Clonar um repositório existente (só na primeira vez)
git clone https://github.com/seu-usuario/seu-repo.git

# 2. Criar uma branch nova para trabalhar sem afetar a main
git checkout -b nome-da-sua-alteracao

# 3. Fazer as alterações nos arquivos, depois "marcar" o que quer salvar
git add nome-do-arquivo.txt

# 4. Criar o commit (a "foto" com mensagem explicando a mudança)
git commit -m "Explica o que essa alteração faz"

# 5. Enviar a branch para o GitHub
git push -u origin nome-da-sua-alteracao
```

Depois do `push`, você vai no site do GitHub e abre o **Pull Request** comparando sua branch com a `main`. Lá você (ou outra pessoa revisando) pode comentar, pedir ajustes, e quando estiver tudo certo, clica em **Merge** — e as alterações entram oficialmente na `main`.

## 6. Boas práticas simples

- Mensagens de commit curtas e no imperativo: "Adiciona guia de Git", não "adicionei" ou "mudanças diversas".
- Um `.gitignore` na raiz do projeto evita commitar arquivos que não deveriam ir pro repositório (ex: `node_modules/`, arquivos de configuração local com senhas).
- Commits pequenos e frequentes contam uma história melhor do que um commit gigante com tudo junto.
- Nunca commitar senhas/chaves — se acontecer, trocar a credencial imediatamente (apagar do histórico não é suficiente).

## 7. Próximo passo prático

Vamos aplicar esse fluxo de novo no projeto da **lista de tarefas semanal**: criar o repositório, fazer commits, e no final publicar com GitHub Pages — assim você fixa o aprendizado construindo algo que realmente vai usar.
