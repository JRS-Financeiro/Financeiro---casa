# Finanças da Família

Página teste do app para organizar as contas da casa. É um arquivo único (`index.html`), sem servidor, sem instalação.

## Como usar

1. Abra o `index.html` no navegador, ou publique no GitHub Pages (Settings → Pages → branch).
2. Primeiro acesso: usuário **Familia**, senha **Familia** (sem acento).
3. Troque a senha em **Ajustes → Segurança** logo depois de entrar.
4. O app abre com dados de exemplo. Use **Limpar exemplos** para começar com as contas reais.

## O que faz

- **Contas do mês**: contas fixas que se repetem todo mês ou avulsas, com dia de vencimento e aviso de X dias antes. Marque como paga e informe o valor real (luz e água mudam todo mês).
- **Totais**: quanto já foi pago, quanto falta pagar, contas atrasadas.
- **Gastos do dia a dia**: mercado, combustível, farmácia, lazer etc., com limite mensal por categoria (método dos envelopes).
- **Análises**: gráfico por categoria, últimos 6 meses, histórico mês a mês.
- **Regra 50/30/20** e **reserva de emergência** calculadas sobre a renda da família.
- **Lembretes**: alertas no aparelho e um arquivo `.ics` para o calendário do celular, que avisa mesmo com o app fechado.
- **Cópia de segurança** criptografada para exportar e restaurar.
- **Modo privado**: os valores aparecem como `R$ *****` ao abrir. O olho ao lado de cada valor revela só ele; o olho do topo revela ou esconde todos. Ao sair do app, tudo volta a ficar escondido.
- **Três temas**: Pérola (claro, padrão), Esmeralda e Safira (em Ajustes → Aparência).
- **Lançamento rápido**: o botão **+** no centro da barra lança um gasto em segundos e mostra quanto resta no limite.
- **Motivação**: nota da família (0 a 100) com a próxima ação para subir, sequência de meses sem atraso, 10 conquistas, sonhos da família com barra de progresso, primeiros passos guiados e comemoração ao quitar o mês.

## Segurança

- Os dados ficam só no aparelho, criptografados com **AES-256-GCM**.
- A chave vem da senha por **PBKDF2-SHA256 com 600 mil iterações** e nunca é gravada. Sem a senha, os dados armazenados são ilegíveis.
- A senha inicial não está escrita no código; só um hash dela.
- Depois de 5 tentativas erradas, o login bloqueia por tempo crescente (até 15 min).
- Bloqueio automático por inatividade (configurável).
- Política de segurança de conteúdo (CSP) proíbe scripts externos e qualquer conexão de rede, então os dados não saem do aparelho.
- Todo texto digitado é escapado antes de aparecer na tela (proteção contra XSS).

**Limite desta versão:** cada aparelho tem seus próprios dados. Para a família inteira ver as mesmas contas em celulares diferentes, a próxima etapa é um servidor com contas de usuário (por exemplo Supabase ou Firebase), mantendo a criptografia.

## Fontes das dicas

- Banco Central do Brasil, [Caderno de Cidadania Financeira](https://www.bcb.gov.br/pre/pef/port/caderno_cidadania_financeira.pdf)
- Gustavo Cerbasi, [Forbes Brasil](https://forbes.com.br/forbes-money/2022/10/cinco-passos-para-o-planejamento-financeiro-segundo-gustavo-cerbasi/)
- Nathalia Arcuri, [Catraca Livre](https://catracalivre.com.br/economize/nathalia-arcuri-da-4-dicas-para-ajustar-as-financas-em-2023/)
- Elizabeth Warren e Amelia Tyagi, *All Your Worth* (regra 50/30/20)
- George S. Clason, *O Homem Mais Rico da Babilônia*
- Morgan Housel, *A Psicologia Financeira*
