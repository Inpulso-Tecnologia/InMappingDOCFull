Classe InMapEngine
==================


Classe responsável sobre o mapeamento da **Biblioteca de Mapeamento**. 
Essa contém as seguintes Inner Class:

* :doc:`EngineOptions </Tecnico/engine_options>`
* :doc:`MapEntity </Tecnico/map_entity>`

E os métodos listado abaixo.

doIt
----

Assinatura
    public static Database.SaveResult[] doIt(MapEntity pMapEntity)  

Valor retornado
  	Retorna uma array do resultado das operações DML.

Exemplo

   .. code-block:: apex

      List<Map<String, Object>> oTeste = new List<Map<String, Object>>();
      Map<String, Object> mapCampos = new Map<String, Object>();
      mapCampos.put('nome do campo', 'valor do campo');
      oTeste.add(mapCampos);

      InMapEngine.MapEntity mapEntity = new InMapEngine.MapEntity('id do mapeamento', oTeste);

      InMapEngine.doIt(mapEntity);


doIt
----

Assinatura
    public static Database.SaveResult[] doIt(List<MapEntity> pListMapEntity) 

Valor retornado
  	Retorna uma array do resultado das operações DML.

Exemplo

   .. code-block:: apex

      List<Map<String, Object>> oTeste = new List<Map<String, Object>>();
      Map<String, Object> mapCampos = new Map<String, Object>();
      mapCampos.put('nome do campo', 'valor do campo');
      oTeste.add(mapCampos);
      
      List<InMapEngine.MapEntity> lstMapEntity = new List<InMapEngine.MapEntity>();
      lstMapEntity.add(new InMapEngine.MapEntity('id do mapeamento', oTeste));

      InMapEngine.doIt(lstMapEntity);


doItByOptions
-------------

Assinatura
    public static Database.SaveResult[] doItByOptions(EngineOptions pEngineOptions, List<Map<String, Object>> pData)

Valor retornado
  	Retorna uma array do resultado das operações DML.

Exemplo

	.. code-block:: apex

	    InMapEngine.EngineOptions engineOpt = new InMapEngine.EngineOptions();

	    List<Map<String, Object>> oTeste = new List<Map<String, Object>>();
	    Map<String, Object> mapCampos = new Map<String, Object>();
	    mapCampos.put('rótulo do campo', 'valor do campo');
	    oTeste.add(mapCampos);
	      
	    InMapEngine.doItByOptions(engineOpt, oTeste);


doItByOptions
-------------

Assinatura
    public static Database.SaveResult[] doItByOptions(EngineOptions pEngineOptions, List<SObject> pListSObject)

Valor retornado
  	Retorna uma array do resultado das operações DML.

Exemplo

   .. code-block:: apex

   	  InMapEngine.EngineOptions engineOpt = new InMapEngine.EngineOptions();

      List<SObject> listObj = new List<SObject>();
	  Task task = new Task(
	      CallObject = 'teste'
	  );
	  listObj.add(task);

	  InMapEngine.doItByOptions(engineOpt, listObj);


doItByOptions
-------------

Assinatura
    public static Database.SaveResult[] doItByOptions(EngineOptions pEngineOptions, List<String> pListJson)

Valor retornado
  	Retorna uma array do resultado das operações DML.

Exemplo

   .. code-block:: apex

      InMapEngine.EngineOptions engineOpt = new InMapEngine.EngineOptions();

      String sJson = '{"nome do campo" : "valor do campo"}';

      InMapEngine.doItByOptions(engineOpt, sJson);


doItByOptions
-------------

Assinatura
    public static Database.SaveResult[] doItByOptions(EngineOptions pEngineOptions, String pFullJson)

Valor retornado
  	Retorna uma array do resultado das operações DML.

Exemplo

   .. code-block:: apex

      InMapEngine.EngineOptions engineOpt = new InMapEngine.EngineOptions();

      String sJson = '{"nome do campo" : "valor do campo"}';

      List<String> lstJson = new List<String>();

      lstJson.add(sJson);

      InMapEngine.doItByOptions(engineOpt, lstJson);












