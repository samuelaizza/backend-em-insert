# Evidências - INSERT, UPDATE e DELETE no banco db_em 
## Identificação 
Nome: Samuel Ferreira Aizza
Turma: 3°B
Data: 
--- 
# 1. SELECT final - Leituras do dia 2026-04-04 
Execute no DBeaver:
Trilha CRUD SQL - db_em - DBeaver 
```sql 
SELECT * 
FROM leituras 
WHERE timestamp >= '2026-04-04'  AND timestamp < '2026-04-05' 
ORDER BY timestamp ASC; 
``` 
Cole abaixo a saída obtida: 
9	EM-ARACATUBA-01	2026-04-04 08:00:00.000 -0300	23.4	76.2
10	EM-ARACATUBA-01	2026-04-04 09:00:00.000 -0300	25.2	72.0
11	EM-ARACATUBA-01	2026-04-04 10:00:00.000 -0300	25.9	70.5
--- 
# 2. SELECT final - Conferência do UPDATE Execute no DBeaver: 
```sql 
SELECT * 
FROM leituras 
WHERE station_id = 'EM-ARACATUBA-01'  AND timestamp = '2026-04-04 09:00:00'; ``` 
Cole abaixo a saída obtida: 
10	EM-ARACATUBA-01	2026-04-04 09:00:00.000 -0300	25.2	72.0
--- 
# 3. SELECT final - Conferência do DELETE Execute no DBeaver: 
```sql 
SELECT * 
FROM leituras 
WHERE station_id = 'EM-ARACATUBA-01'  AND timestamp = '2026-04-04 11:00:00'; ``` 
Cole abaixo a saída obtida: 
```Não teve registro.

Se o DELETE foi feito corretamente, esse SELECT não deverá retornar registros. --- 
# 4. SELECT final - Todas as leituras ordenadas 
Execute no DBeaver: 
```sql 
SELECT * 
FROM leituras 
ORDER BY id ASC; 
``` 
Cole abaixo a saída obtida: 
1	EM-ARACATUBA-01	2026-04-01 08:00:00.000 -0300	24.5	72.1
2	EM-ARACATUBA-01	2026-04-01 09:00:00.000 -0300	25.8	69.4
3	EM-ARACATUBA-01	2026-04-01 10:00:00.000 -0300	27.2	65.8
4	EM-ARACATUBA-01	2026-04-02 08:00:00.000 -0300	23.8	73.5
5	EM-ARACATUBA-01	2026-04-02 09:00:00.000 -0300	24.6	71.2
6	EM-ARACATUBA-01	2026-04-02 10:00:00.000 -0300	25.4	68.9
7	EM-ARACATUBA-01	2026-04-02 11:00:00.000 -0300	26.1	66.4
8	EM-ARACATUBA-01	2026-04-02 12:00:00.000 -0300	27.0	63.8
9	EM-ARACATUBA-01	2026-04-04 08:00:00.000 -0300	23.4	76.2
10	EM-ARACATUBA-01	2026-04-04 09:00:00.000 -0300	25.2	72.0
11	EM-ARACATUBA-01	2026-04-04 10:00:00.000 -0300	25.9	70.5
--- 
# 5. Teste pela API 
Acesse no navegador: 
http://localhost:3000/api/leituras/data/2026-04-04 

Cole abaixo o resultado retornado pela API: 
{
  "dataPesquisada": "2026-04-04",
  "total": 3,
  "leituras": [
    {
      "id": 9,
      "station_id": "EM-ARACATUBA-01",
      "timestamp": "2026-04-04T11:00:00.000Z",
      "temperature_c": 23.4,
      "humidity_pct": 76.2
    },
    {
      "id": 10,
      "station_id": "EM-ARACATUBA-01",
      "timestamp": "2026-04-04T12:00:00.000Z",
      "temperature_c": 25.2,
      "humidity_pct": 72
    },
    {
      "id": 11,
      "station_id": "EM-ARACATUBA-01",
      "timestamp": "2026-04-04T13:00:00.000Z",
      "temperature_c": 25.9,
      "humidity_pct": 70.5
    }
  ]
}
--- 
# 6. Conclusão 
INSERT: usado para adicionar novos dados em uma tabela do banco de dados.
Exemplo: cadastrar um novo usuário.

UPDATE: usado para alterar informações que já existem na tabela.
Exemplo: mudar a senha ou o nome de um usuário.

DELETE: usado para remover dados da tabela.
Exemplo: excluir um cadastro de usuário. 

