# Site de pedidos – Batida de Açaí

- `index.html` – página do cliente (tamanho, complementos, endereço, pagamento Pix com QR Code)
- `admin.html` – painel de vocês (pedidos + editar tamanhos, complementos, preços, taxa, Pix, loja aberta/fechada)
- `config.js` – nome da loja e dados do Firebase
- `firestore.rules` – regras de segurança

## 1. Criar o banco (Firebase, grátis)
1. Acesse https://console.firebase.google.com → **Adicionar projeto**.
2. **Build → Firestore Database → Criar banco** (modo produção, região `southamerica-east1`).
3. Aba **Regras**: cole o conteúdo de `firestore.rules` (troque os e-mails pelos de vocês) e **Publicar**.
4. **Build → Authentication → Começar → E-mail/senha → Ativar**. Em **Usuários → Adicionar usuário**, crie o login de vocês. Em **Configurações → Ações do usuário**, desmarque "Ativar criação (cadastro)".
5. **Configurações do projeto (engrenagem) → Seus apps → `</>` (Web)** → registre e copie `apiKey`, `authDomain`, `projectId`, `appId` para o `config.js`.
6. Preencha também no `config.js`: chave Pix, nome, cidade e WhatsApp.

## 2. Publicar no GitHub
1. Crie um repositório no GitHub e envie estes arquivos.
2. **Settings → Pages → Branch: main / root → Save**.
3. O site fica em `https://SEU-USUARIO.github.io/NOME-DO-REPO/` e o painel em `.../admin.html`.
4. No Firebase, **Authentication → Configurações → Domínios autorizados**: adicione `SEU-USUARIO.github.io`.

## Como funciona o pagamento
O cliente paga por **Pix com o valor exato** (QR Code e copia e cola). O pedido aparece no painel como "aguardando pagamento"; vocês conferem no app do banco e tocam em **Pagamento confirmado**. É grátis e não precisa de servidor.
Para confirmação automática ou cartão, seria preciso um gateway (ex.: Mercado Pago) com um servidor.
