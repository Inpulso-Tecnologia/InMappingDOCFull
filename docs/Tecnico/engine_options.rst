Classe EngineOptions
====================


Inner Classe da classe :doc:`InMapEngine <Tecnico/map_engine>`.

Assinatura do Construtor
    public EngineOptions()

Especificação
  	Possui as váriaveis:
 	*	:doc:`origem <Tecnico/engine_options#origem>`
 	*	:doc:`parentId <Tecnico/engine_options#parentId>`
 	*	:doc:`setMapeamentoId <Tecnico/engine_options#setMapeamentoId>`
 	E os métodos:
 	*	:doc:`fillOrigemId <Tecnico/engine_options#fillOrigemId>`
 	*	:doc:`fillSetMapeamento <Tecnico/engine_options#fillSetMapeamento>`
 	*	:doc:`getSoqlMapeamento <Tecnico/engine_options#getSoqlMapeamento>`
 	*	:doc:`getMountFilter <Tecnico/engine_options#getMountFilter>`

Exemplo

   .. code-block:: apex

      **A fazer**


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

      **A fazer**


fillSetMapeamento
-----------------

Assinatura
    public void fillSetMapeamento()

Exemplo

   .. code-block:: apex

      **A fazer**


getSoqlMapeamento
-----------------

Assinatura
    public String getSoqlMapeamento(String pOrigemId, String pParentId)

Valor retornado
  	Retorna uma **String**.

Exemplo

   .. code-block:: apex

      **A fazer**


getMountFilter
--------------

Assinatura
    public String getMountFilter(List<String> pListValue)

Valor retornado
  	Retorna uma **String**.

Exemplo

   .. code-block:: apex

      **A fazer**