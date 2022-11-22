<template>
  <v-container>
    <v-row>
      <v-col cols="12" md="6">
        <v-textarea
          label="Tasques"
          placeholder="p.e: fer el llit"
          outlined
          v-model="laNovaTasca"

        ></v-textarea>
        <v-btn @click="afegirTasca()" :disabled=!tincText>afegir tasca</v-btn> 
      </v-col>
      <v-col cols="12" sm="6">
        TO DO LIST
        <br>
        <br>
        <v-row class="tasca" v-for="(el,index) in tasques">
            <v-col cols="8">
                <h2>{{el.text}} - {{index}}</h2>
            </v-col>
            <v-col cols="4">
                <v-checkbox v-model="el.feta"></v-checkbox>
            </v-col>   
        </v-row>
      </v-col>

    </v-row>
  </v-container>
</template>

<script>
export default{
    methods:{
        afegirTasca(){
            console.log("Afegint tasca...")
            
            if(this.laNovaTasca.length<=0){
                alert("El camp tasca no pot estar buit")
                return
            }
           
            var tasca={}
            tasca.text=this.laNovaTasca
            tasca.feta=false

            this.tasques.push(tasca)
            this.laNovaTasca=""
        }
    },
    data(){
        return{
            laNovaTasca:"",
            tasques:[
                {
                    text:"Fer el llit",
                    feta:true
                },
                {
                    text:"Fer els deures",
                    feta:true
                },
                {
                    text:"Anar a comprar",
                    feta:false
                }]
        }
       
    },
    computed:{
        tincText(){
            if(this.laNovaTasca.length<=0){
                return false
            }else{
                return true
            }
        }

    }
}
    
    
</script>
<style>
.tasca{
    background-color:darkgrey;
    margin-bottom: 10px;
    }
</style>