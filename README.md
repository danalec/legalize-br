# Legalize — Brasil 🇧🇷

Legislação federal brasileira como repositório Git. Cada lei é um arquivo Markdown, cada lei um commit com sua data oficial de publicação.

**198.138 leis federais** (1988–2026) do [Portal de Dados Abertos](https://dados.gov.br) via [LexML](https://www.lexml.gov.br).

🌐 [English](README.en.md) | [Español](README.es.md)

## Início rápido

```bash
git clone https://github.com/danalec/legalize-br.git
cd legalize-br

# Ver Lei 9.887/1999
cat br/000349107.md

# Listar leis de 2024
ls br/* | head -100

# Ver metadados
head -20 br/000349107.md
```

## Estrutura

```
br/
├── 000349107.md              # Lei federal
├── 000350145.md              # Decreto
├── CAMARA-2616963.md         # PL da Câmara
└── ... (198.138 arquivos)
```

### Convenção de nomes

Cada arquivo `.md` contém uma lei federal com frontmatter YAML:

```yaml
---
identificador: "000349107"
pais: "br"
rango: "Lei"
fecha_publicacion: "1999-07-22"
---
```

| Campo | Descrição |
|-------|-----------|
| `identificador` | ID único do LexML |
| `pais` | Código do país (`br`) |
| `rango` | Tipo normativo (Lei, Decreto, MPV, etc.) |
| `fecha_publicacion` | Data de publicação no DOU |

## Tipos de legislação

| Rango | Descrição | Exemplos |
|-------|-----------|----------|
| `Lei` | Leis Ordinárias | Lei 9.887/1999 |
| `Decreto` | Decretos Executivos | Decreto 3.555/2000 |
| `Decreto Legislativo` | Decretos do Congresso | DL 4856037/1988 |
| `MPV` | Medidas Provisórias | MPV 2616962/2026 |
| `PL` | Projetos de Lei | PL 2616963/2026 |

## Histórico Git

O repositório usa commits para representar a cronologia oficial:

- **198.139 commits** (1 Initialize + 198.138 leis)
- **Ordem cronológica**: 1988-01-01 → 2026-04-15
- **Data de cada commit** = data de publicação no DOU

```bash
# Ver as primeiras leis de 1988
git log --reverse --oneline | head -20

# Ver leis publicadas em uma data específica
git log --after="1999-07-22" --before="1999-07-23" --oneline

# Contar leis por ano
git log --format="%ci" | cut -d' ' -f1 | cut -d'-' -f1 | sort | uniq -c
```

## Período

| Ano | Leis aprox. |
|-----|-------------|
| 1988–1999 | ~30.000 |
| 2000–2009 | ~40.000 |
| 2010–2019 | ~60.000 |
| 2020–2026 | ~68.000 |

**Total**: 198.138 normas federais.

## Fonte de dados

Dados do [LexML Brasil](https://www.lexml.gov.br) — rede colaborativa para legislação brasileira.

- Portal de Dados Abertos do Governo Federal
- Diário Oficial da União (DOU)
- Câmara dos Deputados
- Senado Federal

## Legalize

Este repositório segue o formato [Legalize SPEC](https://github.com/legalize-dev/legalize/blob/main/SPEC.md) — legislação como código, versionada, acessível.

## Contribuir

Encontrou erro nos metadados? Abra uma issue com:
- Identificador do arquivo
- Problema encontrado
- Fonte oficial corretiva

## Autor

Criado por [danalec](https://github.com/danalec).

Baseado no layout do projeto [Legalize](https://github.com/legalize-dev/legalize).

## Licença

Conteúdo legislativo: domínio público (fontes oficiais).

Estrutura e ferramentas: [BSD 3-Clause](LICENSE)

---

[danalec](https://github.com/danalec) · [legalize.dev](https://legalize.dev)