# CBH Engenharia - Assets CDN

Este repositório é utilizado para hospedar as imagens e outros recursos estáticos da aplicação **CBH Engenharia** de forma otimizada utilizando a rede de distribuição de conteúdo (CDN) do **jsDelivr**.

## 🚀 Como Funciona

Sempre que uma nova imagem for adicionada a este repositório no branch principal (`main`), ela poderá ser acessada de forma pública e otimizada globalmente usando a seguinte URL:

```text
https://cdn.jsdelivr.net/gh/HenriqueNasciment0/cbh-assets@main/images/SUBPASTA/ARQUIVO
```

### Exemplo de uso:
* **Caminho no repositório:** `images/logo/cbh-logo-light.png`
* **URL do CDN:** `https://cdn.jsdelivr.net/gh/HenriqueNasciment0/cbh-assets@main/images/logo/cbh-logo-light.png`

---

## 🛠️ Como adicionar novas imagens e usar no Projeto

1. **Adicione a imagem na pasta correta** dentro do repositório `cbh-assets`.
2. **Faça commit e push** para enviar as alterações ao GitHub:
   ```bash
   git add .
   git commit -m "feat: adicionar nova imagem"
   git push origin main
   ```
3. **Copie a URL correspondente** no formato do jsDelivr (como mostrado acima) e utilize-a diretamente no código do projeto principal (`cbh-engenharia`).

---

## ⚙️ Integração com Next.js

Para que o componente `<Image />` do Next.js aceite o carregamento destas imagens externas, o domínio `cdn.jsdelivr.net` já está configurado no arquivo `next.config.ts` da aplicação sob as políticas de `remotePatterns`:

```typescript
// next.config.ts
const nextConfig: NextConfig = {
  images: {
    remotePatterns: [
      {
        protocol: 'https',
        hostname: 'cdn.jsdelivr.net',
        pathname: '/**',
      },
    ],
  },
};
```
