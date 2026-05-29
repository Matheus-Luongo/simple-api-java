<img width="1053" height="763" alt="image" src="https://github.com/user-attachments/assets/10838981-5ef7-4f1c-8a61-fe35c450d3f7" />
<img width="1018" height="698" alt="image" src="https://github.com/user-attachments/assets/6ff3adb6-8a8c-4685-bfe3-43773f3a6d27" />
//DROP TABLE dept PURGE;
//DROP TABLE emp PURGE;

/*CREATE TABLE dept( -- cria a tabela dept (departamento)
  deptno NUMBER(2,0), -- cria a coluna deptno (numero de departamento e define como numero de até dois digitos, sem virgula)
  dname  VARCHAR2(14), -- cria a coluna dname (nome do departamento e define como caracters variaveis)
  loc    VARCHAR2(13), -- localizaçao 
  CONSTRAINT pk_dept PRIMARY KEY (deptno) -- cria uma regra chama pk_dept onde a coluna deptno é uma chave primaria (amarra outras tabelas que contenham a mesma coluna)
);
-- cmeça a popular a tabela com valores de acordo com a tabela
INSERT INTO dept VALUES(10, 'ACCOUNTING', 'NEW YORK');
INSERT INTO dept VALUES(20, 'RESEARCH', 'DALLAS');
INSERT INTO dept VALUES(30, 'SALES', 'CHICAGO');
INSERT INTO dept VALUES(40, 'OPERATIONS', 'BOSTON'); */

/*CREATE TABLE emp(
  empno    NUMBER(4,0),
  ename    VARCHAR2(10),
  job      VARCHAR2(9),
  mgr      NUMBER(4,0),
  hiredate DATE, -- cria a coluna hire date e define como data
  sal      NUMBER(7,2),
  comm     NUMBER(7,2),
  deptno   NUMBER(2,0),
  CONSTRAINT pk_emp PRIMARY KEY (empno),
  CONSTRAINT fk_deptno FOREIGN KEY (deptno) REFERENCES dept (deptno) -- cria uma regra chamada fk_deptno que define a coluna deptno como chave estrangeira e define ela como referencia da tabela dep chamando a coluna de mesmo nome
);
-- popula a tabela emp com os dados dos empregados
INSERT INTO EMP VALUES
        (7369, 'SMITH',  'CLERK',     7902,
        TO_DATE('17-DEZ-1980', 'DD-MON-YYYY'),  800, NULL, 20);
INSERT INTO EMP VALUES
        (7499, 'ALLEN',  'SALESMAN',  7698,
        TO_DATE('20-FEV-1981', 'DD-MON-YYYY'), 1600,  300, 30);
INSERT INTO EMP VALUES
        (7521, 'WARD',   'SALESMAN',  7698,
        TO_DATE('22-FEV-1981', 'DD-MON-YYYY'), 1250,  500, 30);
INSERT INTO EMP VALUES
        (7566, 'JONES',  'MANAGER',   7839,
        TO_DATE('2-ABR-1981', 'DD-MON-YYYY'),  2975, NULL, 20);
INSERT INTO EMP VALUES
        (7654, 'MARTIN', 'SALESMAN',  7698,
        TO_DATE('28-SET-1981', 'DD-MON-YYYY'), 1250, 1400, 30);
INSERT INTO EMP VALUES
        (7698, 'BLAKE',  'MANAGER',   7839,
        TO_DATE('1-MAI-1981', 'DD-MON-YYYY'),  2850, NULL, 30);
INSERT INTO EMP VALUES
        (7782, 'CLARK',  'MANAGER',   7839,
        TO_DATE('9-JUN-1981', 'DD-MON-YYYY'),  2450, NULL, 10);
INSERT INTO EMP VALUES
        (7788, 'SCOTT',  'ANALYST',   7566,
        TO_DATE('09-DEZ-1982', 'DD-MON-YYYY'), 3000, NULL, 20);
INSERT INTO EMP VALUES
        (7839, 'KING',   'PRESIDENT', NULL,
        TO_DATE('17-NOV-1981', 'DD-MON-YYYY'), 5000, NULL, 10);
INSERT INTO EMP VALUES
        (7844, 'TURNER', 'SALESMAN',  7698,
        TO_DATE('8-SET-1981', 'DD-MON-YYYY'),  1500,    0, 30);
INSERT INTO EMP VALUES
        (7876, 'ADAMS',  'CLERK',     7788,
        TO_DATE('12-JAN-1983', 'DD-MON-YYYY'), 1100, NULL, 20);
INSERT INTO EMP VALUES
        (7900, 'JAMES',  'CLERK',     7698,
        TO_DATE('3-DEZ-1981', 'DD-MON-YYYY'),   950, NULL, 30);
INSERT INTO EMP VALUES
        (7902, 'FORD',   'ANALYST',   7566,
        TO_DATE('3-DEZ-1981', 'DD-MON-YYYY'),  3000, NULL, 20);
INSERT INTO EMP VALUES
        (7934, 'MILLER', 'CLERK',     7782,
        TO_DATE('23-JAN-1982', 'DD-MON-YYYY'), 1300, NULL, 10); */

