<template>
  <div id="app">
    <h3>El logo es parte del componente padre</h3>
    <img alt="Vue logo" src="./assets/logo.png">


    <GalleryComponent 
      title="Mensaje enviado desde el padre"
      v-bind:images_src = "arregloImagenes"
      pepito="mensaje del prop pepito"
    />

    <p>Esto es parte del componente padre</p>
    <hr>

    <GalleryComponent2 
      title="Gallery Component Version 2"
      v-bind:images_src = "arregloImagenes2"
      pepito="mensaje del prop pepito"
    />

    <hr>

    <GalleryComponent3 
      title="Gallery Component Version 3"
      v-bind:images_src = "arregloImagenes3"
      v-on:add ="agregarImagen"
      v-on:delete="eliminarImagen"
    />

  </div>
</template>

<script>
import GalleryComponent from '@/components/GalleryComponent.vue';
import GalleryComponent2 from '@/components/GalleryComponent2.vue';
import GalleryComponent3 from '@/components/GalleryComponent3.vue';

export default {
  name: 'App',
  components: {
    GalleryComponent,
    GalleryComponent2,
    GalleryComponent3
  },
  data: function(){
    return{
      arregloImagenes:[
        'https://2.bp.blogspot.com/-wl1pjP9hIXE/T7SbHP7pZ_I/AAAAAAAAAqE/bY9Gm9DOy6I/s1600/1213330412905_f.jpg',
        'https://4.bp.blogspot.com/-hHKfgJTJcq0/Tic9ooKwTzI/AAAAAAAAB68/Ch3vAvcXnzw/s1600/Cyd%2Bde%2BMyzar%2B%2528Zeta%2529%2B17.JPG',
        'https://i.pinimg.com/originals/34/6b/e2/346be288254eddc0654cdae08ab091de.jpg'
      ],
      arregloImagenes2:[
        'https://m.media-amazon.com/images/M/MV5BMzRkNWQwNmMtOTM0ZC00ZDhiLWI3OWQtZTVkZmM1OTAwYWJhXkEyXkFqcGdeQXVyMTYzNzk2MDE2._V1_.jpg',
        'https://mir-s3-cdn-cf.behance.net/projects/404/de7033172506273.Y3JvcCwxMjkwLDEwMDksMCwxODI.png',
        'https://i.pinimg.com/originals/f4/69/ea/f469ea0513f9ba1ccab309c62724641d.jpg'
      ],
      arregloImagenes3:[
        'https://i0.wp.com/codigoespagueti.com/wp-content/uploads/2021/08/My-Hero-Academia-Cosplay-femenino-de-All-Might-hace-del-poderoso-guerrero-una-tierna-waifu-compressed.jpg',
        'https://medias.spotern.com/spots/w640/66/66545-1532336916.jpg',
        'https://cdn.atomix.vg/wp-content/uploads/2020/12/bakugo.jpg'
      ],
    }
  },
  methods:{
    agregarImagen: function(src){
      this.arregloImagenes3.push(src);
    },
    eliminarImagen: function(indice){
      this.arregloImagenes3.splice(indice,1);
    },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: lightcyan;
}
</style>
