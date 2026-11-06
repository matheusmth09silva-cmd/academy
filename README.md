# Pináculo Academy

Landing page de venda da **Pináculo Academy**, a mentoria para barbeiros construída dentro da Pináculo Barbearia.
Ela reúne técnica, estratégia e posicionamento para quem quer transformar talento em carreira.

🔗 **Site:** https://matheusmth09silva-cmd.github.io/academy/

---

## Sobre o projeto

O site inteiro é um único arquivo HTML (`index.html`), com CSS e JavaScript embutidos. Não há build, nem dependências para instalar, nem framework. Basta abrir o arquivo no navegador ou publicá-lo em qualquer hospedagem estática.

### Seções da página

| Seção | Âncora | Conteúdo |
|---|---|---|
| Hero | `#hero` | Logo, headline, subtítulo e CTA principal |
| Sobre | `#sobre` | O que é a mentoria, para quem é e como é entregue |
| Conteúdo | `#conteudo` | Módulos numerados, vídeo explicativo e modelo 3D opcional |
| Método | `#metodo` | As quatro frentes: Técnica, Prática, Posicionamento e Experiência |
| Depoimentos | `#depoimentos` | Prova social (desligada até haver depoimentos reais) |
| Oferta | `#oferta` | Itens inclusos, preço, garantia de 7 dias e botão de compra |
| FAQ | `#faq` | Perguntas frequentes |
| CTA final | `#final` | Chamada de encerramento |

### Recursos

- **Checkout em modal:** coleta nome, e-mail e WhatsApp (com máscara e validação) e redireciona para o **Mercado Pago**.
- **Checkout automático opcional** (Supabase + Pix com QR Code), com cadastro e login do aluno, geração do Pix, verificação de status e confirmação de pagamento.
- **Animações cinematográficas** com GSAP + ScrollTrigger e rolagem suave com Lenis. Elas são desligadas automaticamente quando o usuário pede movimento reduzido ou está em modo de economia.
- **Barra fixa de compra** no celular.
- **Vídeo explicativo** com suporte a YouTube, Vimeo ou arquivo `.mp4` local.
- **Modelo 3D do Sketchfab** opcional, carregado só quando o visitante toca para abrir.
- **Rastreamento** opcional com Meta Pixel e Google Analytics 4 (eventos `ViewContent`, `Lead`, `begin_checkout` etc.).
- **SEO e compartilhamento:** meta tags, Open Graph, Twitter Card e dados estruturados (schema.org).
- Responsivo, com suporte a iPhone (safe areas) e Android.

---

## Tecnologias

- HTML5, CSS3 e JavaScript puro
- [GSAP 3.12](https://gsap.com/) + ScrollTrigger: animações
- [Lenis](https://lenis.darkroom.engineering/): rolagem suave
- [Supabase JS](https://supabase.com/): autenticação e funções de pagamento (opcional)
- [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator): QR Code do Pix (opcional)
- Google Fonts: **Manrope** e **Cormorant Garamond**

As bibliotecas externas vêm do jsDelivr e são carregadas sob demanda, com verificação de integridade (SRI).

---

## Como editar

**Todo o conteúdo fica num único bloco de configuração**, no topo do arquivo: `window.PINACULO_CONFIG`. Para trocar textos, preço, vídeo ou links, você não precisa mexer em mais nada.

| Campo | O que controla |
|---|---|
| `heroHeadline`, `heroSub`, `heroCta` | Textos do topo da página |
| `aboutCards`, `modules`, `method` | Blocos de conteúdo |
| `videoEmbedUrl`, `videoPosterUrl` | Link do vídeo explicativo e imagem de capa |
| `sketchfabModelId` | ID do modelo 3D (vazio = não exibe) |
| `mentorName`, `mentorBio`, `mentorPhotoUrl` | Bloco "Quem conduz a formação" |
| `mostrarDepoimentos`, `testimonials` | Liga ou desliga os depoimentos e define o conteúdo deles |
| `includes` | Lista "O que está incluso" |
| `price`, `priceInstallments` | Preço exibido |
| `guaranteeTitle`, `guaranteeText` | Texto da garantia |
| `faq` | Perguntas e respostas |
| `linkPagamento` | Link de pagamento do Mercado Pago |
| `supabaseUrl`, `supabaseAnonKey` | Backend do checkout automático (opcional) |
| `supportEmail` | E-mail de atendimento no rodapé |
| `metaPixelId`, `ga4Id` | Rastreamento (vazio = desligado) |
| `stickyBar` | Liga ou desliga a barra fixa no celular |

> ⚠️ **Preço:** o valor cobrado é o que está configurado **no link do Mercado Pago**. Mantenha o campo `price` igual a esse valor.

> ⚠️ **Depoimentos:** os depoimentos que vêm no arquivo são apenas exemplos de formato. Publique somente depoimentos reais de alunos.

---

## Modos de pagamento

1. **Link do Mercado Pago** (modo atual). Com `linkPagamento` preenchido, o modal coleta os dados do aluno e abre o Mercado Pago numa nova aba. O valor cai na conta dona do link.
2. **Checkout automático.** Com `linkPagamento` vazio e `supabaseUrl`/`supabaseAnonKey` preenchidos, o site usa as funções `criar-pagamento` e `status-pagamento` do Supabase para gerar o Pix e confirmar o pagamento. O link do Grupo VIP só é entregue pelo backend, e só para pedidos pagos.

O **modo demonstração** (`modoDemo: true`) funciona apenas em `localhost` ou abrindo o arquivo local. Ele nunca registra pagamento nem libera acesso.

---

## Publicação

### GitHub Pages
1. Deixe o arquivo na raiz do repositório com o nome **`index.html`**.
2. Vá em **Settings → Pages**, escolha *Deploy from a branch*, branch `main` e pasta `/ (root)`, e clique em **Save**.
3. Em poucos minutos o site fica disponível em `https://<usuario>.github.io/<repositorio>/`.

### Netlify
Arraste a pasta com o `index.html` para o [Netlify Drop](https://app.netlify.com/drop).

> ℹ️ **Formulário de inscrição:** o registro de nome, e-mail e WhatsApp antes do pagamento usa o **Netlify Forms** (`data-netlify="true"`). Ele **só funciona hospedado na Netlify**. No GitHub Pages o pagamento continua funcionando, mas os dados da inscrição não ficam salvos.

### Imagem de compartilhamento
As meta tags apontam para `og-image.jpg` (1200 × 630 px). Coloque esse arquivo na mesma pasta do `index.html` para a prévia aparecer no WhatsApp, Instagram e outras redes.

---

## Estrutura

```
academy/
├── index.html      # site completo (HTML + CSS + JS)
├── og-image.jpg    # imagem de compartilhamento (adicionar)
├── LICENSE
└── README.md
```

---

## Autor

Desenvolvido por **Matheus Silva Melo**
[GitHub](https://github.com/matheusmth09silva-cmd) · [LinkedIn](https://www.linkedin.com/in/matheus-silva-melo-147622386)

## Licença

Distribuído sob a licença MIT. Veja o arquivo [`LICENSE`](LICENSE).
