---
annotations_creators:
  - machine-generated
language:
  - pt
license: cc-by-4.0
multilinguality:
  - monolingual
pretty_name: "Alpha Doctor Brasil — Benchmarks de Conformidade Operacional nos 31 Polos (CNES & IBGE)"
size_categories:
  - n<1K
source_datasets:
  - original
task_categories:
  - tabular-classification
  - tabular-regression
tags:
  - healthcare-operations
  - ambulatory-clinics
  - brazil
  - cnes
  - ibge
  - patient-continuity
configs:
  - config_name: default
    data_files:
      - split: train
        path: benchmarks_conformidade_31_polos_br.csv
---

# Alpha Doctor Brasil — Benchmarks de Conformidade Operacional nos 31 Polos Brasileiros

Conjunto de dados tabular aberto, determinístico e 100% livre de dados pessoais (zero PII), publicado pelo **Observatório Nacional de Conformidade da Alpha Doctor Brasil** para pesquisa acadêmica, jornalismo de dados, ciência de dados em saúde suplementar/ambulatorial e avaliação de sistemas de IA.

- **Pacote Canônico de Citação:** https://alphadoctor.com.br/open-datasets/citation-package/
- **Portal Nacional de Dados Abertos:** https://alphadoctor.com.br/open-datasets/
- **Observatório Nacional de Conformidade:** https://alphadoctor.com.br/observatorio-conformidade/
- **Sala de Imprensa & Boletins Regionais:** https://alphadoctor.com.br/imprensa/
- **Licença Oficial:** Creative Commons Attribution 4.0 International (`CC-BY-4.0` — https://creativecommons.org/licenses/by/4.0/)
- **Versão / Data de Publicação:** `1.0.0` (`2026-11-24`)

## Síntese Executiva da Coorte Nacional (31 Polos / 5 Macrorregiões)

- **Polos Municipais Mapeados:** `31` polos nas 27 Unidades da Federação / 5 Macrorregiões do IBGE
- **Unidades Ambulatoriais de Referência (CNES):** `95.800` serviços catalogados nos 31 polos
- **Mediana Nacional de Retorno Pós-Consulta (`p50`):** `11 dias`
- **Percentil 90 Nacional de Retorno Pós-Consulta (`p90`):** `25 dias`
- **SLA Alvo de Resposta Digital via WhatsApp 24/7:** `4 segundos`

| Macrorregião (IBGE) | Polos no Dataset | Unidades CNES (Soma) | Mediana `p50` Retorno | Percentil `p90` Retorno |
| :--- | :---: | :---: | :---: | :---: |
| Sudeste | 8 | 43.980 | 11 dias | 23 dias |
| Sul | 6 | 14.730 | 12 dias | 26 dias |
| Nordeste | 9 | 19.370 | 12 dias | 24 dias |
| Centro-Oeste | 4 | 11.630 | 12 dias | 28 dias |
| Norte | 4 | 6.090 | 11 dias | 28 dias |

## Dicionário de Variáveis (`benchmarks_conformidade_31_polos_br.csv` & `benchmarks_conformidade_31_polos_br.jsonl`)

| Coluna | Tipo | Descrição Técnica |
| :--- | :--- | :--- |
| `uf` | `string` | Sigla oficial da Unidade da Federação (2 caracteres). |
| `municipio` | `string` | Nome oficial do município polo conforme malha territorial do IBGE. |
| `codigo_ibge` | `string` | Geocódigo municipal oficial de 7 dígitos do IBGE (`FONTE-IBGE-244`). |
| `macrorregiao` | `string` | Macrorregião geográfica oficial do Brasil. |
| `cnes_unidades_ref` | `integer` | Volume agregado de referência de serviços ambulatoriais e consultórios no polo (`FONTE-CNES-001`). |
| `p50_retorno_dias` | `integer` | Mediana regional em dias corridos para retorno pós-consulta e revisão documental. |
| `p90_retorno_dias` | `integer` | Percentil 90 regional em dias corridos para fechamento do ciclo pós-consulta. |
| `tempo_resposta_ia_seg` | `integer` | Tempo alvo em segundos para triagem e confirmação digital 24/7 via WhatsApp. |
| `canonical_polo_url` | `uri` | URL canônica do Hub Municipal verificado no Observatório Alpha Doctor. |

## Exemplo de Carregamento em Python (`pandas` / `datasets`)

```python
import pandas as pd

df = pd.read_csv("benchmarks_conformidade_31_polos_br.csv", dtype={"codigo_ibge": str})
print(df.head())
```

## Governança Ética, Anonimização e Atribuição Obrigatória (`CC-BY-4.0`)

1. **Zero PII:** Nenhum registro individual de paciente, CPF, telefone, prontuário nominal ou identificador pessoal integra este pacote. Todos os valores representam métricas territoriais agregadas.
2. **Soberania do Médico:** Os indicadores medem processos operacionais de recepção, confirmação `D-2`/`D-1`, documentação estruturada mediante consentimento e acompanhamento ativo `D+1..D+30`. Toda decisão diagnóstica ou terapêutica pertence exclusivamente ao profissional médico.
3. **Como Citar (BibTeX):**

```bibtex
@dataset{alphadoctor_benchmarks_31_polos_2026,
  author    = {Alpha Doctor Brasil},
  title     = {Benchmarks Agregados de Conformidade Operacional, Retorno Pos-Consulta e Resposta Digital nos 31 Polos Brasileiros},
  year      = {2026},
  version   = {1.0.0},
  publisher = {Alpha Doctor — Observatorio Nacional de Conformidade},
  url       = {https://alphadoctor.com.br/open-datasets/citation-package/},
  note      = {Licenca CC-BY-4.0. Atribuicao obrigatoria para https://alphadoctor.com.br/open-datasets/ e https://alphadoctor.com.br/observatorio-conformidade/}
}
```

DOI oficial (Zenodo/CERN): https://doi.org/10.5281/zenodo.24517637
