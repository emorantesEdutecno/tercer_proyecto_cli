<template>
    <div id="GalleryComponent3">
        <p> {{  mensaje  }}</p>
        <button v-on:click="saludar"> Saludo</button>
        <hr>
        <h2> {{  title  }}</h2>
        <img v-for="imagen in images_src" v-bind:key="imagen" v-bind:src="imagen" alt="imagen del padre">

        <hr>
        <form>
            <label for="nuevaImagen">Ingrese una imagen de internet:</label>
            <input type="text" id="nuevaImagen" v-model="newImage">
            <button v-on:click.prevent="agregar">Enviar al padre</button>
        </form>
    </div>
</template>

<script>
export default{
    name:'GalleryComponent3',
    props: {
        title: {
            type:String,
            default:'El titulo por defecto del prop',
        },
        images_src: {
            type: Array,
            required: true,
        },
    },
    data:function(){
        return{
            mensaje:'',
            newImage:'',
        }
    },
    methods:{
        saludar: function(){
            this.mensaje = 'Este mensaje es parte del componente Hijo';
        },
        agregar: function(){
            this.$emit('add', this.newImage);
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

#GalleryComponent3{
    background-color: lightcoral;
    color: bisque;
}
</style>