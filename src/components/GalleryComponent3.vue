<template>
    <div id="GalleryComponent3">
        <p> {{  mensaje  }}</p>
        <button v-on:click="saludar"> Saludo</button>
        <hr>
        <h2> {{  title  }}</h2>

        <div id="contenedorPadre">
            <div class="contenedorImagenes" v-for="(imagen,index) in images_src" v-bind:key="imagen">
            <img  v-bind:src="imagen" alt="imagen del padre">
            <button v-on:click="eliminar(index)">Eliminar</button>
        </div>

        </div>



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
        eliminar: function(indice){
            this.$emit('delete', indice);
        },
    }
}
</script>

<style scoped>
img{
    border-radius: 50%;
    width: 100%;
    border: 3px solid blue;

}

#GalleryComponent3{
    background-color: lightcoral;
    color: bisque;
}

.contenedorImagenes{
    width: 30%;
    display: inline-block;
}

#contenedorPadre{

}
</style>