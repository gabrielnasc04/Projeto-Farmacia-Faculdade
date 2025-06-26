Tabela de frequências – vendas por categoria 

SELECT categoria_produto AS Categoria, COUNT(*) AS Quantidade_de_Vendas 
FROM vendas 
GROUP BY categoria_produto 
ORDER BY Quantidade_de_Vendas DESC; 

b. Gráfico de Barras – Produtos Vendidos por Semana 

SELECT WEEK(data_venda) AS Semana, SUM(quantidade) AS Total_Vendidos 
FROM vendas 
GROUP BY WEEK(data_venda) 
ORDER BY Semana; 

c. Relatório de Fornecedores x Produtos 

SELECT f.nome AS Fornecedor, COUNT(p.id) AS Produtos_Cadastrados 
FROM fornecedores f 
JOIN produtos p ON p.fornecedor_id = f.id 
GROUP BY f.nome;
