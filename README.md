# 🚖 Urban Routes - Garantia de Qualidade (QA): Testes de Regressão & Design de Testes

## 🎯 Objetivo do Projeto
O objetivo principal deste projeto foi garantir a estabilidade e a qualidade do ecossistema do **Urban Routes** — uma aplicação que calcula rotas, tempos e custos de viagem para múltiplos meios de transporte. 

O trabalho foi dividido em duas grandes etapas estratégicas de Quality Assurance:
1. **Execução de Testes de Regressão:** Validar as funcionalidades existentes do núcleo do sistema para garantir que novas atualizações não introduziram defeitos na experiência do utilizador.
2. **Design de Testes (Particionamento por Equivalência & Análise de Valores-Limite):** Projetar cenários de testes exaustivos e robustos para o formulário crítico de "Adicionar carteira de motorista", mitigando falhas antes da codificação/entrega do recurso.

---

## 🛠️ Ferramentas e Tecnologias Utilizadas
* **Ambiente de Testes:** Google Chrome DevTools (Versão mais recente) para inspeção de elementos e análise de logs.
* **Gestão e Documentação de Testes:** Google Sheets para criação de matrizes de testes, mapeamento de classes e execução de Casos de Teste (TCs).
* **Gestão de Defeitos:** Estruturação de Relatórios de Bugs seguindo o padrão de mercado (Severidade, Prioridade, Passos para Reproduzir, Resultados Esperados vs. Reais).

---

## 🚀 Resultados Alcançados

### 1. Testes de Regressão & Mapeamento de Bugs
* Execução completa da suite de testes de regressão fornecida pela equipa de QA.
* Identificação e documentação detalhada de bugs críticos na aplicação que degradavam a experiência do utilizador.
* Atribuição de status padronizados (`Aprovado`, `Reprovado`) e classificação rigorosa de prioridades (Bloqueador, Crítico, Grande, Pequeno, Trivial).

### 2. Design de Testes (Carteira de Motorista)
* **Mapeamento de Campos:** Definição analítica de cenários para os campos `Nome`, `Sobrenome` e `Data de Nascimento`.
* **Técnicas Aplicadas:** Divisão rigorosa em classes de equivalência (positivas e negativas) e identificação de valores-limite para testar as fronteiras de aceitação do sistema.
* **Criação de Casos de Teste:** Escrita de casos de teste detalhados e estruturados focados na validação e comportamento do campo `Nome`.

📊 **[Aceda aqui à Planilha Completa de Engenharia de QA (Google Sheets)]((https://docs.google.com/spreadsheets/d/104IHqsd_J8Ovb3NkatfAO4b8RxYdNxMQ/edit?usp=sharing&ouid=111965607442582328407&rtpof=true&sd=true) e (https://docs.google.com/spreadsheets/d/12IzLQLgglVCYshE_7mCcn4xm9txQwji_/edit?usp=sharing&ouid=111965607442582328407&rtpof=true&sd=true)**

### 📊 Matriz de Design de Testes: Valores-Limite para o Campo "Nome"

Para garantir a robustez do formulário de "Adicionar carteira de motorista", foram aplicadas as técnicas de **Particionamento por Equivalência (EP)** e **Análise de Valores-Limite (BVA)** no campo "Nome" (limites regulamentares de 2 a 30 caracteres):

| ID | Cenário de Teste | Valor de Entrada | Tamanho | Classe de Equivalência | Resultado Esperado |
| :--- | :--- | :--- | :---: | :--- | :--- |
| **TC-01** | Limite Inferior Inválido (Fronteira) | `"A"` | 1 car. | Classe Negativa (Curto) | **Erro:** Mensagem de validação visível |
| **TC-02** | Limite Inferior Válido (Fronteira) | `"An"` | 2 car. | Classe Positiva (Válido Mínimo) | **Sucesso:** Campo aceite com sucesso |
| **TC-03** | Valor Típico Válido (Meio da Classe) | `"Marcos"` | 6 car. | Classe Positiva (Válido) | **Sucesso:** Campo aceite com sucesso |
| **TC-04** | Limite Superior Válido (Fronteira) | `"Carlos Eduardo Santos Silva Pere"` | 30 car. | Classe Positiva (Válido Máximo) | **Sucesso:** Campo aceite com sucesso |
| **TC-05** | Limite Superior Inválido (Fronteira) | `"Carlos Eduardo Santos Silva Perei"` | 31 car. | Classe Negativa (Longo) | **Erro:** Bloqueio de inserção ou mensagem de erro |
| **TC-06** | Caracteres Especiais Inválidos | `"Marcos#123"` | 10 car. | Classe Negativa (Caractere Inválido) | **Erro:** Mensagem de erro (apenas letras permitidas) |
| **TC-07** | Campo Totalmente Vazio | `""` | 0 car. | Classe Negativa (Obrigatório) | **Erro:** Mensagem de campo obrigatório |

---

## 🧠 Competências Adquiridas e Aprendizados
Durante o ciclo de vida deste projeto, consolidei competências fundamentais da engenharia de qualidade de software:
* **Mentalidade Analítica de QA:** Capacidade de diferenciar de forma clara e objetiva o comportamento esperado do comportamento real do software sob teste.
* **Técnicas de Caixa Preta:** Domínio prático de Particionamento por Equivalência (EP) e Análise de Valores-Limite (BVA) para reduzir o número de testes necessários mantendo a máxima cobertura de código.
* **Documentação Técnica Padronizada:** Habilidade na escrita de relatórios de bugs claros, objetivos e acionáveis para os programadores (Passos para reproduzir com clareza).

---

## 📈 Melhorias Futuras
Para os próximos passos de evolução desta aplicação, planeia-se:
* **Automação de Testes (E2E):** Automatizar os fluxos críticos de regressão mapeados utilizando Python e Selenium WebDriver.
* **Testes de API:** Integrar validações de contratos e respostas de endpoints via Postman para o algoritmo de cálculo de rotas.
