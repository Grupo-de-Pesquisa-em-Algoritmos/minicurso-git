# Minicurso de Git

Este repositório contém o material do minicurso introdutório de Git, voltado para quem deseja aprender os principais comandos e fluxos de trabalho com controle de versão. Aborda desde a configuração inicial até o uso de branches, commits e colaboração via GitHub.

## Seção Prática
1. Login via SSH
Verifique Git e SSH:
```bash
git --version
ssh -V
```

Gere chave:
```bash
ssh-keygen -t ed25519 -C "github@username"
```

Inicie ssh-agent:
```bash
eval "$(ssh-agent -s)"
```

Adicione chave:
```bash
ssh-add ~/.ssh/id_ed25519
```

Copie chave pública:
```bash
cat ~/.ssh/id_ed25519.pub
```

Adicione ao GitHub (Settings > SSH and GPG keys).
Teste:
```bash
ssh -T git@github.com
```


2. Repositórios
2.1 Criando repositório local
```bash
mkdir meu-projeto
cd meu-projeto
git init
echo "# Meu Projeto" > README.md
git add README.md
git commit -m "Commit inicial"
git remote add origin git@github.com:username/meu-projeto.git
git branch -M main
git push -u origin main
```

2.2 Clonando repositório
```
git clone git@github.com:username/meu-projeto.git
```

3. Fluxos
```bash
echo "Primeira linha" >> arquivo.txt
git add arquivo.txt
git commit -m "Adiciona arquivo.txt"
git push origin main
git pull origin main
```


4. Branches
```bash
git checkout -b feature/nova-ideia
echo "Nova funcionalidade" >> funcionalidade.txt
git add funcionalidade.txt
git commit -m "Adiciona nova funcionalidade"
git checkout main
git merge feature/nova-ideia
git push origin main
git tag -a v1.0 -m "Versão 1.0"
git push origin v1.0
```

Crie PR no GitHub.
Simule conflito e resolva localmente.


5. Rollback
```bash
git log --oneline
git revert abc123
git push origin main
# Ou reset (EXTREMAMENTE PERIGOSO):
git reset --hard abc123
git push --force origin main
```


6. Rebase
```bash
git checkout -b teste-rebase
echo "Teste" >> teste.txt
git add teste.txt
git commit -m "Commit de teste"
git checkout main
git merge teste-rebase
git log --graph --oneline
```


7. GitHub Pages
```bash
mkdir username.github.io
cd username.github.io
git init
echo '<h1>Meu Site</h1>' > index.html
git add index.html
git commit -m "Página inicial"
git remote add origin git@github.com:username/username.github.io.git
git branch -M main
git push -u origin main
```