/* programação em bloco, o sql segue a estrutura de C onde dentro de um bloco (loop) é inserido o script
são instruções temporarias no banco, elas serão executadas e após isso descartadas
BEGIN
	NULL;
END;*/

/*CREATE TABLE emp(
  empno    NUMBER(4,0),
  ename    VARCHAR2(10),
  job      VARCHAR2(9),
  mgr      NUMBER(4,0),
  hiredate DATE,
  sal      NUMBER(7,2),
  comm     NUMBER(7,2),
  deptno   NUMBER(2,0),
  CONSTRAINT pk_emp PRIMARY KEY (empno), -- cria a regra chamada pk_emp onde empno será a chave primaria
  CONSTRAINT fk_deptno FOREIGN KEY (deptno) REFERENCES dept (deptno) -- cria a regra fk_deptno onde define deptno como chave estrangeira e a referencia a deptno 
);

-- popula a tabela
INSERT INTO EMP VALUES
        (7369, 'SMITH',  'CLERK',     7902,
        TO_DATE('17-DEZ-1980', 'DD-MON-YYYY'),  800, NULL, 20);
INSERT INTO EMP VALUES
        (7499, 'ALLEN',  'SALESMAN',  7698,
        TO_DATE('20-FEV-1981', 'DD-MON-YYYY'), 1600,  300, 30);
INSERT INTO EMP VALUES
        (7521, 'WARD',   'SALESMAN',  7698,
        TO_DATE('22-FEV-1981', 'DD-MON-YYYY'), 1250,  500, 30);
INSERT INTO EMP VALUES
        (7566, 'JONES',  'MANAGER',   7839,
        TO_DATE('2-ABR-1981', 'DD-MON-YYYY'),  2975, NULL, 20);
INSERT INTO EMP VALUES
        (7654, 'MARTIN', 'SALESMAN',  7698,
        TO_DATE('28-SET-1981', 'DD-MON-YYYY'), 1250, 1400, 30);
INSERT INTO EMP VALUES
        (7698, 'BLAKE',  'MANAGER',   7839,
        TO_DATE('1-MAI-1981', 'DD-MON-YYYY'),  2850, NULL, 30);
INSERT INTO EMP VALUES
        (7782, 'CLARK',  'MANAGER',   7839,
        TO_DATE('9-JUN-1981', 'DD-MON-YYYY'),  2450, NULL, 10);
INSERT INTO EMP VALUES
        (7788, 'SCOTT',  'ANALYST',   7566,
        TO_DATE('09-DEZ-1982', 'DD-MON-YYYY'), 3000, NULL, 20);
INSERT INTO EMP VALUES
        (7839, 'KING',   'PRESIDENT', NULL,
        TO_DATE('17-NOV-1981', 'DD-MON-YYYY'), 5000, NULL, 10);
INSERT INTO EMP VALUES
        (7844, 'TURNER', 'SALESMAN',  7698,
        TO_DATE('8-SET-1981', 'DD-MON-YYYY'),  1500,    0, 30);
INSERT INTO EMP VALUES
        (7876, 'ADAMS',  'CLERK',     7788,
        TO_DATE('12-JAN-1983', 'DD-MON-YYYY'), 1100, NULL, 20);
INSERT INTO EMP VALUES
        (7900, 'JAMES',  'CLERK',     7698,
        TO_DATE('3-DEZ-1981', 'DD-MON-YYYY'),   950, NULL, 30);
INSERT INTO EMP VALUES
        (7902, 'FORD',   'ANALYST',   7566,
        TO_DATE('3-DEZ-1981', 'DD-MON-YYYY'),  3000, NULL, 20);
INSERT INTO EMP VALUES
        (7934, 'MILLER', 'CLERK',     7782,
        TO_DATE('23-JAN-1982', 'DD-MON-YYYY'), 1300, NULL, 10);*/
        
