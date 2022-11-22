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
        <v-btn @click="temperaturesAleatories()">aleatori</v-btn>
      </v-col>
      <v-col cols="12" md="6">
        Resultat
        <br>
        Mostres: {{tamanyArray}}
        <br>
        Mostres superiors a 50 graus:{{mesDe50}}
        <br>

        <v-sparkline
        :value="temperatures"
        :gradient="['red','blue']" 
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
    mounted(){
      //iniciem array de
      this.temperaturesAleatories()

    },
    data(){
      return{
        gradient:["red","blue"],
        temperatura:0,
        temperatures:[]
        
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
      },
      temperaturesAleatories(){
        console.log("Afegint temperatures aleatòries")
        //array amb 100 valors aleatoris creem array buit
        var nouArray=[]
        //repetim 100 vegades
        for(var i=0;i<100;i++){
          //afegim valors
          var valorAleatori=Math.random()*100
          var valorAleatoriEnter=this.processarEnter(valorAleatori)

          nouArray.push(valorAleatoriEnter)
        }
        //Assignem al array del component
        this.temperatures=nouArray

      },
      processarEnter(val){
        return parseInt(val)
      }
    },
    computed:{
      tamanyArray(){
        return this.temperatures.length
      },
      mesDe50(){
        var mostresDeMesDe50Graus=0
        this.temperatures.forEach((temperatura) => {
          if(temperatura>50){
            mostresDeMesDe50Graus++
          }
          
        })
        return mostresDeMesDe50Graus
      }
    },
    whatch:{
      temperatures(newValue,oldValue){
        console.log(newValue,oldValue)
      },
      mesDe50(newValue,oldValue){
        if(newValue>55){
          alert("ALERTA")
        }
      }
    }
  }
</script>
