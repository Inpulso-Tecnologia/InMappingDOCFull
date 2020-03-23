Exemplo de uso
====================

Após a importação do pacote, será demonstrado um exemplo de como pode 
utilizar a biblioteca, nesse exemplo será criado um Contato a partir 
da inserção de um Lead.


**Criação dos metadado**


Crie um registro no metadado **Origem**, conforme a figura a seguir:

.. figure:: img/leadToContact.png
    :alt: Solidity logo
    :align: center
    
    Criando um registro de **Origem** chamado LeadToContact.

Crie os registros no **Campo de Origem** para a conversão do **Lead** para um **Contato**, nesse exemplo teremos dois campos que serão passados para o **Contato**, no caso o campo de **Sobrenome** e o campo **Companhia**, como nas figuras a seguir.

.. figure:: img/exemploLastName.png
    :alt: Solidity logo
    :align: center
    
    Criando um registro de **Campo de Origem** chamado ExemploLastName do tipo **Texto**.

.. figure:: img/exemploCompany.png
    :alt: Solidity logo
    :align: center
    
    Criando um registro de **Campo de Origem** chamado ExemploCompany do tipo **Texto**.


**Criação do mapeamento**


Agora será criado o mapeamento, vá até o aplicativo de **Biblioteca de Mapeamento**, após isso vá na aba de **Gerenciador de Mapeamentos** e clique em **Novo**, após isso selecione **LeadToContact**, como na figura a seguir:

.. figure:: img/step1.png
    :alt: Solidity logo
    :align: center
    
    Selecionando a origem **LeadToContact**.

A segunda etapa será a configuração o destino do mapeamento da seguinte forma:

*   **Nome**: ConvertLead
*   **Objeto Selecionado**: Contato
*   **Permissão**: Somente novo
*   **Descrição**: Esse mapeamento serve para converter um Lead recém criado em um Contato.

Como demonstrado na figura a seguir:

.. figure:: img/step2.png
    :alt: Solidity logo
    :align: center
    
    Configurando o destino do mapeamento.

A terceira e última etapa será a parte de fazer o mapeamento dos **Campos da Origem** para os campos do destino, como na figura a seguir:

.. figure:: img/step3.png
    :alt: Solidity logo
    :align: center
    
    Mapenando os campos da origem para os campos do destino.


**Criação do trigger**


Após toda essas etapas, agora iremos criar um trigger de after insert para o objeto Lead, como desmonstrado a seguir:

.. code-block:: apex
	:linenos:

	
	trigger lead_ai on Lead (after insert) {
		List<Lead> lstLead = Trigger.new;
	    
		Set<Id> setIdMaps = new Set<Id>();
		
		// 	Pegando o Id do mapeamento criado
		Mapeamento__c maps = [
	            SELECT 
	                Id,
	                Name
	            FROM 
	                Mapeamento__c
	            WHERE
	                Name = 'ConvertLead'
	    ]; 
	    setIdMaps.add(maps.Id);
	    
	    
	    // Criando o objeto EngineOptions e atribuindo o Id do mapeamento que utilizaremos
	    InMapEngine.EngineOptions engineOpt = new InMapEngine.EngineOptions();
	    engineOpt.setMapeamentoId = setIdMaps;
	    
	    
	    
	    // Criando o Map, para realização do parse, onde o a chave do map é o nome do campo da origem e o objeto do map é o valor desse campo no objeto destino
	    List<Map<String, Object>> oLead = new List<Map<String, Object>>();
	    Map<String, Object> mapCampos = new Map<String, Object>();
	    for(Integer i = 0; i < lstLead.size(); i++) {
	        mapCampos.clear();
	        mapCampos.put('ExemploLastName', lstLead[i].LastName);
	        mapCampos.put('ExemploCompany', lstLead[i].Company);
	        oLead.add(mapCampos);
	    }
	    
	    
	    // E por último iniciando a engrenagem de mapear os dados passados
	    InMapEngine.doItByOptions(engineOpt, oLead);
	}