/*DECLARE -- define constantes
		v_variavel varchar2(5); -- declara a "v_variavel como valores alfanumerico com até 5 caracteres
BEGIN -- inicia a seção de execução (aparecido com o void loop)
		Select  nome_coluna -- seleciona a coluna que será selecionada
	into v_variavel -- escolhe onde será armazenado o conteudo da coluna selecionada
		from nome_tabela; -- informa de qual tabela será extraido os dados
EXCEPTION -- declara as exceções que devem ser tratadas durante a execução do programa
		When exception_name then -- declara a exceção
END; -- encerra o programa
/ -- para PLSQL é necessaio para encerrar o editor
*/
/*
SET SERVEROUTPUT ON -- necessario para que o comando seja exibido no serial
DECLARE -- declara as variaveis
    v_teste VARCHAR2(30):='Hello, World'; -- define V_teste como alfanumerico com até 30 caracteres e usa o  operador de = para atribuir o valor de Hello, 
BEGIN -- começa a execução do programa 
	DBMS_OUTPUT.PUT_LINE(v_teste); -- exibe a V_teste no serial usando o pacote citado
END;  --encerra o programa     
/ -- finaliza a linha de comando

v_nascimento DATE; -- a variavel data aceita valores nulos e não tem valor inicial (nascimento)
v_data DATE := SYSDATE + 7; -- Declaração de data onde será a data de hoje + 7 dias
v_codigo NUMBER(2) NOT NULL := 10; -- Variavel númerica, é preenchida com um valor não nulo recebendo o valor de 10 inicialmente
v_UF VARCHAR2(2) := ‘ ‘SP’’; -- Declaração de caracter alfanumerico limitado a 2 caracteres (para incluir valores alfanumericos se faz necessaior aspas simples
v_loc VARCHAR2(2) DEFAULT ‘‘RJ’’; -- valor por padrão ´[e RJ
v_teste_logico BOOLEAN := (v_valor1 < v_valor2); -- Declara uma variavel booleana ( 0 ou 1, verdadeiro ou falso)
c_const CONSTANT NUMBER := 54; --  Declaração da constante númerica 
*/
/*
SELECT colunas -- Colunas que retornarão dados á consulta, podem incluir funções de grupo ou expressões
INTO {variaveis...|registro} -- obrigatória, usada para especificar os nomes das variaveis que inserem valores apartir da select, deve oferecer uma variavel para cada coluna
FROM tabela -- a variavel terá o valor armazenado
WHERE condição;

SET SERVEROUTPUT ON -- informa que deve ser exibida mensagem no serial 
DECLARE -- onde será declarado as variaveis
  v_nome    VARCHAR2(30); -- variavel alfanumerico até 30 caracteres
  v_cargo   VARCHAR2(30);
BEGIN -- inicio da programação
  SELECT ename, job -- seleciona o nome e o cargo
  INTO v_nome, v_cargo -- atribue os valores coletados do funcionario 7934 nas variaveis
  FROM emp -- seleciona a tabela
  WHERE empno = 7934; -- aponta que as informações são do funcionario 7934
DBMS_OUTPUT.PUT_LINE(v_nome); -- Exibe o nome do 7934
DBMS_OUTPUT.PUT_LINE(v_cargo); -- Exibe o cargo do 7934
END;
/

SET SERVEROUTPUT ON -- informa que deve ser exibida mensagem no serial 
DECLARE -- onde será declarado as variaveis   
  v_soma_sal   NUMBER;  -- define a variavel para as soma dos salarios como numerico
  v_deptno	 NUMBER NOT NULL := 10; -- define a variavel do departamento como um numero não nulo de até 10 caracteres          
BEGIN -- inicia a programação
  SELECT	SUM(sal)  -- seleciona os salarios e soma os valores dos salarios
  INTO		v_soma_sal -- joga os valores na variavel v_soma_sal
  FROM		emp -- pega da tabela emp
  WHERE	deptno = v_deptno; -- aponta que as informações são do dept serão buscadas com referencia na variavel do departamento
DBMS_OUTPUT.PUT_LINE('A soma dos salários do departamento ' || v_deptno || ' é ' || v_soma_sal); -- exibe no serial o texto + departamento + salario
END;
/

DECLARE -- inicia a declaração de variaveis
v_empno NUMBER := 11; -- declara a variavel como numero do empregado e adiciona o numero 11
v_ename VARCHAR2(13) := 'SANDRA'; --  declara a variavel do nome do employer como alfanumerico de 13 caracteres e define como SANDRA
v_job VARCHAR2(13) := 'GERENTE'; -- declara a função como gerente
v_deptno NUMBER := 10; -- declara o departamento dela como 10
BEGIN -- inicia o prograqma
   INSERT INTO emp(empno, ename, job, deptno) -- insere na tabela emp(nas colunas citadas) usando o insert 
          VALUES (v_empno, v_ename, v_job, v_deptno); -- aponta os valores (variaveis) que serão inseridas na tabela
END;
/

DECLARE -- inicia a declação de variaveis
	v_sal_increase   NUMBER := 2000; -- declara a variavel de aumento de salario como numerica e insere o valor de 2000
BEGIN -- inicia a programação
	UPDATE	emp -- atualiza a tabela emp 
	SET		sal = sal + v_sal_increase -- atualizando a coluna de salario com o valor ja existente + a variavel de aumento
	WHERE	job = 'ANALYST'; -- seleciona todos os salarios para aqueles tem o cargo de analista
END;
/

DECLARE
	v_deptno   NUMBER := 10; -- declara a variavel de departamento como numerico e define como 10               
BEGIN							
	DELETE FROM   emp -- deleta da tabela emp
	WHERE         deptno = v_deptno; -- deleta na coluna de departamento o departamento declarado na variavel
END;
/
*/
/*
-- Commit igual ao github onde será confirmado apenas quando o commit for efetivado, também existe o rollback que retorna o ultimo comando, o comando só funcionaria se todos funcionassem

BEGIN -- inicia o programa
	INSERT INTO dept VALUES ('A','A','A'); -- insere na coluna departamento os valores
	COMMIT; -- insere o commit onde será inserido apenas de todos os codigo funcionarem
EXCEPTION -- cria a exceção 
	WHEN OTHERS THEN ROLLBACK; -- exceção onde caso o commit não funcione então o codigo volta para o momento antes do inicio do programa
END;
/
*/
/*
CREATE TABLE tabela1 -- cria tabela 1  
  (col1 VARCHAR2(18)); -- cria e define a coluna 1 como uma variavel do tipo texto com até 18 caracteres alfanumericos
  
  INSERT INTO tabela1 -- insere na tabela 1 
    VALUES ('Campo com 18 bytes'); -- insere o valor em parenteses com exatos 18 bytes
  
  SET SERVEROUTPUT ON -- inicia a print no serial
  
  DECLARE -- declara variaveis
    v_col1 VARCHAR2(18); -- declara a variavel v_col1 como alfanumerico de até 18 caracteres
  BEGIN -- inicia a progrmação
    SELECT col1 INTO v_col1 -- seleciona a col1 e joga na variavel v_col1
      FROM tabela1; -- aponta em qual tabela a coluna está
    DBMS_OUTPUT.PUT_LINE ('Valor = ' || v_col1); -- printa no serial
  END;
  /
  
  */
  /*
  TRUNCATE TABLE tabela1; -- esvazia a tabela
  
  ALTER TABLE tabela1 -- altera a tabela 1
  MODIFY col1 VARCHAR2(30); -- modificando a col1 alterando a quantidade da carqacteres alfanumericos para 30
  
  INSERT INTO tabela1 -- insere na tabela1 os valores
    VALUES ('Tamanho alterado para 30 bytes'); -- insere estes valores de 30 bytes 
  
  SET SERVEROUTPUT ON -- prepara para printar no serial
  
  DECLARE -- inicia a declaração de variaveis
    v_col1 VARCHAR2(18); -- define a variavel v_col1 ainda como 18 caracteres alfanumericos (induzindo o erro)
  BEGIN -- inicia a programação
    SELECT col1 INTO v_col1 -- seleciona a col1 e joga as informações na variavel v_col1
      FROM tabela1; -- aponta de onde virão os dados
    DBMS_OUTPUT.PUT_LINE ('Valor = ' || v_col1); -- printa o valor da variavel V_col1 no serial ( porém devido ao erro acima ela não roda)
  END;
  /
  
  ORA-06502: PL/SQL: numeric or value error: character string buffer too small
  ORA-06512: at line 4
  */
  /*
  DECLARE -- inicia declaração de variaveis
    v_col1 tabela1.col1%TYPE; -- define a variavel v_col1 com a formatação igual da tabela1 coluna 1
  BEGIN -- inicia a progrmação
    SELECT col1 INTO v_col1 -- seleciona a coluna 1 e joga o valor dentro da variavel v_col1
      FROM tabela1; -- aponta a tabela de onde vem os dados
    DBMS_OUTPUT.PUT_LINE ('Valor = ' || v_col1); -- printa no serial
  END;
  /
  
  identificador [CONSTANT] {tabela.coluna%type | variavel%type} 
  [NOT NULL] [:= valor para inicialização | expr default]
  
  v_nome emp.ename%type; -- declaração da variável com a mesma 
  -- estrutura da coluna ename da tabela emp.
  
  v_balance number(7,2); 
  
  v_min_balance v_balance%type; -- declaração da variável com a 
  -- mesma estrutura da variável declarada anteriormente.
  ----------------------- IF -----------------------
  IF (condição) THEN
      conjunto de instruções;
  END IF;
  */
  /*
  DECLARE -- inicia declaração de variaveis
    v_col1    tabela1.col1%TYPE;   -- formata a variavel v_col1 conforme a col1 da tabela 1
    v_tamanho NUMBER(3); -- cria a variavel de tamanho e declara como número de até 3 casas
  BEGIN   -- inicia a linha de programação
    SELECT LENGTH(col1), col1 INTO v_tamanho, v_col1 --seleciona e lê a col1 e joga o tamanho na variavel tamanho da coluna e oq está escrito dentro da coluna na variavel da col1
      FROM tabela1;   -- aponta para a tabela que está a coluna
    IF v_tamanho > 25 THEN -- se a variavel tamanho for maior que 25 então
      DBMS_OUTPUT.PUT_LINE ('Texto = ' || v_col1); -- printa no serial o texto dentro da variavel da col1   
    END IF; -- finaliza a condição de se
  END;
  /
  
  */
