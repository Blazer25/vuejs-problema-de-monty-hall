<template>
  <div class="portas">
      <div class="area-da-porta">
          <div class="frame-da-porta" :class="{ selecionada: selecionada && !aberta }">
              <Premios v-if="aberta && temPremio" />
          </div>

          <div class="porta" @click="selecionada = !selecionada" :class="{ aberta }">
            <div class="numero-porta" :class="{ selecionada }">{{ numero }}</div>
          <div class="macaneta" :class="{ selecionada }" @click="aberta = true"></div>
      </div>
      </div>

  </div>
</template>

<script>
import Premios from './Premios.vue'

export default {
name: 'Porta-',
components:{
    Premios
},
props: {
    numero:{},
    temPremio:{type: Boolean}
    },
    data(){
        return{
            aberta: false,
            selecionada: false
        }
    }
}
</script>

<style>
   .portas .area-da-porta{
       position: relative;
       width: 200px;
       height: 300px;
       border-bottom: 10px solid #808080;
       margin-bottom: 25px;
       font-size: 3rem;
       display: flex;
       justify-content: center;
   }

   .portas .area-da-porta .frame-da-porta{
       display: flex;
       justify-content: center;
       align-items: flex-end;
       position: absolute;
       width: 180px;
       height: 297px;
       border-right: 5px solid #000000;
       border-top: 5px solid #000000;
       border-left: 5px solid #000000;
   }

      .portas .area-da-porta .porta{
       position: absolute;
       top: 5px;
       width: 180px;
       height: 296px;
       background-color: #d2691e;
       display: flex;
       flex-direction: column;
       align-items: center;
   }

      .portas .area-da-porta .porta .numero-porta.selecionada{
          color: #000000;
      }

   .portas .area-da-porta .porta .macaneta{
       height: 20px;
       width: 20px;
       border-radius: 10px;
       background-color: #000000;
       align-self: flex-start;
       margin-left: 20px;
       margin-top: 95px;
   }

   /* Quando selecionado */
      .portas .area-da-porta .frame-da-porta.selecionada{
       border-right: 5px solid white;
       border-top: 5px solid white;
       border-left: 5px solid white;
   }

   .portas .area-da-porta .porta .numero-porta.selecionada{
       color: white;
    
   }

   .portas .area-da-porta .porta .macaneta.selecionada{
       background-color: white;
   }

   /* Quando aberta */
   .portas .area-da-porta .porta.aberta{
       background-color: rgb(91, 91, 91);
   }

   .portas .area-da-porta .porta.aberta .macaneta{
       display: none;
   }   

   .portas .area-da-porta .porta.aberta .numero{
       display: none;
   }     

</style>