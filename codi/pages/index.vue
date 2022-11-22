<template>
  <v-container>
    <v-row>
      <v-col cols="12" md="6">
        <v-text-field 
          label="Temperatura"
          placeholder="Escriu la temperatura"
          type="number"
          v-model="temperatura"

        ></v-text-field>
        <v-btn @click="afegir()">afegir</v-btn>
        <v-btn @dblclick="netejar()">netejar</v-btn>
        <v-btn @mouseenter="borrar()">borrar l'últim</v-btn>
      </v-col>
      <v-col cols="12" md="6">
       Resultat
        <br>

        <v-sparkline
        :value="temperatures"
        ></v-sparkline>
    
        <pre>
          {{temperatures}}
        </pre>

      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default{
    data(){
      return{
        temperatura:0,
        temperatures:[33,24,41,23,44,11,23]
      }
    },
    methods:{
      afegir(){
        console.log("Afegint...")
        console.log("temperatura",this.temperatura)
        const tmp=parseFloat(this.temperatura)
        //parseInt per treure el decimal
        console.log("El tipus de temperatura és",
        typeof(this.temperatura))
        console.log
        ("El tipus de temperatura és",typeof(tmp))
        this.temperatures.push(tmp)
      },
      netejar(){
        console.log("Netejant...")
        this.temperatures=[]
        console.log(this.temperatures)
      },
      borrar(){
        console.log("Borrant l'últim")
        this.temperatures.pop()
      }
    }
  }
</script>