/*
IF (condição) THEN
     conjunto de instruções 1;
  ELSE
     conjunto de instruções 2;
  END IF;
*/
/*DECLARE
    v_col1    tabela1.col1%TYPE; -- define a variavel v_col1 como mesmo tipo da cola1 da tabela1  
    v_tamanho NUMBER(3); -- define a variavel v_tamanho como numérico de 3 caracteres
  BEGIN   -- Inicia a linha de codigo
    SELECT LENGTH(col1), col1 INTO v_tamanho, v_col1    -- seleciona a col1 e Lê seu tamanho e armazena o tamanho dentro da variavel V_tamanho e também armazena o texto da col1 na variavel V_Coluna
      FROM tabela1;   -- Aponta onde está a col1
    IF v_tamanho > 25 THEN -- COndicional onde se a variavel V_Tamanho for maior que 25, então ´printa       
      DBMS_OUTPUT.PUT_LINE ('Texto = ' || v_col1); -- Printa 
    ELSIF v_tamanho > 20 THEN
       DBMS_OUTPUT.PUT_LINE ('Texto maior que 20');
    ELSIF v_tamanho > 15 THEN
       DBMS_OUTPUT.PUT_LINE ('Texto maior que 15');
    ELSE -- Caso não atenda nenhuma das condições printa que o texto é menor ou igual a 15
       DBMS_OUTPUT.PUT_LINE ('Texto menor ou igual a 15');
    END IF; 
  END;
  */
