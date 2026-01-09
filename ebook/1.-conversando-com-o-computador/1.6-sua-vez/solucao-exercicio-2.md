---
icon: puzzle-piece
---

# Solução Exercício 2

**1) Confirme que você está na pasta correta:**

```bash
pwd
```

A saída deve mostrar o caminho até `pratica-terminal`.

**2) Crie o arquivo `anotacoes.txt`:**

Linux/macOS:

```bash
touch anotacoes.txt
```

Windows (CMD):

```cmd
type nul > anotacoes.txt
```

Windows (PowerShell):

```powershell
New-Item anotacoes.txt
```

Esse comando não gera saída.

**3) Crie uma cópia do arquivo:**

Linux/macOS:

```bash
cp anotacoes.txt anotacoes-backup.txt
```

Windows:

```cmd
copy anotacoes.txt anotacoes-backup.txt
```

**4) Renomeie o arquivo original:**

Linux/macOS:

```bash
mv anotacoes.txt minhas-anotacoes.txt
```

Windows:

```cmd
move anotacoes.txt minhas-anotacoes.txt
```

**5) Liste os arquivos para conferir o resultado:**

Linux/macOS:

```bash
ls
```

Windows:

```cmd
dir
```

Você deve ver os arquivos `minhas-anotacoes.txt` e `anotacoes-backup.txt`.

***

👏 Muito bem! Você já sabe criar, copiar e renomear arquivos pelo terminal.
