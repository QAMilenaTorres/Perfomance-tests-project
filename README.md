# JMeter Performance Tests

Este repositório contém exemplos de testes de performance usando **Apache JMeter** para diferentes cenários de requisições HTTP.

---

## **Test Plans Incluídos**

### 1️⃣ Teste Básico - JSON Placeholder

- **URL:** `https://jsonplaceholder.typicode.com/posts`
- **Thread Group:**
  - Usuários: 50
  - Ramp-up: 1 segundo
  - Loops: 2
- **Objetivo:** Testar requisições GET para posts, medir tempo de resposta e taxa de erro.
- **Resultados esperados:**
  - Response Time médio < 500 ms
  - Error % < 5%
  - Throughput: ~50 req/sec

### 2️⃣ Teste Médio - Example.com

- **URL:** `http://example.com/`
- **Thread Group:**
  - Usuários: 15
  - Ramp-up: 3 segundos
  - Loops: 6
- **Objetivo:** Testar estabilidade do servidor com múltiplas requisições consecutivas.
- **Resultados esperados:**
  - Response Time médio < 700 ms
  - Error % < 2%
  - Throughput: ~10 req/sec

### 3️⃣ Teste de Imagem - HTTP Cat

- **URL:** `https://http.cat/200.jpg`
- **Thread Group:**
  - Usuários: 100
  - Ramp-up: 2 segundos
  - Loops: 1
- **Objetivo:** Testar download de arquivos estáticos e medir latência, banda e erros.
- **Resultados esperados:**
  - Response Time médio < 800 ms
  - Error % < 1%
  - Throughput: ~100 req/sec

---

## **Listeners Usados**

- **View Results Tree:** Visualização detalhada de cada requisição
- **Summary Report:** Métricas de desempenho resumidas (Average, Min, Max, Error %, Throughput)
- **Graph Results:** Gráfico visual da performance do teste

---

## **Como Rodar**

1. Abra o **JMeter**.
2. Importe o arquivo `.jmx` do teste.
3. Configure os **Thread Groups** conforme desejado.
4. Clique em **Start** e monitore os resultados nos **Listeners**.
5. Analise:
   - **Response Time**: tempo médio para cada requisição
   - **Throughput**: requisições por segundo
   - **Error %**: percentual de requisições com erro

---

## **Observações**

- Estes testes são **exemplos** para aprendizado e prática com JMeter.
- Os endpoints utilizados são públicos (`jsonplaceholder.typicode.com`, `example.com`, `http.cat`) e seguros para testes.
- Ideal para treinar **teste de carga, stress e performance** antes de aplicar em projetos reais.
