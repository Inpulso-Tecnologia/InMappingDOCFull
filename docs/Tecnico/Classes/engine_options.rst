Classe EngineOptions
====================


Inner Classe da classe :doc:`InMapEngine </Tecnico/Classes/map_engine>`.

Assinatura do Construtor
    public EngineOptions()

Possui as váriaveis: 

* :ref:`origem <Tecnico/Classes/engine_options:origem>`
* :ref:`parentId <Tecnico/Classes/engine_options:parentId>`
* :ref:`setMapeamentoId <Tecnico/Classes/engine_options:setMapeamentoId>`

E os métodos:

* :ref:`fillOrigemId <Tecnico/Classes/engine_options:fillOrigemId>`
* :ref:`fillSetMapeamento <Tecnico/Classes/engine_options:fillSetMapeamento>`

Exemplo

   .. code-block:: apex

      InMapEngine.EngineOptions engineOpt = new InMapEngine.EngineOptions();


origem
------

Assinatura
    public Origem__mdt origem {get;set;}  

Ação
  	Cria uma variável tipo **Origem__mdt**.


parentId
--------

Assinatura
    public String parentId {get;set;}  

Ação
  	Cria uma variável tipo **String**.


setMapeamentoId
---------------

Assinatura
    public Set<Id> setMapeamentoId {get;set;}  

Ação
  	Cria uma coleção do tipo **Set<Id>**.


fillOrigemId
------------

Assinatura
    public void fillOrigemId()

Exemplo

   .. code-block:: apex

      InMapEngine.EngineOptions engineOpt = new InMapEngine.EngineOptions();
      engineOpt.fillOrigemId();


fillSetMapeamento
-----------------

Assinatura
    public void fillSetMapeamento()

Exemplo

   .. code-block:: apex

      InMapEngine.EngineOptions engineOpt = new InMapEngine.EngineOptions();
      engineOpt.fillSetMapeamento();