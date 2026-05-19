# Publicar o ecossistema Bianca (GitHub + Vercel)

## Arquivos principais

| Arquivo | URL publicada | Função |
|---------|---------------|--------|
| `Links.html` | `https://seu-dominio.com/` | Página de links (destino do **bit.ly/bianca-povliuk**) |
| `Site 2 bianca povliuk.html` | `https://seu-dominio.com/Site%202%20bianca%20povliuk.html` | Landing do **Método ELO** |

A pasta **`Assets/`** vai junto no GitHub.

A Vercel usa `vercel.json` para abrir `Links.html` na raiz do domínio (`/`), mesmo sem `index.html`.

---

## Fluxo

```
bit.ly/bianca-povliuk  →  Links.html (página inicial)
    ├── Conheça o Método ELO  →  Site 2 bianca povliuk.html
    ├── Falar no Whatsapp     →  wa.me
    └── Instagram
```

---

## Atualizar o site

Na pasta do projeto, no **Git Bash**:

```bash
git add .
git commit -m "Descreva o que mudou"
git push
```

A Vercel republica automaticamente.
