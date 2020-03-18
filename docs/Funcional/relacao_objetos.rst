#################
Relação de Objetos
#################

Neste tópico estaremos falando sobre o relacionamento entre as reclamações do **Reclame AQUI** com os objetos que o RA Connect utiliza no Salesforce.

Reclamação
-----------------------

.. figure:: img/casoReclamacao.png
    :alt: Solidity logo
    :align: center
    
    Caso criado a partir de uma reclamação.

As reclamações baixadas pela conexão serão transformadas em **casos** no Salesforce, dados da reclamação como o titulo, interações e quem abriu a reclamação serão transformadas em dados do **caso** criado.

Interação
-----------------------

.. figure:: img/comentarioInteracao.png
    :alt: Solidity logo
    :align: center
    
    Comentário do caso, criado a partir de uma interação da reclamação.

As interações relacionada àquela reclamação serão registradas como **comentário do caso**.

Consumidor
-----------------------

.. figure:: img/contatoCaso.png
    :alt: Solidity logo
    :align: center
    
    Contato vinculado ao caso.

Esse **contato** é o representante do consumidor dentro do Salesforce.

.. figure:: img/contatoConsumidor.png
    :alt: Solidity logo
    :align: center
    
    Contato que representa o consumidor que abriu a reclamação.	

Os dados do consumidor abastecerá os dados do **contato**.

.. Hint:: Caso tenha um contato já existente do consumidor no Salesforce (a base de identificação é o campo Email), será atribuida à esse contato todos as reclamações relacionadas ao consumidor, caso contrário será criado um novo contato e as reclamações serão vinculadas ao mesmo.