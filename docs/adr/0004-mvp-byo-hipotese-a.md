# ADR 0004: MVP com base do próprio usuário (hipótese A)

- Status: Aceito (2026-11-26), por decisão do mantenedor na conversa.
- Substitui parcialmente: ADR 0003 (no MVP, não há servidor com chave de IA).
- Contexto: a especificação descreve uma base curada, com servidor, chave de IA e sincronização. Antes de investir nessa base, o mantenedor quer validar se a ideia interessa às pessoas.

## Decisão

O MVP é um app Android em que o próprio usuário:
1. Envia os próprios PDFs, que ficam no aparelho.
2. Monta a própria base a partir deles.
3. Faz as leituras com a IA que escolher, usando a chave dele.

Tudo fica no aparelho. Não há servidor da aplicação, nem base curada, nem login.

Essa é a **hipótese A**. A **hipótese B**, a base curada com servidor e assinatura, fica adiada. Ela volta quando a hipótese A indicar interesse.

## Consequências

- Não há servidor no MVP. A ADR 0003 deixa de valer para o MVP e passa a valer para a hipótese B.
- A ADR 0002 continua válida: nenhum conteúdo de fonte entra no repositório público. Como o usuário traz os próprios PDFs, o repositório não distribui conteúdo de terceiros.
- A chave de IA do usuário é guardada no aparelho com armazenamento seguro (Android Keystore). Ela não sai do dispositivo, exceto na chamada ao provedor escolhido pelo próprio usuário.
- Privacidade: os PDFs, o diário e as leituras ficam no aparelho.
- A especificação em `docs/especificacao.md` continua descrevendo a hipótese B. Ela não é alterada nesta ADR.

## Critérios para avançar

- Hipótese A: definir antes de começar a medir uso real, por exemplo, quantas pessoas concluem uma leitura com a própria base e se voltam a usar.
- Hipótese B: só retomar após esse resultado, com o piloto de base curada descrito na especificação.
