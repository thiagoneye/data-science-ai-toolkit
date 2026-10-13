# 03 — Configurações deste projeto

[← Índice](README.md) · [← Arquitetura](02-arquitetura-e-ferramental.md) · [Próximo: governança →](04-boas-praticas-e-governanca.md)

Este capítulo descreve **os arquivos efetivamente incluídos** no toolkit original. Não confunda exemplos comentados com serviços ativos. No computador do usuário, a pasta de trabalho é `/home/thiagoney/GitHub/data-science-ai-toolkit`.

## Visão geral

```text
AGENTS.md
rules/                   # 8 regras de domínio e README
.agents/skills/          # 12 skills, cada uma com SKILL.md
.codex/config.toml.example
mcp/README.md
examples/prompts.md
scripts/validate_repository.py
```

`AGENTS.md` define comunicação (português no chat, identificadores/docstrings em inglês e comentários explicativos em português), segurança, integridade de dados e regras científicas. Solicita a leitura de documentos em `rules/` e das skills pertinentes.

## Catálogo das 8 rules

| Arquivo | Quando consultar | Verificação relevante |
|---|---|---|
| [`python-standards.md`](../rules/python-standards.md) | Implementação, revisão e refatoração Python | Tipos, organização, qualidade e manutenção |
| [`data-engineering.md`](../rules/data-engineering.md) | ETL, ELT, catálogos e armazenamento | Proveniência, schemas e idempotência |
| [`data-quality.md`](../rules/data-quality.md) | Ingestão e validação | Completude, duplicatas, anomalias |
| [`machine-learning.md`](../rules/machine-learning.md) | Experimentos com ML clássico | Split, baselines, métricas e leakage |
| [`deep-learning.md`](../rules/deep-learning.md) | Redes neurais e treinamento GPU | Checkpoints, logs e estabilidade |
| [`scientific-computing.md`](../rules/scientific-computing.md) | Dados CFD, modelos físicos, matemática numérica | Unidades, precisão e consistência |
| [`scientific-research.md`](../rules/scientific-research.md) | Estudos acadêmicos, artigos e ablação | Evidência, hipóteses e limitações |
| [`testing-and-reproducibility.md`](../rules/testing-and-reproducibility.md) | Qualquer alteração verificável | Testes, ambiente, seeds e reprodutibilidade |

**Como usar:** a leitura seletiva é mais eficiente que carregar todas as rules em todas as tarefas.

## Catálogo das 12 skills

| Skill | Quando utilizar | Entregável típico |
|---|---|---|
| [`dataset-profiling`](../.agents/skills/dataset-profiling/SKILL.md) | Conhecer novo dataset | Inventário de schema e estatísticas |
| [`exploratory-data-analysis`](../.agents/skills/exploratory-data-analysis/SKILL.md) | Descobrir distribuições e relações | Relatório EDA com gráficos |
| [`data-quality-validation`](../.agents/skills/data-quality-validation/SKILL.md) | Detectar falhas e inconsistências | Relatório de validação |
| [`data-pipeline-engineering`](../.agents/skills/data-pipeline-engineering/SKILL.md) | Projetar/alterar ETL e data lake | Pipeline e testes de ingestão |
| [`feature-engineering`](../.agents/skills/feature-engineering/SKILL.md) | Criar e transformar atributos | Features e checagens contra leakage |
| [`ml-experiment-design`](../.agents/skills/ml-experiment-design/SKILL.md) | Definir experimento e split | Protocolo, baselines e métricas |
| [`model-training`](../.agents/skills/model-training/SKILL.md) | Executar treinamento | Configuração, checkpoints e logs |
| [`model-evaluation`](../.agents/skills/model-evaluation/SKILL.md) | Medir desempenho e robustez | Tabela de métricas e análise de resíduos |
| [`scientific-ml-modeling`](../.agents/skills/scientific-ml-modeling/SKILL.md) | Surrogates e modelos científico-informados | Definição de arquitetura e avaliação |
| [`cfd-data-processing`](../.agents/skills/cfd-data-processing/SKILL.md) | Processar saídas CFD e OpenFOAM | Dados normalizados, metadados e checagens |
| [`scientific-literature-review`](../.agents/skills/scientific-literature-review/SKILL.md) | Levantamento de literatura | Síntese rastreável das fontes |
| [`reproducibility-audit`](../.agents/skills/reproducibility-audit/SKILL.md) | Revisar projeto antes de publicação | Checklist de rastreabilidade |

