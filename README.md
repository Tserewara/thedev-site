# thedev.com.br

Site institucional estático da THE DEV TECNOLOGIA LTDA. HTML e CSS puros, sem build, sem JavaScript e sem rastreamento. Serve à verificação da empresa e à revisão do app na Meta.

| Página | Uso na Meta |
|---|---|
| `index.html` | Site da empresa |
| `privacidade.html` | Privacy Policy URL |
| `termos.html` | Terms of Service URL |
| `exclusao-de-dados.html` | Data Deletion Instructions URL |

O cabeçalho e o rodapé (dados da empresa) se repetem em todas as páginas: ao mudar um, mude em todos. Logo e ícones ficam em `assets/` (pixel art: exiba o logo em 56 px de altura ou múltiplos inteiros disso). A seção "Integrações com plataformas de terceiros" da política de privacidade e a seção de integrações da página de exclusão são as que a Meta procura.

## Como publicar no GitHub Pages

1. Crie um repositório **público** no GitHub e envie a branch `main`.
2. Em **Settings → Pages**, em "Build and deployment", escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
3. Em **Custom domain**, informe `thedev.com.br` (o arquivo `CNAME` já traz esse valor).
4. Na DigitalOcean (**Networking → Domains → thedev.com.br**), crie os registros:

   | Tipo | Nome | Valor |
   |---|---|---|
   | A | `@` | `185.199.108.153` |
   | A | `@` | `185.199.109.153` |
   | A | `@` | `185.199.110.153` |
   | A | `@` | `185.199.111.153` |
   | AAAA | `@` | `2606:50c0:8000::153` |
   | AAAA | `@` | `2606:50c0:8001::153` |
   | AAAA | `@` | `2606:50c0:8002::153` |
   | AAAA | `@` | `2606:50c0:8003::153` |
   | CNAME | `www` | `<usuario>.github.io.` |

   IPs conferidos na [documentação do GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site) em 11/10/2026. Remova registros A/AAAA antigos do apex que apontem para outro lugar.
5. Opcional, recomendado: verifique o domínio em **Settings (da conta) → Pages → Add a domain**, para impedir que outro repositório o use.
6. Quando o DNS propagar e o certificado for emitido, marque **Enforce HTTPS** em Settings → Pages.

Para conferir a propagação: `dig thedev.com.br +short` e `dig www.thedev.com.br +short`.
