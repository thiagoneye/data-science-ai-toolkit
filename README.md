# Codex Data Science Toolkit

Repositório de **MCPs, regras e skills** para **OpenAI Codex no VS Code**, com foco em ciência de dados, engenharia de dados, machine learning, deep learning e computação científica.

## O que contém

- `docs/`: documentos do uso do **OpenAI Codex no VS Code** no contexto de Ciência de Dados, Engenharia de Dados, Machine Learning e computação científica.
- `AGENTS.md`: regras globais do repositório, lidas pelo Codex.
- `rules/`: documentos de regras detalhadas por domínio, referenciados pelo `AGENTS.md`.
- `.agents/skills/`: skills acionáveis que usam o formato `SKILL.md`.
- `.codex/config.toml.example`: exemplos de servidores MCP para copiar seletivamente para `~/.codex/config.toml` ou `.codex/config.toml` em projetos confiáveis.
- `mcp/`: catálogo, política e instruções de instalação.
- `scripts/validate_repository.py`: validação estática da estrutura e metadados das skills.
- `examples/`: exemplos de prompts e fluxo de trabalho.

## Início rápido (Ubuntu + VS Code + Codex)

1. Instale/autentique a extensão **OpenAI Codex** no VS Code e abra esta pasta como workspace.
2. Verifique se o agente consegue ler `AGENTS.md` e descobrir as skills em `.agents/skills/`.
3. Personalize as regras aplicáveis ao projeto: leia `rules/README.md`.
4. **Não copie a configuração MCP inteira sem revisar.** Consulte `mcp/README.md`, substitua os caminhos e habilite somente os servidores desejados.
5. Experimente: `Use a skill dataset-profiling para inspecionar data/sample.parquet, sem modificar os dados brutos.`

> O arquivo `.codex/config.toml.example` **não** é carregado automaticamente: é um template. Para ativá-lo, copie as seções desejadas para `~/.codex/config.toml` ou para `.codex/config.toml` de um projeto confiável. O VS Code e a CLI do Codex compartilham a configuração.

## Skills disponíveis

| Skill | Resultado esperado |
| --- | --- |
| `dataset-profiling` | perfil de qualidade e schema |
| `exploratory-data-analysis` | relatório de EDA com visualizações |
| `data-pipeline-engineering` | desenho/implementação incremental de pipeline |
| `data-quality-validation` | testes e contrato de dados |
| `feature-engineering` | transformações sem vazamento |
| `ml-experiment-design` | plano de experimento com splits e baselines |
| `model-training` | treinamento reproduzível e checkpoints |
| `model-evaluation` | avaliação, erros e incerteza |
| `scientific-ml-modeling` | plano de surrogate / SciML |
| `scientific-literature-review` | revisão com referências verificáveis |
| `reproducibility-audit` | auditoria de seeds, dependências e dados |

## Convenções importantes

- Respostas em português brasileiro; identificadores, nomes de funções/classes e docstrings em inglês; comentários explicativos no código em português.
- Nunca inventar resultados de análises, métricas, citações ou resultados de execução.
- Nunca usar dados de teste para selecionar features, pipelines ou hiperparâmetros.
- Para séries temporais de múltiplas simulações, dividir por identificador de caso quando o objetivo for generalizar para **novas simulações**.
- Segredos em variáveis de ambiente, nunca commitados.
- Modificar somente arquivos autorizados; execução externa e servidores MCP precisam de revisão de permissões.

## Publicação no GitHub

```bash
cd data-science-ai-toolkit
git init
git add .
git commit -m "feat: add Codex data science MCP rules and skills toolkit"
git branch -M main
# Crie um repositório vazio no GitHub e substitua a URL:
git remote add origin https://github.com/USER/data-science-ai-toolkit.git
git push -u origin main
```

## Referências

- [OpenAI Codex e MCP](https://developers.openai.com/codex/mcp)
- [OpenAI Codex skills](https://developers.openai.com/codex/skills)
- [VS Code Agent Skills](https://code.visualstudio.com/docs/copilot/customization/agent-skills)
- [GitHub MCP](https://github.com/github/github-mcp-server)
- [Filesystem MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem)
- [OpenAI Docs MCP](https://developers.openai.com/learn/docs-mcp)

**Escopo:** templates e instruções; os MCPs dependem de instalação/autenticação externa e não são iniciados por este repositório.
