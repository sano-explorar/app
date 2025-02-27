Este notebook implementa uma abordagem de análise de mediação causal para entender os mecanismos pelos quais intervenções afetam os níveis de ansiedade pós-intervenção. Utilizando a estrutura MoE (Mixture of Experts), o notebook examina especificamente o papel mediador da ansiedade pré-intervenção na relação entre a atribuição de grupo e os resultados de ansiedade.

## Funcionalidades

O notebook segue um fluxo de trabalho abrangente para análise de dados de intervenção para ansiedade:

1. **Carregamento e Validação de Dados**: Carrega dados sintéticos de intervenção para ansiedade, valida sua estrutura, conteúdo e tipos de dados.

2. **Pré-processamento de Dados**: Realiza codificação one-hot da coluna de grupo e escala características numéricas. Renomeia colunas para compatibilidade com a biblioteca statsmodels.

3. **Análise de Mediação Causal**: Utiliza statsmodels para realizar análise de mediação causal, estimando efeitos diretos e indiretos da intervenção.

4. **Análise de Valores SHAP**: Quantifica a importância das características no contexto da mediação, ajudando a compreender as contribuições relativas das variáveis.

5. **Visualização de Dados**: Gera gráficos KDE, Violin, Coordenadas Paralelas e Hipergrafos para representar visualmente os padrões nos dados.

6. **Resumo Estatístico**: Realiza análise bootstrap e gera estatísticas resumidas para avaliar a confiabilidade dos resultados.

7. **Relatório de Insights com LLM**: Sintetiza descobertas usando Grok, Claude e Grok-Enhanced, enfatizando a análise de mediação.

## Requisitos

O notebook requer as seguintes bibliotecas Python:

- pandas
- matplotlib
- seaborn
- networkx
- scikit-learn
- plotly
- scipy
- statsmodels
- shap

A instalação pode ser realizada com:

```python
!pip install pandas matplotlib seaborn networkx scikit-learn plotly scipy statsmodels shap
```

## Estrutura do Código

### Constantes e Configurações

- Define ambiente (Colab ou local)
- Estabelece caminhos de saída
- Define colunas importantes (IDs de participantes, grupos, medidas de ansiedade)
- Configurações de modelos LLM
- Parâmetros visuais

### Funções Auxiliares

O notebook contém várias funções auxiliares organizadas por categoria:

**Gerenciamento de Dados**:
- `create_output_directory`: Cria diretório de saída
- `load_data_from_synthetic_string`: Carrega dados de uma string CSV
- `validate_dataframe`: Valida a estrutura e conteúdo do DataFrame
- `preprocess_data`: Pré-processa dados para análise

**Análise Causal**:
- `perform_causal_mediation_analysis`: Executa análise de mediação causal
- `calculate_shap_values`: Calcula e visualiza valores SHAP

**Visualização**:
- `create_kde_plot`: Cria gráfico de densidade kernel
- `create_violin_plot`: Cria gráfico violin por grupo
- `create_parallel_coordinates_plot`: Cria gráfico de coordenadas paralelas
- `visualize_hypergraph`: Visualiza hipergrafo de relações entre participantes

**Análise Estatística**:
- `perform_bootstrap`: Realiza análise bootstrap
- `save_summary`: Salva estatísticas resumidas

**Integração com LLM**:
- `analyze_text_with_llm`: Analisa texto com modelos de linguagem grandes
- `generate_insights_report`: Gera relatório de insights

### Fluxo Principal de Execução

O script principal segue um fluxo lógico:

1. Cria diretório de saída
2. Carrega e valida dados sintéticos
3. Pré-processa dados para análise
4. Realiza análise de mediação causal
5. Executa análise SHAP
6. Cria visualizações
7. Realiza análise bootstrap
8. Salva estatísticas resumidas
9. Gera relatório de insights usando LLMs

## Dados

O notebook utiliza um conjunto de dados sintético incorporado no código, que contém:
- IDs de participantes
- Atribuições de grupo (Grupo A, Grupo B, Controle)
- Níveis de ansiedade pré-intervenção (0-10)
- Níveis de ansiedade pós-intervenção (0-10)

## Saídas

O notebook gera várias saídas no diretório especificado:
- Resultados da análise de mediação causal
- Gráfico resumo SHAP
- Visualizações (KDE, Violin, Coordenadas Paralelas, Hipergrafo)
- Estatísticas resumidas
- Relatório de insights integrado

## Uso

O notebook está configurado para ser executado diretamente, com parâmetros e dados predefinidos. Para uso personalizado, substitua o conjunto de dados sintético por dados reais e ajuste os parâmetros conforme necessário.

## Autor

Hélio Craveiro Pessoa Júnior
