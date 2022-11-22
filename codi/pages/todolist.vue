<template>
  <v-container>
    <v-row>
      <v-col cols="12" md="6">
        TASQUES
        <br>
        <v-textarea
          label="Tasques"
          placeholder="p.e: fer el llit"
          outlined
        ></v-textarea>
        <v-btn text>afegir tasca</v-btn>  
      </v-col>
      
      <v-col cols="12" sm="6">
        TO DO LIST
        <br>
        <br>
        <v-row class="tasca" v-for="(el,index) in tasques">
            <v-col cols="8">
                {{el}}
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
    data(){
        return{
            tasques:[
                {
                    text: "Fer el llit",
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
       
    }
}
    
    
</script>
<style>
.tasca{
    background-color:darkgrey;
    margin-bottom: 10px;
    }
</style>