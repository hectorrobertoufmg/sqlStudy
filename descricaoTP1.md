# Trabalho da disciplina "Introdução à banco de dados"

### Questões que preciso desenvolver:

20170.

### A0 - Resposta

SELECT nome
FROM Personagens
WHERE planeta = 'Tatooine';

---

### A1 - Resposta

SELECT F.nome, F.planeta, N.nome, N.custo_em_creditos 
FROM Fabricantes AS F JOIN Naves AS N ON F.nome = N.fabricante
WHERE custo_em_creditos < 500000 and planeta = 'Naboo';

### A2 - Resposta

SELECT E.nome, E.classificacao, P.nome, P.clima
FROM Planetas AS P JOIN Especies AS E ON P.nome = E.planeta
WHERE E.classificacao = 'reptiliano' AND (P.clima = 'arido' OR P.clima = 'umido');

Ambas as consultas retornarão a mesma resposta, a dúvida é se há uma diferença na eficiena.

SELECT nome, classificacao, planeta
FROM Especies
WHERE classificacao = 'reptiliano' AND planeta IN (SELECT nome
												   FROM Planetas
												   WHERE clima = 'arido' OR clima = 'umido');

### A3 - Resposta

SELECT P.nome
FROM Fabricantes AS F JOIN Planetas AS P ON F.planeta = P.nome
WHERE F.produto = 'ambos';

### A7 - Resposta

SELECT modelo
FROM Naves
WHERE passageiros > tripulacao;

