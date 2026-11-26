# ADR 0002: Base editorial em armazenamento privado, fora do git

- Status: Aceito (2026-11-26), por decisão do mantenedor na conversa.
- Contexto: o repositório `luisnovais-dev/desembaralhe` é público. A especificação exige verificar os direitos de uso de cada fonte antes da publicação, e não presume autorização pela existência de um PDF na internet.

## Decisão

A base editorial (trechos das fontes, significados revisados, evidências e metadados de revisão) fica em armazenamento privado, no lado do servidor. Não é versionada no git deste repositório.

## Consequências

- Nenhum PDF, trecho de livro ou exportação da base entra no repositório. O `.gitignore` bloqueia tipos de arquivo comuns de fontes (PDF, EPUB, DOC) como proteção extra, mas não substitui a revisão do que é commitado.
- O repositório guarda o código, a documentação do processo e a especificação. Se a especificação ou outras partes do repositório contiverem conteúdo de terceiros, isso deve ser revisto antes de manter o repositório público.
- O aplicativo não recebe a base inteira. Ele recebe, pelo servidor, apenas o conteúdo necessário para cada leitura (ver ADR pendente sobre chave de IA e backend).
- Antes de qualquer publicação de conteúdo da base, deve ser verificada a situação de uso de cada fonte.

## Fora do escopo desta ADR

Esta ADR trata apenas das fontes. As leituras não são guardadas no servidor: o diário fica no aparelho durante o piloto, e o servidor só mantém o buffer de entrega e os metadados da operação, como define a especificação (seção Entrega e recuperação da leitura).

## Pendência

- Decidir se o repositório continua público. Isso não foi decidido nesta ADR.
