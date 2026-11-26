# ADR 0003: Backend com a chave de IA e a base editorial

- Status: Aceito (2026-11-26), por decisão do mantenedor na conversa.
- Contexto: um conteúdo entregue ao aparelho pode ser extraído, e uma chave de API embutida no app pode ser extraída do APK. A base editorial tem restrições de direitos de uso (ADR 0002).

## Decisão

Existe um servidor com três responsabilidades:
1. Guardar a chave de API da IA, que nunca vai para o aplicativo nem para o repositório.
2. Guardar a base editorial em armazenamento privado.
3. Montar o contexto de cada leitura com o conteúdo necessário, chamar a IA e entregar o resultado.

O diário de leituras fica no aparelho durante o piloto. O servidor guarda só o buffer temporário de entrega e os metadados da operação, como define a especificação.

## Consequências

- O aplicativo não recebe a base inteira. Recebe a interpretação pronta, pelo servidor.
- A API do servidor é independente de plataforma, para suportar um cliente iOS depois (ADR 0001).
- Histórico de leituras no servidor fica fora do piloto. Se for adotado, exige nova decisão, com impactos de privacidade e retenção registrados.
- A escolha da linguagem e da hospedagem do servidor fica para outra ADR.
