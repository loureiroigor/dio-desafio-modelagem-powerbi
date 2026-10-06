Repositório criado para o desafio de projeto da DIO. O objetivo foi transformar uma única tabela plana (*Financial Sample*) num modelo relacional em estrela (*Star Schema*), utilizando o Power Query e linguagem DAX.

## O que foi feito:

- **Preparação e Backup:** Importação da base original e criação da consulta `Financials_origem` (oculta para backup).
- **Tabelas de Dimensão (Power Query):** 
  - Criação das tabelas `D_Produtos`, `D_Produtos_Detalhes`, `D_Descontos` e `D_Detalhes` através da duplicação de consultas, seleção de colunas e remoção de duplicados.
  - Utilização da funcionalidade **Agrupar Por** para calcular métricas (Média, Mediana, Máximo, Mínimo) por produto.
  - Geração de chaves substitutas (`ID_Produto`) utilizando **Colunas Condicionais**.
- **Tabela de Factos:** 
  - Construção da `F_Vendas` centralizando as métricas de negócio.
  - Criação de uma *Surrogate Key* (`SK_ID`) através da adição de uma coluna de índice.
- **Tabela de Calendário (DAX):** 
  - Criação da tabela `D_Calendario` utilizando a função DAX `CALENDARAUTO()` para suportar análises temporais.
- **Modelagem:** Configuração dos relacionamentos no Power BI, garantindo que todas as dimensões se ligam diretamente à tabela de factos (Star Schema).

## Arquivos no Repositório:
- Arquivo `.pbix` com o modelo de dados finalizado.
- Imagem do diagrama em estrela (Star Schema).