### Cenário 1 — EDA de catálogos Parquet

> Leia `AGENTS.md` e `rules/data-quality.md`. Aplique as skills `dataset-profiling` e `exploratory-data-analysis`. Analise um arquivo Parquet informado por mim sem modificá-lo. Relate schema, nulos, duplicatas, distribuição de parâmetros e limitações. Não afirme ter calculado estatísticas sem executar comandos.

### Cenário 2 — Data Lake Medallion e CFD

> Consulte `rules/data-engineering.md`, `rules/scientific-computing.md` e as skills `data-pipeline-engineering` e `cfd-data-processing`. Proponha uma etapa Silver idempotente que valide `case_id`, preserve Bronze e produza metadados estruturados. Primeiro apresente plano e testes; não modifique arquivos ainda.

### Cenário 3 — Modelo condicionado no tempo

> Consulte `rules/machine-learning.md`, `rules/scientific-research.md` e as skills `ml-experiment-design`, `scientific-ml-modeling` e `model-evaluation`. Planeje experimento de surrogate `3 parameters + time -> Cd`. Faça split por `case_id`, defina baseline, métricas e análise de resíduos por condição física. Não divulgue desempenho sem experimentos reais.

## MCPs do repositório: estado real

O arquivo [`.codex/config.toml.example`](../.codex/config.toml.example) contém **um servidor remoto ativo no exemplo** e **três blocos opcionais comentados**:

| Nome no template | Tipo | Status no template | Uso | Dependência |
|---|---|---|---|---|
| `openaiDeveloperDocs` | HTTP remoto | Declarado | Consultar documentação oficial OpenAI | Acesso à rede |
| `filesystem` | stdio local | Comentado | Operar arquivos em diretório permitido | Node/npx e servidor filesystem |
| `context7` | stdio local | Comentado | Consultar documentação de bibliotecas | Node/npx e serviço terceiro |
| `github` | stdio local em contêiner | Comentado | Interagir com repositórios GitHub | Docker, autenticação e permissões mínimas |

Esse é um catálogo de **exemplos disponíveis**, não prova de que quatro servidores estejam instalados ou conectados.

### Preparar ambiente e verificar

```bash
cd /home/thiagoney/GitHub/data-science-ai-toolkit
python scripts/validate_repository.py
codex --version
codex mcp list
```

Para acrescentar o MCP de documentação oficial sem copiar configurações:

```bash
codex mcp add openaiDeveloperDocs --url https://developers.openai.com/mcp
codex mcp list
```

### Configuração Codex

Inspecione o template com `cat .codex/config.toml.example`. Em Codex, a configuração global fica em `~/.codex/config.toml`; projetos confiáveis podem usar `.codex/config.toml`, conforme suporte e política da versão instalada. **Não sobrescreva** configurações pessoais existentes.

Exemplo de configuração com somente a documentação oficial:

```toml
[mcp_servers.openaiDeveloperDocs]
url = "https://developers.openai.com/mcp"
```

Exemplo de integração local **opcional** do filesystem, restrita a pasta aprovada:

```toml
[mcp_servers.filesystem]
command = "npx"
args = ["-y", "@modelcontextprotocol/server-filesystem", "/home/thiagoney/GitHub/data-science-ai-toolkit"]
```

A ativação depende de disponibilidade do pacote e confiança no servidor. **Não execute MCPs de terceiros sem revisão**. Para GitHub, siga o [guia oficial](https://github.com/github/github-mcp-server) e use token via variável de ambiente, com permissões mínimas. O arquivo do repositório traz exemplo de contêiner, não credenciais.

### Ferramentas que não exigem MCP extra

`python`, `pytest`, `git`, `conda`, `duckdb` via Python e inspeção de arquivos já podem ser acessados pela ferramenta de execução de comandos do Codex, se autorizados pelo ambiente. Um servidor MCP adicional só vale a pena se oferecer integração específica com valor e controle adequados.

### Comandos de trabalho e revisão

```bash
cd /home/thiagoney/GitHub/data-science-ai-toolkit
python scripts/validate_repository.py
git status --short
git diff --check
git diff --stat
```

**Critério de aceite:** relatórios devem separar claramente “arquivo consultado”, “comando executado”, “teste aprovado” e “sugestão não implementada”.
