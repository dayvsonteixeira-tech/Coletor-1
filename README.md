# RAN Estoque

App simples (PWA) para bipar a RAN da peça e registrar o endereço (estoque ou linha), pensado pra rodar no navegador dos coletores Android da empresa, publicado pelo GitHub Pages.

## Como publicar no GitHub Pages

1. Crie uma conta no [github.com](https://github.com) se ainda não tiver.
2. Crie um repositório novo, público (ex: `ran-estoque`).
3. Na página do repositório, clique em **Add file → Upload files** e arraste os 4 arquivos desta pasta: `index.html`, `manifest.json`, `sw.js`, `icon.svg`. Clique em **Commit changes**.
4. Vá em **Settings → Pages**.
5. Em **Build and deployment → Source**, escolha **Deploy from a branch**.
6. Em **Branch**, escolha `main` e a pasta `/ (root)`. Clique em **Save**.
7. Aguarde 1–2 minutos. O link vai aparecer na própria página, algo como:
   `https://SEU-USUARIO.github.io/ran-estoque/`

## Como instalar no coletor

1. No coletor, abra o Chrome e acesse o link do passo 7.
2. Toque no menu (⋮) → **Adicionar à tela inicial** (ou "Instalar app", dependendo da versão do Chrome).
3. O app abre em tela cheia, com ícone próprio, como se fosse nativo.

## Como funciona

- O leitor do coletor normalmente funciona como teclado: ele "digita" o código no campo em foco. O app já mantém o campo de bipagem sempre focado.
- Fluxo: escolha o modo (**Estoque** ou **Linha**) no topo → bipe a RAN (7 caracteres) → bipe o endereço → salvo automaticamente, e o app já volta pronto pra próxima peça.
- Aba **Consultar**: mostra a posição atual de cada peça já bipada (a última localização registrada), com busca.
- Aba **Exportar**: baixa CSV com as peças em estoque (posição atual), CSV com o que foi pra linha e ainda não foi lançado no SAP (marca como sincronizado depois de baixar), e um histórico completo pra auditoria.
- Aba **Config**: nome do setor, operador, e limpar dados do piloto.

## Importante

- Os dados ficam salvos **no navegador daquele coletor** (localStorage), não na nuvem. Se o coletor for resetado ou os dados do navegador forem limpos, o histórico se perde — exporte o CSV com frequência.
- Cada RAN pode ser bipada várias vezes (ela muda de lugar); a aba Consultar sempre mostra a posição mais recente.
- Pensado pra rodar em **um setor por vez** primeiro. Pra expandir pra mais setores, o mais simples é duplicar o repositório (ou usar o campo "Setor" em Config) e ajustar depois se quiser separar os dados por área.
