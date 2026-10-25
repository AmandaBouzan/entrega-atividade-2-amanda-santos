# ENTREGA — Atividade 4 (PWA)

**Nome:** Amanda Santos Pereira Bouzan · **GitHub:** AmandaBouzan

## 1. Site comum × PWA

A comparação abaixo descreve o comportamento esperado da arquitetura implementada.
A observação no navegador do PWA do professor e os prints ainda precisam ser
registrados pela aluna; não foram apresentados como observações já realizadas.

| # | Site comum sem suporte offline | PWA desta atividade | Evidência a registrar |
|---|---|---|---|
| 1 | O acesso depende da conexão e do cache HTTP disponível. | O Service Worker mantém o shell e aplica cache à API e aos pôsteres; o IndexedDB mantém os filmes. | Application → Service Workers e Cache Storage. |
| 2 | Normalmente abre como uma aba do navegador. | O manifest com `display: standalone` permite instalação e abertura em janela própria em navegadores compatíveis. | Janela do app instalado ou manifest no DevTools. |
| 3 | O carregamento de uma página normalmente usa a versão disponível no servidor. | Uma nova versão do Service Worker aguarda a escolha Atualizar/Depois, preservando a sessão até a confirmação. | Aviso “Nova versão disponível”. |

Um site comum também pode adotar essas capacidades; as diferenças acima se referem
à comparação com um site que não implementa Service Worker/manifest/offline.

## 2. Prova do offline no build

**Pendente de execução com o token TMDB pessoal.** Os testes automatizados não
substituem prints de uma execução real. Nenhum token foi incluído no repositório.

- [ ] Visitar o PWA do professor e registrar a comparação da seção 1.
- [ ] Capturar Application → Cache Storage: `tmdb-api` e `tmdb-images` com itens.
- [ ] Capturar o app após modo Offline + reload e a aba Favoritos com o banner.
- [ ] Capturar o aviso “Nova versão disponível” e testar Atualizar/Depois.

Salvar as imagens em `evidencias/` e referenciá-las neste arquivo depois do teste.
Procedimento completo no [README](README.md).

## 3. Reflexão: autoUpdate × prompt

Para um checkout eu escolheria `prompt`, evitando recarregar a página durante o pagamento.
O aviso permite concluir a compra antes de ativar a nova versão.
O risco é manter uma versão antiga, então o servidor deve preservar compatibilidade e validar a transação.
Para um app de notícias eu escolheria `autoUpdate`, pois simplifica a adoção de correções e melhorias.
Mesmo nesse caso, uma recarga pode interromper a leitura e perder a posição do artigo.
Eu preservaria artigo e posição, e separaria a atualização das notícias da atualização do código do app.
Se o produto priorizasse leitura sem interrupções, usaria `prompt` também para notícias.

## 4. Declaração de uso de IA

Foi usado ChatGPT/Codex para ler o enunciado, implementar os TODOs, acrescentar
verificações automatizadas e preparar a documentação e o Pull Request. A validação
com o token pessoal e as evidências visuais ainda precisam ser realizadas pela aluna.
