<template>
    <div class="screen screen-bg">
        <div class="cell cell-centered">
            <h1>{{headerText}}</h1>
            <button class="button" v-on:click="goToSizes" >{{buttonText}}</button>
        </div>
        <div class="cell cell-centered">
            <img class="sticker" :src="stickerUrl" />
        </div>
    </div>
</template>

<script>
import stickerUrl from '../assets/img/oeko.png';

export default {
    name: 'Header',
    methods:{ 
    goToSizes: function(event) {
        event.preventDefault();
        console.log("Go to sizes");
    },
    }
    ,
    data() {
        return {
            headerText : 'Entdecke unsere Hautfreundlichkeit',
            buttonText : 'JETZT DEINE GRÖSSE WÄHLEN',
            stickerUrl
        }
    }
}
</script>

<style lang="scss" scoped>
    h1 {
        max-width: 20ch;
    }
    .sticker {
      margin: 10px;
      top: 3%;
      right: 3%;
      width: 12%;
      max-width: 155px;
      position: absolute;
    }
</style>
