<template>
    <div class="screen screen-bg">
        <div class="container container-gradient">
            <div class="cell cell-centered">
                <h1>{{headerText}}</h1>
                <button class="button" v-on:click="goToSizes" >{{buttonText}}</button>
            </div>
            <div class="cell cell-centered forsticker">
                <img class="sticker" :src="stickerUrl" />
            </div>
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
    .forsticker {
        margin: initial;
        width: 45vw;
        text-align: right;
    }
    .sticker {
      margin: 10px;
      top: 3%;
      right: 3%;
      max-width: 155px;
      position: absolute;
    }

    @media screen and (max-width: 800px) {
    .sticker {
            right: -70%;
            top: -30%;
            max-width: 25vw;
    }
  }
</style>
