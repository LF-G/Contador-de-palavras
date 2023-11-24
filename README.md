# Contador-de-palavras
Contador de frequência de palavras/expressões em processos jurídicos.

Este respositório contém:
(1) Um script Python (contador.py);
(2) Uma pasta com processos judiciais;
(3) Um arquivo intitulado "frequencias.xlsx".

Vou explicá-los um a um:

(1) Script Python (contador.py)

O script Python imprime, para cada um dos processos judiciais da pasta "Decisoes", uma tabela
em formato xlsx que contém:

- o número do processo;
- a jurisdição do processo;
- a quantidade de arquivos existentes no processo;
- a frequência com que ocorrem, no processo, expressões do grupo "sabidamente inverídico";
- a média, por arquivo do processo, de ocorrência de expressões do grupo "sabidamente inverídico";
- a frequência com que no processo ocorrem palavras do grupo "ofens-";
- a média, por arquivo do processo, de ocorrência de palavras do grupo "ofens-".

Por "expressões do grupo sabidamente inverídico" quero dizer "a expressão 'sabidamente inverídico' e algumas de suas variações". Em outras palavras,
o grupo "sabidamente inverídico" engloba a expressão "sabidamente inverídico" propriamente dita e outras como "sabidamente inverídica", "sabidamente
inverídicas" e "sabidamente inveridico". Para capturar expressões deste grupo, utilizei a seguinte Regex (Regular Expression) da linguagem Python:
\W(sabidament.{,20}inver.dic.*?)\W.

Por "palavras do grupo ofens-" quero dizer "palavras como ofensivo, ofensa, ofensiva". Para capturar expressões deste grupo, utilizei a seguinte Regex
(Regular Expression) da linguagem Python: \b[Oo][Ff][Ee][Nn][Ss]\w*.

O código foi inteiramente escrito por mim.

(2) Pasta com processos judiciais

Esta pasta é uma base de processos judiciais organizada da seguinte maneira: os documentos de um mesmo processo estão reunidos em uma pasta cujo nome é o código desse 
processo; as pastas dos processos de um determinado TRE estão reunidas em uma pasta cujo nome especifica o TRE (jurisdição) em questão; as pastas de cada
um dos TREs (jurisdições) estão reunidas em uma única grande pasta (a pasta "Decisoes").

(3) Arquivo intitulado "frequencias.xlsx"

Este arquivo é o resultado da execução do script Python contador.py.

Para executar o script, basta colocá-lo junto com a pasta "Decisoes" em um mesmo diretório.
