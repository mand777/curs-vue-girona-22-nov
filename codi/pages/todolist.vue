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
      
      <v-col cols="12" md="6">
        TO DO LIST
        <br>
        <v-row class="tasca" v-for="tasca in tasques">
            <v-col cols="8">
                <h2>{{tasca.text}}</h2>
            </v-col>
            <v-col cols="4">
                <v-checkbox v-model="tasca.feta"></v-checkbox>
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
                    tasca: "Fer el llit",
                    feta:true
                },
                {
                    tasca:"Fer els deures",
                    feta:true
                },
                {
                    tasca:"Anar a comprar",
                    feta:false
                }]
        }
       
    }
}
    
    
</script>