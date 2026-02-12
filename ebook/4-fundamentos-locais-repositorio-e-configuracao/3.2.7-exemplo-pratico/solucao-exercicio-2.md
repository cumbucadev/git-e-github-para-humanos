---
icon: puzzle-piece
---

# Solução Exercício 2

#### 💻 Linux / macOS

```bash
# 1. Criar a pasta
mkdir lista-de-leituras

# 2. Entrar na pasta
cd lista-de-leituras

# 3. Iniciar o repositório Git
git init

# 4. Verificar o status do repositório
git status

# 5. (Opcional) Verificar se a pasta .git foi criada
ls -a
```

#### 🪟 Windows (cmd ou PowerShell)

```powershell
1. Criar a pasta
mkdir lista-de-leituras

:: 2. Entrar na pasta
cd lista-de-leituras

:: 3. Iniciar o repositório Git
git init

:: 4. Verificar o status do repositório
git status

:: 5. (Opcional) Ver a pasta .git

:: No PowerShell:
Get-ChildItem -Force

:: No cmd:
dir /a
```

#### O que você deve ver

Ao rodar `git init`, você verá uma mensagem como esta:

```bash
Initialized empty Git repository in /caminho/para/lista-de-leituras/.git/
```

E ao rodar `git status`, algo como:

```bash
On branch master

No commits yet
nothing to commit (create/copy files and use "git add" to track")
```

***

:books: Pronto! Agora o seu projeto "lista-de-leituras" está versionado com Git.
