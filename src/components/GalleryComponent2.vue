<template>
    <div id="GalleryComponent2">
        <p> {{  mensaje  }}</p>
        <button v-on:click="saludar"> Saludo</button>
        <hr>
        <h2> {{  title  }}</h2>
        <img v-for="imagen in images_src" v-bind:key="imagen" v-bind:src="imagen" alt="imagen del padre">
        <p>{{  pepito  }}</p>
    </div>
</template>

<script>
export default{
    name:'GalleryComponent2',
    props: {
        title: {
            type:String,
            default:'El titulo por defecto del prop',
        },
        images_src: {
            type: Array,
            required: true,
        },
        pepito: {
            type: String,
            default: 'Valor de pepito por defecto',
            required: true,
        }
    },
    data:function(){
        return{
            mensaje:'',
        }
    },
    methods:{
        saludar: function(){
            this.mensaje = 'Este mensaje es parte del componente Hijo';
        },
    }
}
</script>

<style scoped>
img{
    border-radius: 50%;
    width: 20%;
    border: 3px solid blue;
    display: inline-block;
}

#GalleryComponent2{
    background-color: darkseagreen;
    color:brown;
}
</style>