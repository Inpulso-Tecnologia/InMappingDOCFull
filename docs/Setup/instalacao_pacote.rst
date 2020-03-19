
Registro de Domínio para a Organização
--------------------------------------


Para que o pacote possa ser baixado primariamente o usuário deve possuir uma organização no SalesForce que possua o domínio cadastrado. Para cadastrar um domínio, vá até às configurações através a engrenagem no canto superior direito, como na figura a seguir: 

.. figure:: img/configuracao.png
    :alt: Solidity logo
    :width: 500px
    :align: center
    
    Acessando **Configurações** da organização.

A seguir digite na barra de busca rápida **Meu domínio** e clique nele, como na figura a seguir:

.. figure:: img/dominio1.png
    :alt: Solidity logo
    :align: center
    
    Barra de pesquisa das configurações

Caso não tenha domínio cadastrado, deve-se escolher um nome para o domínio e verificar a validade do mesmo.

.. figure:: img/dominio2.png
    :alt: Solidity logo
    :align: center
    
    Registro de domínio

Após a validação confirmada, registrar o domínio do mesmo. Após o registro concluído, o SalesForce pedirá para que logue novamente. 

Após logar, vá para a tela do **Meu domínio** novamente e clique em **Efetuar login**.

.. figure:: img/dominio3.png
    :align: center

    Logar no novo domínio

Efetuado login, clique em **Implantar para usuários**.

.. figure:: img/dominio4.png
    :alt: Solidity logo
    :align: center
    
    Implantar o novo domínio para os usuários

Tendo realizado estas ações, já com o domínio registrado, poderá seguir para a instalação do pacote.


Implantação da Biblioteca
-------------------------------


Com o arquivo .Zip da biblioteca será necessário fazer o deploy via Workbentch, acessando o site a seguir:
        
        https://workbench.developerforce.com/login.php

Após fazer o login vá até o canto superior direito em **Migration -> Deploy**, como demonstrado na figura a seguir:

.. figure:: img/deploy.png
    :alt: Solidity logo
    :align: center
    
    Acessando a seção para fazer o deploy

Agora escolha o .Zip da biblioteca e marque **Single Package**, como na figura a seguir:

.. figure:: img/deployBiblioteca.png
    :alt: Solidity logo
    :align: center
    
    Configurando o deploy

Na tela a seguir clique em **Deploy**.

.. figure:: img/deploy2.png
    :alt: Solidity logo
    :align: center
    
    Confirmando o deploy

Nesse momento será iniciado o deploy, caso ocorra tudo certo, sem nenhum problema, ficará parecido como a figura a seguir:

.. figure:: img/deployFinalizado.png
    :alt: Solidity logo
    :align: center
    
    Deploy finalizado