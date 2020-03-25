inMapMappingList
================


Atributos:
----------


+-----------+--------+----------------------------------+-------------+
| Name      | Tipo   | Descrição                        | Obrigatório |
+===========+========+==================================+=============+
| title     | String | Título do cabeçalho              | Falso       |
+-----------+--------+----------------------------------+-------------+
| parent-id | String | Id do objeto "pai" do mapeamento | Falso       |
+-----------+--------+----------------------------------+-------------+


Exemplo:
--------
    .. code-block:: html

        <template>
            <template if:true={openmodel}>
                <c-in-map-mapping-list title="Mapeamentos Exemplo" parent-id="id do objeto pai"></c-in-map-mapping-list>
            </template>
        </template>