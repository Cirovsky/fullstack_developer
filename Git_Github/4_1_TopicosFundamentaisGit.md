# 4.1. Tópicos Fundamentais para entender o funcionamento do Git

* SHA1

* Objetos internos do GIT

* Segurança

## SHA1

O SHA1 é um algoritmo de encriptação. É um conjunto de funções hash criptografadas

projetadas pela NSA (Agência de Segurança Nacional dos Estados Unidos).

O SHA1 vai pegar uma informação e embaralhar-la de uma forma muito específica.

A encripitação gera um conjunto de caracteres de 40 dígitos específico daquele arquivo, e qualquer alteração será gerada uma chave totalmente diferente. 

Ele é uma forma segura de indentificar um arquivo e controlar, com isso, qualquer alteração no arquivo, evitando alterações indevidas ou acidentais. 

Pode-se consultar o sha1 de um arquivo no git bash através do seguinte comando:

`$ openssl sha1 README.md`

`SHA1(README.md)= 518c1df47c3b37e27ac3b799126620a1b3dfcf98`

A menor modificação do arquivo gerará uma nova chave.

## Objetos internos do Git

Os objetos fundamentais do Git são Blobs, Trees e Commits. Eles são fundamentais para o versionamento do Código.

### Blob

É um objeto que armazena meta-dados dos arquivos. O Tipo, o tamanho e o conteúdo de um arquivo. 

### Tree

As trees, armazenam BLOBs. Elas armazenam e apontam para as BLOBS.

A tree guarda o nome dos arquivos. Ela é responsável por montar a estrutura onde estão localizados os arquivos.

As arvores também possui o seu próprio SHA1. 

Mudar um arquivo, então mudará o SHA1 do arquivo, da BLOB e da TREE. 

### Commit

O COMMIT junta todos os outros objetos. Ele aponta para a(s) ávores (TREEs), aponta para o parente (o COMMIT imediatamente anterior a ele) para o Autor, para uma mensagem, e para um timestamp (data e hora de  quando os arquivos foram 'comitados').

O cojunto de commits formam uma linha do tempo de quando aqueles arquivos foram alterados. Não há como alterar sem que isso fique claro dentro do histórico de commits.

### Segurança

O Git opera de modo a proporcionar um sistema distribuído seguro. Pelo fato dos commits serem tão dificeis de ser alterados, e que a versões dos arquivos na máquina dos colaboradores e nos servidores na nuvem. O código do programa terá várias versões confiáveis que podem ser acessadas em caso de problemas em algum dos repositórios (locais ou remotos).

[](4_2_CiclodeVidadosArquivosGit.md)Próximo