/*  
  DECLARE
    v_tamanho NUMBER(3); 
  BEGIN   
    SELECT LENGTH(col1) INTO v_tamanho     
      FROM tabela1; 
    IF v_tamanho > 25 AND
       TO_CHAR(SYSDATE, 'YYYY') > 1999 THEN  
       DBMS_OUTPUT.PUT_LINE ('Maior que 25 bytes e século XXI');
    END IF; 
  END;
  /
  
  DECLARE
    v_tamanho NUMBER(3); 
  BEGIN   
    SELECT LENGTH(col1) INTO v_tamanho     
      FROM tabela1;   
    IF v_tamanho > 25 OR
       TO_CHAR(SYSDATE, 'YYYY') > 1999 THEN
       DBMS_OUTPUT.PUT_LINE ('Maior que 25 bytes ou século XXI');
    END IF; 
  END;
  /
  
  LOOP                                  
   conjunto de instruções;
    EXIT [WHEN condição]; 
  END LOOP;
  */
/*
DECLARE -- Inicia o bloco das variaveis
    v_contador NUMBER(2) :=1; -- declava a variavel V_contador como um numero de até 2 caracteres e o define como 1
  BEGIN   -- Inicia a linha de codigo
    LOOP -- Inicio do laço de repetição de inserção de numeros
      INSERT INTO tabela1 -- insere na tabela1
      VALUES ('Inserindo texto numero ' || v_contador); -- o valor de Inserindo texto número onde o número sera igual a variavel v_contador
      v_contador := v_contador + 1;   -- faz com que sempre o loop chegue a este momento, ascrecente na variavel mais 1 número
    EXIT WHEN v_contador > 10;   -- diz que o programa deve fechar quando a variavel for maior que 10
    END LOOP; -- finaliza o laço
  END;
  /
  
  SELECT * FROM tabela1
  
FOR contador in [REVERSE] limite_inferior..limite_superior LOOP  -- reverse faz o contador decrescer 
    conjunto de instruções;
    . . .
  END LOOP;

BEGIN   -- Inicia o codigo
    FOR i IN 1..10 LOOP -- segue com o laço de repetição enquanto i estiver entre 1 e 10
      INSERT INTO tabela1 -- insere na tabela 1
      VALUES ('Inserindo texto numero ' || i); --valores junto ao texto onde o valores numericos são igual a variavel i
    END LOOP; -- finaliza o laço de repetição
  END;
  /  
*/
/*
DECLARE
    v_contador NUMBER(2) :=1; -- define a variavel como um numero de até 2 caracteres
  BEGIN   
    WHILE v_contador <= 10 LOOP -- utiliza o laço de repetição com while onde a condição é ser menor ou igual a 10
      INSERT INTO tabela1 -- insere na tabela1 as informações em parenteses abaixo
      VALUES ('Inserindo texto numero ' || v_contador); 
      v_contador := v_contador + 1;   -- sempre que o codigo passar por esta linha adiciona 1 ao contador
    END LOOP;
  END;

BEGIN   
     <<loopexterno>> -- label
    FOR i IN 1..3 LOOP -- primeiro laço fará com quem o laço de baixo rode 3 vezes
      <<loopexterno>>   
      FOR j IN 1..5 LOOP -- laço que roda cinco vezes 3 vezes devido ao laço acima
          INSERT INTO tabela1 
          VALUES ('Inserindo texto numero ' || i || j);
      END LOOP loopexterno; -- finaliza o loop externo de 5
    END LOOP loopexterno; -- finaliza o loop externo de 3
  END;
  /
  
SELECT * FROM tabela1;

SET SERVEROUTPUT ON

DECLARE
  v_empno    emp.empno%TYPE;
  v_ename    emp.ename%TYPE;
  v_job      emp.job%TYPE;
  v_mgr      emp.mgr%TYPE;
  v_hiredate emp.hiredate%TYPE;
  v_sal      emp.sal%TYPE;
  v_comm     emp.comm%TYPE;
  v_deptno   emp.deptno%TYPE;

BEGIN
SELECT empno, ename, job, mgr,
       hiredate, sal, comm, deptno
  INTO v_empno, v_ename, v_job, v_mgr,
       v_hiredate, v_sal, v_comm, v_deptno
  FROM emp
 WHERE empno = 7839;
 DBMS_OUTPUT.PUT_LINE ('Codigo   = ' || v_empno);
 DBMS_OUTPUT.PUT_LINE ('Nome     = ' || v_ename);
 DBMS_OUTPUT.PUT_LINE ('Cargo    = ' || v_job);
 DBMS_OUTPUT.PUT_LINE ('Gerente  = ' || v_mgr);
 DBMS_OUTPUT.PUT_LINE ('Data     = ' || v_hiredate);
 DBMS_OUTPUT.PUT_LINE ('Sala     = ' || v_sal);
 DBMS_OUTPUT.PUT_LINE ('Comissao = ' || v_comm);
 DBMS_OUTPUT.PUT_LINE ('Depart.  = ' || v_deptno);  
END;
/

SET SERVEROUTPUT ON

DECLARE
  emprec emp%ROWTYPE; -- declara a variavel emprec,depois gera uma variavel para cada linha rowtype coleta a linha inteira inclusive os formatos de dados da tabela emp

BEGIN
SELECT * -- seleciona a tabela como um todo
  INTO emprec -- joga os dados selecionados na variavel emprec
  FROM emp -- aponta de onde vem as informações (tabela de exemplo)
 WHERE empno = 7839; -- onde empno é igual ao valor pedido
 DBMS_OUTPUT.PUT_LINE ('Codigo   = ' || emprec.empno); -- começa a printar no serial
 DBMS_OUTPUT.PUT_LINE ('Nome     = ' || emprec.ename);
 DBMS_OUTPUT.PUT_LINE ('Cargo    = ' || emprec.job);
 DBMS_OUTPUT.PUT_LINE ('Gerente  = ' || emprec.mgr);
 DBMS_OUTPUT.PUT_LINE ('Data     = ' || emprec.hiredate);
 DBMS_OUTPUT.PUT_LINE ('Sala     = ' || emprec.sal);
 DBMS_OUTPUT.PUT_LINE ('Comissao = ' || emprec.comm);
 DBMS_OUTPUT.PUT_LINE ('Depart.  = ' || emprec.deptno);  
END;


SELECT * 
  FROM emp;
  
SELECT ename, job 
  FROM emp
 WHERE deptno = 20;
 
 DECLARE   
  emprec emp%ROWTYPE; 
BEGIN 
SELECT SUM(sal)    
  INTO emprec.sal   
  FROM emp 
GROUP BY deptno;  
  DBMS_OUTPUT.PUT_LINE ('Salario = ' || emprec.sal); 
END;
/
ERROR at line 1:
-- ORA-01422: exact fetch returns more than requested number of rows
-- ORA-06512: at line 4

-- Tupla Sinonimo de linha ou registro da tabela

/* %FOUND retorna verdadeiro (TRUE), caso alguma linha (tupla) tenha sido
afetada.

. %ISOPEN em um CURSOR explícito, retorna verdadeiro (TRUE) caso o CURSOR
esteja aberto. No caso do CURSO implícito sempre retornará como falso
(FALSE), porque um CURSOR implícito sempre é fechado após a execução dos
comandos associados a ele.

· %NOTFOUND retorna verdadeiro (TRUE) caso nao tenha encontrado nenhuma
tupla. Caso tenha encontrado, retornara falso (FALSE) até a última tupla.

. %ROWCOUNT retorna o numero de tuplas do CURSOR.*/
/*
BEGIN
   DELETE 
     FROM emp
   WHERE deptno = 10;
   DBMS_OUTPUT.PUT_LINE ('Linhas apagadas = ' || SQL%ROWCOUNT); -- utiliza o "SQL" que pega a ultima consulta implicita de conta a quantidade de linahs
   ROLLBACK; -- desfaz a execução pedida anteriormente
END;
/

DECLARE   
  CURSOR cursor_emp IS -- declaqrqa o cursor como cursor_emp que é 
      SELECT deptno, SUM(sal)-- uma seleção da coluna deptno, no qual pega a soma dos salarios        
      FROM emp-- diz que tudo esta na tabela emp
     GROUP BY deptno; -- agrupa por deptno (codigo de departamento)
     OPEN nome_cursor; -- abre o cursor declarado acima

DECLARE   
  CURSOR cursor_emp IS -- declaqrqa o cursor como cursor_emp que é 
      SELECT deptno, SUM(sal)-- uma seleção da coluna deptno, no qual pega a soma dos salarios        
      FROM emp-- diz que tudo esta na tabela emp
     GROUP BY deptno; -- agrupa por deptno (codigo de departamento)
BEGIN
   OPEN cursor_emp; -- abre o cursor declarado acima
END;
/

FETCH cursor_name -- instrução utilizada para extrair dados de um conjunto ativo do identificador  do cursor
 INTO [variável1, variável2, ...|record_name]; -- joga o dado nas variaveis (precisa ter a mesma quantidade de variaveis de colunas) e nome da variavel onde foi armazenado
 
 DECLARE
  emprec emp%ROWTYPE; -- cria a variavel emp rowtype(cada linha)
  CURSOR cursor_emp IS -- cria o cursor e nomeia como cursor_emp
         SELECT deptno, SUM(sal)--  extrai os dados por departamento e soma os salarios         
          FROM emp -- da tabela emp       
        GROUP BY deptno; -- agrupa por departamento
BEGIN -- inicia a linha de codigo
   OPEN cursor_emp; -- abre o cursor
   FETCH cursor_emp INTO emprec.deptno, emprec.sal; -- extrai os dados do cursor e joga nas duas variaveis criadas pelo rowtype (depnto e soma dos salarios)
   DBMS_OUTPUT.PUT_LINE ('Departamento: ' || emprec.deptno); -- printa no serial
   DBMS_OUTPUT.PUT_LINE ('Salario     : ' || emprec.sal);
END;
/

DECLARE
  emprec emp%ROWTYPE; -- cria a variavel emp rowtype(cada linha)
  CURSOR cursor_emp IS -- cria o cursor e nomeia como cursor_emp
         SELECT deptno, SUM(sal)--  extrai os dados por departamento e soma os salarios         
          FROM emp -- da tabela emp       
        GROUP BY deptno; -- agrupa por departamento
BEGIN -- inicia a linha de codigo
   OPEN cursor_emp; -- abre o cursor
   LOOP -- inicia o LOOP
      FETCH cursor_emp INTO emprec.deptno, emprec.sal; -- extrai os dados do cursor e joga nas duas variaveis criadas pelo rowtype (depnto e soma dos salarios)
      EXIT WHEN cursor_emp%NOTFOUND; -- sai do loop quando o cursor não for encontrado
      DBMS_OUTPUT.PUT_LINE ('Departamento: ' || emprec.deptno);
      DBMS_OUTPUT.PUT_LINE ('Salario     : ' || emprec.sal);
   END LOOP; -- finaliza o loop
   CLOSE cursor_emp; -- fecha o cursos para liberar memoria RAM
END;
/

------------------------- LOOP FOR ------------------------------------

FOR nome_registro IN nome_cursor LOOP -- instrução de laço, nome da variavel que será criada IN nome do cursor
    Instruções; -- oq será feito dentro do loop
END LOOP;
-- não se faz necessario criar a variavel pois o proprio loop tem a função de dclarar e utilizar o rowtype

DECLARE   
  CURSOR cursor_emp IS -- cria o cursor e nomeia como cursor_emp
    SELECT deptno, SUM(sal)--  extrai os dados por departamento e soma os salarios         
    FROM emp -- da tabela emp       
  GROUP BY deptno; -- agrupa por departamento
BEGIN    
  FOR emprec IN cursor_emp LOOP -- inicia o laço for, com a variavel emprec utilizando o cursor onde oOPEN, FETCH e CLOSE ja são executadas no for
    DBMS_OUTPUT.PUT_LINE ('Departamento: ' || emprec.deptno);       
    DBMS_OUTPUT.PUT_LINE ('Salario     : ' || emprec.soma);    
  END LOOP; 
END; 
/

BEGIN   
  FOR emprec IN (SELECT deptno, SUM(sal) soma --utilizando olaço for da variavel emprec enquanto, selecionar a coluna deptno, e somando os salarios
    FROM emp GROUP BY deptno) -- faz o agrupramento (tudo até aqui foi basicamente o cursor eo FETCH implicitos
  LOOP -- inicia o loop
    DBMS_OUTPUT.PUT_LINE ('Departamento: ' || emprec.deptno);        
    DBMS_OUTPUT.PUT_LINE ('Salario     : ' || emprec.soma);    
  END LOOP; 
END; 
/

DECLARE
  emprec emp%ROWTYPE;   -- declara  a variavel como emprec e adicionar cada linha na variavel 
  CURSOR cursor_emp IS -- cria o cursor e nomea como cursor_emp 
         SELECT empno, sal --extrai o dados de empno e o salario      
          FROM emp -- aponta a tabela onde esta
            FOR UPDATE; -- bloqueia a linhas para serem atualizadas, assim enquanto o codigo roda ninguém mexe
BEGIN
   OPEN cursor_emp; -- abre o cursor
   LOOP -- inicia o loop
      FETCH cursor_emp INTO emprec.empno, emprec.sal; -- ´pega as informações do cursor de joga nas variaveis
      EXIT WHEN cursor_emp%NOTFOUND; -- caso ocursor pare finaliza o loop
      UPDATE emp SET sal = sal * 1.05 WHERE CURRENT OF cursor_emp; -- atualiza o salario em 5% onde foi rezervado no for update (cursor)
   END LOOP;
   CLOSE cursor_emp;
END;
*/

