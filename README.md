# METAFISICO — Site institucional (metafisico.io)

Site estático e independente do aplicativo. HTML + CSS puros, sem build.

## Estrutura

```
index.html         Landing do ecossistema
privacidade.html   Política de Privacidade (Play Console / App Store)
styles.css         Estilos
favicon.svg
CNAME              metafisico.io
.nojekyll
assets/            Logos e telas do app
.github/workflows/deploy.yml   Deploy automático no GitHub Pages
```

## Publicar no GitHub Pages

1. Crie um repositório **público** novo (ex.: `metafisico-site`).
2. Copie **o conteúdo desta pasta** para a raiz do repositório (não a pasta `site/` inteira).
3. Faça commit e push na branch `main`.
4. No repositório: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
5. Aguarde o workflow terminar (aba **Actions**).

## Apontar o domínio na GoDaddy

Em **Meus Produtos → DNS → Gerenciar zonas** do `metafisico.io`:

| Tipo  | Nome | Valor                | TTL     |
|-------|------|----------------------|---------|
| A     | @    | 185.199.108.153      | 1 hora  |
| A     | @    | 185.199.109.153      | 1 hora  |
| A     | @    | 185.199.110.153      | 1 hora  |
| A     | @    | 185.199.111.153      | 1 hora  |
| CNAME | www  | SEUUSUARIO.github.io | 1 hora  |

Remova registros A/CNAME antigos de `@` e `www` (parking da GoDaddy).

Depois, em **Settings → Pages → Custom domain**, informe `metafisico.io`, salve e marque
**Enforce HTTPS** quando o certificado ficar disponível (pode levar alguns minutos após a
propagação do DNS).

## Atualizar os links das lojas

Em `index.html`, altere os `href` dos elementos `#ios-link` e `#android-link` para os links
definitivos do TestFlight e do Google Play.
