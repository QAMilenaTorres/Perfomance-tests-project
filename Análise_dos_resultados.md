# JMeter Performance Tests - Análise de Resultados

Este arquivo contém a análise feita pelo QA que executou os testes com os resultados obtidos pelos sites abaixo.
---

## **1️⃣ Teste Básico - JSON Placeholder**

| Métrica              | Resultado        | Observação                                   |
|----------------------|----------------|---------------------------------------------|
| Usuários (Threads)    | 50             | Ramp-up: 1s, Loops: 2                       |
| Tempo Médio de Resposta | 119 ms         | Dentro do esperado (<500 ms)                 |
| Throughput           | 0.83 req/sec    | Boa taxa considerando volume de usuários     |
| Error %              | 10%             | Alguns erros, possível instabilidade do endpoint |

**Análise:**  
O teste mostrou latência baixa, mas um pouco de erro (%10). Pode ser devido ao endpoint público ou requisições simultâneas. Ideal para treinar análise de throughput e tempo de resposta.

---

## **2️⃣ Teste Médio - Example.com**

| Métrica              | Resultado        | Observação                                   |
|----------------------|----------------|---------------------------------------------|
| Usuários (Threads)    | 15             | Ramp-up: 3s, Loops: 6                       |
| Tempo Médio de Resposta | 1401 ms        | Endpoint simples, tempo alto por múltiplas iterações |
| Throughput           | 0.10 req/sec    | Baixo, esperado para teste com loops longos |
| Error %              | 0%              | Nenhum erro detectado                        |

**Análise:**  
Apesar do tempo de resposta alto, não houve erros. Teste útil para treinar loops e ver impacto de múltiplas iterações em servidores simples.

---

## **3️⃣ Teste de Imagem - HTTP Cat**

| Métrica              | Resultado        | Observação                                   |
|----------------------|----------------|---------------------------------------------|
| Usuários (Threads)    | 100            | Ramp-up: 2s, Loops: 1                       |
| Tempo Médio de Resposta | 2093 ms        | Download de arquivo relativamente pesado    |
| Throughput           | ~100 req/sec    | Alta taxa, servidor suporta bem a carga     |
| Error %              | 0%              | Sem erros, teste de download bem-sucedido  |

**Análise:**  
Teste de arquivos estáticos mostrou latência maior devido ao tamanho da imagem, mas não houve erros. Excelente para praticar testes de download e medir throughput.

---

## **Listeners Usados**

- **View Results Tree:** Visualização detalhada de cada requisição  
- **Summary Report:** Métricas resumidas (Average, Min, Max, Error %, Throughput)  
- **Graph Results:** Gráfico visual da performance do teste  

---

## **Conclusão**

- Testes demonstram diferentes tipos de cenários: **GET simples, múltiplas iterações e download de arquivos**.  
- Métricas essenciais para análise: **Response Time, Throughput e Error %**.  
- Ideal para treinar **teste de carga, stress e performance** com JMeter em endpoints públicos.
