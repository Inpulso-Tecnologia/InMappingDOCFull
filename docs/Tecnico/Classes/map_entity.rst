Classe MapEntity
================


Inner Classe da classe :doc:`InMapEngine </Tecnico/Classes/map_engine>`.

Assinatura do Construtor
    public MapEntity(Id pMapeamentoId, List<Map<String, Object>> pListMapFields)

Possui as váriaveis: 

* :ref:`mapeamentoId <Tecnico/Classes/map_entity:mapeamentoid>`
* :ref:`listMapFields <Tecnico/Classes/map_entity:listmapfields>`

Exemplo

   .. code-block:: apex

      List<Map<String, Object>> oTeste = new List<Map<String, Object>>();
      Map<String, Object> mapCampos = new Map<String, Object>();
      mapCampos.put('nome do campo', 'valor do campo');
      oTeste.add(mapCampos);

      InMapEngine.MapEntity mapEntity = new InMapEngine.MapEntity('id do mapeamento', oTeste);


mapeamentoId
------------

Assinatura
    public Id mapeamentoId;

Ação
  	Cria uma variável tipo **Id**.


listMapFields
-------------

Assinatura
    public List<Map<String, Object>> listMapFields; 

Ação
  	Cria um lista de mapas do tipo **List<Map<String, Object>>**.