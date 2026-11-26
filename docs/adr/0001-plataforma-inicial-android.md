# ADR 0001: Plataforma inicial Android, com iOS depois

- Status: Aceito (2026-11-26), por decisão do mantenedor na conversa.
- Contexto: a especificação deixa aberto se a primeira plataforma é web, Android, iOS ou uma combinação. O MVP funciona por dispositivo.

## Decisão

O primeiro cliente é Android. iOS fica para depois.

## Justificativa

- Android permite distribuição por APK, sem passar pela revisão de loja para o piloto. A instalação de APK pelo usuário final depende de permitir fontes desconhecidas no aparelho; o ADB é a ferramenta do desenvolvedor e não é exigido do usuário.
- iOS exige conta de desenvolvedor e revisão de loja, o que atrasa o piloto.

## Consequências

- Stack do cliente: Kotlin, Jetpack Compose, minSdk 28, compileSdk 36 (ver `docs/arquitetura.md`).
- O backend (chave de IA, entrega da leitura, base editorial) deve expor uma API independente de plataforma, para que um cliente iOS possa ser adicionado depois sem refazer o servidor.
- Lógica de domínio (tiragens, métodos, posições) deve ficar fora da camada de interface, para facilitar a reutilização. Como isso será feito (por exemplo, Kotlin Multiplatform) fica para outra ADR.
- Rejeitado para o MVP: web como primeiro cliente, porque o diário no aparelho e o uso offline pedem um app nativo.
