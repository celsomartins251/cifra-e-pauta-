# Cifra & Pauta — PWA

Pacote preparado a partir do HTML original, preservando seu conteúdo e adicionando:
- `manifest.webmanifest` para instalação como PWA;
- `sw.js` para cache offline dos arquivos do aplicativo;
- ícone SVG próprio;
- registro do Service Worker no carregamento.

## Publicação
Envie o conteúdo desta pasta para uma pasta `cifra-e-pauta/` na raiz de um repositório GitHub com GitHub Pages habilitado.

URL esperada:
`https://SEU-USUARIO.github.io/SEU-REPOSITORIO/cifra-e-pauta/`

## Instalação no Android
1. Abra a URL pelo Chrome.
2. Aguarde o primeiro carregamento completo com internet.
3. Abra o menu ⋮ e escolha **Instalar app** ou **Adicionar à tela inicial**.

## Observações
O Service Worker armazena o HTML e os arquivos locais. A fonte tipográfica remota do Google é opcional e pode não carregar na primeira utilização offline. O pacote não adiciona autenticação Firebase nem altera o sistema de login do HTML original.


## Atualização automática
O Service Worker usa cache versionado (`cifra-e-pauta-v2`), verifica o `sw.js`
publicado ao abrir o PWA e também quando o dispositivo volta a ficar online ou
o app retorna ao primeiro plano. Quando detecta uma versão nova, ativa o novo
Service Worker e recarrega a página para servir os arquivos atualizados.
Os dados do editor armazenados em `localStorage` (chave `cp2`) não são apagados
pela rotina de atualização. Para receber uma versão nova, publique os arquivos
atualizados mantendo o mesmo endereço e incremente `CACHE_NAME` no `sw.js`
a cada mudança de arquivos estáticos.
