inMapMappingBuilder
===================


Atributos:
----------


+---------------+--------+------------------------------------------------------+-------------+
| Name          | Tipo   | Descrição                                            | Obrigatório |
+===============+========+======================================================+=============+
| origem-id     | String | Id do metadado Origem que o mapeamento é relacionado | Falso       |
+---------------+--------+------------------------------------------------------+-------------+
| mapeamento-id | String | Id do mapeamento a ser editado                       | Falso       |
+---------------+--------+------------------------------------------------------+-------------+


Eventos
-------


**onCancelar()**

    Evento chamado ao cancelar alguma etapa do processo de criação de mapeamentos.


**onCancelar()**

    Evento chamado ao salvar o mapeamento na última etapa do componente.


Exemplo:
--------
    .. code-block:: html

        <template>
            <template if:true={openmodel}>
                <c-in-map-mapping-builder origem-id="id do metadado Origem" mapeamento-id="id do mapeamento que será alterado" oncancelar={closeModal} onsave={onSaveMapBuilder}></c-in-map-mapping-builder>
            </template>
        </template>

    .. code-block:: javascript

        import { LightningElement, track } from 'lwc';

        export default class inMapMappingBuilderExample extends LightningElement {

            @track openmodel = true;

            closeModal() {
                this.openmodel = false;
            } 

            onSaveMapBuilder() {
                this.closeModal();
            }
        }

