<template>
<div>
    <h2>{{ tituloMayuscula() }}</h2>
    <h3>Tareas a hacer: {{numTareas}}</h3>
</div>

</template>

<script type="text/javascript">
import {bus} from './main.js'
export default {
    props: ['titulo'],
    data(){
        return {
            numTareas: 0
        }
    },
    methods:{
        tituloMayuscula(){
            return this.titulo.toUpperCase();
        }
    },
    created(){
        bus.$on('actualizarContador', (numTareas)=>{
            this.numTareas = numTareas;
        })
    }

}
</script>

<style type="text/css">

</style>