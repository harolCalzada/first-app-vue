<template>
    <ul class="list-group">
    <li v-for="(tarea, indice) of tareas"
          class="list-group-item"
          v-bind:class="{terminada: tarea.terminada}">
           {{tarea.texto}}
           <span class="pull-right">
               <button type="button"
                             class="btn btn-success
                             btn-xs glyphicon glyphicon-ok"
                             v-on:click="tarea.terminada = !tarea.terminada"
                             >

               </button>
               <button type="button"
                             class="btn btn-danger
                             btn-xs glyphicon glyphicon-remove"
                             v-on:click="borrar(indice)">

               </button>
           </span>
    </li>
    </ul>
</template>

<script type="text/javascript">
export default{
    props:['tareas'],
    methods:{
        borrar(indice){
            this.tareas.splice(indice, 1);
        }
    }
}
</script>

<!-- con scoped me aseguro q los estilos solo seran para este componente, en caso comprario se aplicara a todo el template-->
<style type="text/css" scoped>
    .terminada{
        color: gray;
        text-decoration: line-through;
    }
</style>