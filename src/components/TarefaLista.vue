<template>
    <BoxTarefa>
        <div class="columns">
            <div class="column is-7">{{tarefa.descricao || 'Tarefa sem descrição'}}</div>
            <div class="column">
                <CronometroPrincipal :tempoEmSegundos="tarefa.duracaoEmSegundos" />
            </div>
        </div>
    </BoxTarefa>
</template>

<script lang="ts">
import ITarefa from "@/interfaces/ITarefa";
import { defineComponent, PropType } from "vue";
import CronometroPrincipal from "./CronometroPrincipal.vue";
import BoxTarefa from "./BoxTarefa.vue";

export default defineComponent({
   name: "TarefaLista",
   components: {
    CronometroPrincipal,
    BoxTarefa
},
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
});
</script>

