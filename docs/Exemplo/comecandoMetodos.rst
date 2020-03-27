Utilizando Metodos da Biblioteca
================================


A terceira etapa para utilizarmos a biblioteca será utilizarmos os 
métodos que a mesma oferece, para criarmos de uma maneira automatica 
os objetos destinado a partir do objeto origem, a seguir será mostrado 
como criar um **Contato**, a aprtir da trigger de pós inserção de um 
**Lead**.

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


.. Hint:: Nessa trigger mostra como utilizar a classe :doc:`InMapEngine </Tecnico/Classes/map_engine>`, a inner class :doc:`EngineOptions </Tecnico/Classes/engine_options>` e o objeto personalizado :doc:`Mapeamento__c </Tecnico/ObjetosPersonalizados/mapeamento>`.