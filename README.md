# SPS MCP B1 — versões publicadas

Vitrine de versões do **SPS MCP B1** (MCP para SAP Business One da SPS Group).
O gerenciador instalado em cada cliente consulta este repositório para saber se há versão nova
e, com o botão **Atualizar versão**, baixa e instala o pacote.

> Aqui ficam **somente os pacotes de instalação** e a ficha da última versão.
> Nada de código-fonte, configuração ou dados de clientes.

## Organização

| Arquivo | O que é |
|---|---|
| `versao.json` | Ficha da **última versão**: número, data, novidades, nome e tamanho do pacote, SHA-256 e **assinatura da SPS**. |
| `pacotes/SPS-MCP-B1-<versão>.zip` | Pacote de instalação. Ficam a última e a penúltima versão. |

## Segurança

- Cada `versao.json` é **assinado** com a chave privada da SPS (Ed25519). A chave pública vai dentro
  do produto: o gerenciador **recusa** qualquer ficha sem a assinatura da SPS.
- O gerenciador confere o **SHA-256** do pacote baixado antes de instalar.
- A atualização instala por cima e **mantém** conexões, usuários, perfis e configurações do cliente.

## Como publicar (dono do produto)

No projeto do SPS MCP B1:

```
npm run publicar
```

O comando gera o pacote, assina a ficha, copia para cá e envia ao GitHub.

---
SPS Group · SPS MCP B1. Baseado no exemplo `b1-mcp-server` da SAP (licença MIT).
