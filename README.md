# BDAnimais

## ETAPA 1
 -- Criando a tabela  "Animais" com as colunas, ID, NOME, NASC , PESO  e COR. --
 
CREATE TABLE Animais (
  ID INT,
  NOME VARCHAR(50),
  NASC DATE,
  PESO DECIMAL(10, 2),
  COR VARCHAR(50)
);

-- inserindo dados na tabela "Animais" --

insert into Animais values (01, 'Ágata', date'2016-06-06', 13.9, 'branco');
insert into Animais values (02, 'Félix', date'2016-06-06', 14.3, 'preto');
insert into Animais values (03, 'Tom', date'2013-02-08', 11.2, 'azul');
insert into Animais values (04, 'Garfield', date'2015-07-06', 17.1, 'laranja');
insert into Animais values (05, 'Frajola', date'2013-08-01', 13.7, 'preto');
insert into Animais values (06, 'Manda-chuva', date'2012-02-03', 12.3, 'amarelo');
insert into Animais values (07, 'Snowball', date'2014-04-06', 13.2, 'preto');
insert into Animais values (10, 'Ágata', date'2015-08-03', 11.9, 'azul');
insert into Animais values (11, 'Gato de Botas', date'2012-12-10', 11.6, 'amarelo');
insert into Animais values (12, 'Kitty', date'2020-04-06', 11.6, 'amarelo');
insert into Animais values (13, 'Milu', date'2013-02-04', 17.9, 'branco');
insert into Animais values (14, 'Pluto', date'2012-01-03', 12.3, 'amarelo');
insert into Animais values (15, 'Pateta', date'2015-05-01', 17.7, 'preto');
insert into Animais values (16, 'Snoopy', date'2013-07-02', 18.2, 'branco');
insert into Animais values (17, 'Rex', date'2019-11-03', 19.7, 'bege');
insert into Animais values (20, 'Bidu', date'2012-09-08', 12.4, 'azul');
insert into Animais values (21, 'Dum Dum', date'2015-04-06', 11.2, 'laranja');
insert into Animais values (22, 'Muttley', date'2011-02-03', 14.3, 'laranja');
insert into Animais values (23, 'Scooby', date'2012-01-02', 19.9, 'marrom');
insert into Animais values (24, 'Rufus', date'2014-04-05', 19.7, 'branco');
insert into Animais values (25, 'Rex', date'2021-08-19', 19.7, 'branco');
insert into Animais values (25, 'Cerato', date'2021-08-19', 19.7, 'branco');
insert into Animais values (25, 'Carlos', date'2021-08-19', 19.7, 'marrom');
insert into Animais values (25, 'Roberto', date'2021-08-20', 31.2, 'roxo');
insert into Animais values (25, 'Clayton', date'2021-12-28', 31.2, 'roxo');
insert into Animais values (25, 'Rircardo', date'2021-12-22', 31.2, 'roxo');

-- Mostra todos os animais inseridos --

SELECT * from Animais;

-- Mostra os animais da tabela onde o PESO é maior que 13.1. --

SELECT * FROM Animais WHERE PESO > 13.1;

-- Mostra os animais com a data de nascimento entre o intervalo de 1 de fevereiro de 2015 a 31 de dezembro de 2015. --

SELECT * FROM Animais Where NASC >= "2015-02-01" AND NASC <= "2015-12-31";
SELECT * FROM Animais Where NASC BETWEEN "2015-02-01" AND "2015-12-31";

--  Mostra os animais que tem a cor "branco" e o peso é maior que 15.0. --

SELECT * FROM Animais WHERE COR = "branco" AND PESO > 15.0;

-- Mostra os animais cujos nomes começam com a letra "b". --

SELECT NOME, COR, PESO FROM Animais Where NOME LIKE "b%";

--  Mostra os nomes, cores e pesos dos animais com cores "vermelho", "amarelo", "marrom" ou "laranja". --

SELECT NOME, COR, PESO FROM Animais  
WHERE COR = "vermelho" OR COR = "amarelo" OR  COR = "marrom" OR COR = "laranja";

-- Mostra os animais ordenados por data de nascimento em ordem decrescente. --

SELECT NOME, COR, NASC, PESO FROM Animais ORDER BY NASC DESC;

-- Mostras os animais cujos nomes começam com "C" e cuja cor não é "branco". --
SELECT * FROM Animais WHERE NOME LIKE "C%" AND COR != "branco";

-- Mostra os animais onde o nome contém a sequência "ba" em qualquer posição. --
SELECT * FROM Animais WHERE NOME LIKE "%ba%";

-- Mostra os animais cujo peso está entre 13.0 e 15.0. --

SELECT * FROM Animais WHERE PESO >= 13.0 AND PESO <= 15.0;

-- Mostra os animais com peso maior ou igual a 30.0 e que são da cor "amarelo", ou da cor "roxo" e com data de nascimento após 31 de dezembro de 2012. --

SELECT * FROM Animais 
WHERE PESO >= 30.0 AND COR = "amarelo" OR COR = "roxo" AND NASC > "2012-12-31";


/*DESAFIO 1 - Capricornianos */

-- Mostra os animais cuja data de nascimento corresponde a 1º a 20 de janeiro ou 22 a 31 de dezembro. --

SELECT * FROM Animais 
WHERE MONTH(NASC) = 1 AND DAY(NASC) BETWEEN 1 AND 20 OR MONTH(NASC) = 12 
AND DAY(NASC) BETWEEN 22 AND 31;

/*DESAFIO 2 - Nomes compostos*/

-- Mostra os animais cujos nomes contêm um espaço em branco ou seja são compostos. --

SELECT * FROM Animais WHERE NOME LIKE "% %";
