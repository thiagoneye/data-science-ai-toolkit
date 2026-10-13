# Guia de desenvolvimento assistido por IA

Este diretório documenta o uso do **OpenAI Codex no VS Code** no contexto de Ciência de Dados, Engenharia de Dados, Machine Learning e computação científica. Leia os módulos em ordem ou consulte-os por tarefa.

| Ordem | Guia | Resultado de aprendizagem |
|---|---|---|
| 00 | [Roadmap](00-roadmap.md) | Dominar conceitos e uma trilha de prática progressiva |
| 01 | [Paradigmas e metodologias](01-paradigmas-e-metodologias.md) | Selecionar estratégias de trabalho de acordo com o risco |
| 02 | [Arquitetura e ferramental](02-arquitetura-e-ferramental.md) | Diferenciar instruções, rules, skills, MCP e ferramentas |
| 03 | [Configurações deste projeto](03-configuracoes-deste-projeto.md) | Utilizar os arquivos reais do repositório e configurar MCPs |
| 04 | [Boas práticas e governança](04-boas-praticas-e-governanca.md) | Controlar contexto, segurança, evidência e revisão |

## Convenções

- Documentação em português brasileiro; identificadores e docstrings de código em inglês; comentários explicativos **dentro de código** em português.
- Trechos de comandos são exemplos: revise caminhos, permissões e versões antes de executar.
- Rules são **documentos de orientação** deste toolkit; a aplicação depende de `AGENTS.md` e da leitura dos arquivos adequados pelo agente.
- Skills não são executáveis por si só: descrevem workflows que o Codex pode selecionar e seguir.
- O template de MCPs **não instala nem ativa automaticamente** os servidores.

## Referências principais

- [Documentação Codex](https://developers.openai.com/codex/)
- [MCP em Codex](https://developers.openai.com/codex/mcp)
- [OpenAI Docs MCP](https://developers.openai.com/learn/docs-mcp)
- [Agent Skills](https://agentskills.io/)
- [GitHub MCP](https://github.com/github/github-mcp-server)

> Atualize este guia sempre que alterar a estrutura em `.agents/skills/`, `rules/` ou `.codex/config.toml.example`.
