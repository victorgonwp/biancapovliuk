# Publicar o ecossistema Bianca (GitHub + Vercel)

Este projeto tem **duas páginas** no mesmo site:

| Arquivo | URL depois de publicar | Função |
|---------|------------------------|--------|
| `index.html` | `https://seu-dominio.com/` | Página de links (Linktree) — destino do **bit.ly/bianca-povliuk** |
| `metodo.html` | `https://seu-dominio.com/metodo.html` | Landing do **Método ELO** (formação e mentoria) |

A pasta **`Assets/`** precisa ir junto (logo e fotos).

---

## Fluxo que você montou

```
Instagram / bio
    ↓
bit.ly/bianca-povliuk  →  página de links (index)
    ├── Conheça o Método ELO  →  /metodo.html
    ├── Falar no Whatsapp     →  WhatsApp direto (wa.me)
    └── Instagram
```

O **bit.ly** não pode mais ser o botão verde do WhatsApp na página de links — senão a pessoa volta para a mesma página. Por isso o botão verde usa **wa.me** com o número `5514988378339`.

---

## Passo a passo (igual ao seu site Vigon)

### 1. Conta no GitHub

1. Acesse [github.com](https://github.com) e entre na sua conta.
2. Clique em **New repository**.
3. Nome sugerido: `bianca-povliuk` (ou outro).
4. Deixe **Public** (Vercel gratuito funciona bem assim).
5. **Não** marque “Add README” se você já vai enviar os arquivos da pasta.
6. Crie o repositório.

### 2. Enviar os arquivos para o GitHub

**Opção A — GitHub Desktop (mais fácil para quem é leigo)**

1. Instale [GitHub Desktop](https://desktop.github.com/).
2. **File → Add local repository** e escolha esta pasta do projeto.
3. Se pedir, clique em **create a repository** nesta pasta.
4. Escreva um resumo do commit, ex.: `Site Bianca: links + método ELO`.
5. **Commit to main** → **Publish repository** (ou **Push origin**).

**Opção B — Terminal (na pasta do projeto)**

```powershell
git init
git add index.html metodo.html links.html Assets vercel.json .gitignore
git commit -m "Publica site Bianca: links e metodo ELO"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/bianca-povliuk.git
git push -u origin main
```

Troque `SEU-USUARIO` e o nome do repositório pelos seus.

### 3. Conectar na Vercel

1. Acesse [vercel.com](https://vercel.com) e entre (pode usar “Continue with GitHub”).
2. **Add New… → Project**.
3. Importe o repositório `bianca-povliuk`.
4. Framework Preset: **Other** (é HTML estático, sem build).
5. **Deploy**.

Em ~1 minuto você ganha um link tipo: `https://bianca-povliuk.vercel.app`

Teste:

- `https://....vercel.app/` → página de links  
- `https://....vercel.app/metodo.html` → landing do método  

### 4. Domínio próprio (quando tiver)

Exemplo: `biancapovliuk.com.br` ou subdomínio `links.biancapovliuk.com.br`.

1. Na Vercel: projeto → **Settings → Domains**.
2. Adicione o domínio e siga as instruções de DNS (geralmente registro **CNAME** ou **A** no Registro.br / Cloudflare / onde comprou).
3. Aguarde propagação (pode levar de minutos a algumas horas).

Depois, no **bit.ly**, aponte `bianca-povliuk` para:

`https://seu-dominio.com/`  
(com barra no final ou sem — os dois costumam funcionar)

### 5. Atualizar o site no futuro

1. Edite os arquivos no Cursor.
2. Commit + Push no GitHub Desktop (ou `git push`).
3. A Vercel publica de novo **automaticamente**.

---

## Checklist antes do deploy

- [ ] Pasta `Assets/` com logo e foto da Bianca
- [ ] `index.html` abre local e os 3 botões funcionam
- [ ] `metodo.html` abre local e imagens carregam
- [ ] bit.ly aponta para a URL **raiz** do site publicado (`/`)
- [ ] Botão verde na página de links abre o WhatsApp (não o bit.ly)

---

## Dúvidas comuns

**Preciso de dois projetos na Vercel?**  
Não. Um repositório, um projeto Vercel, duas páginas (`index` + `metodo`).

**E o Site 1 (clientes)?**  
O arquivo `Site 1 bianca povliuk.html` ficou de backup. Se quiser publicar depois, pode virar `clientes.html` no mesmo projeto.

**Nome com espaço (`Site 2...`)?**  
Na publicação usamos `metodo.html` sem espaços — melhor para links e SEO.

---

## Suporte

Se algo quebrar após o deploy, confira no navegador (F12 → Console) se alguma imagem em `Assets/` não foi enviada ao GitHub.
