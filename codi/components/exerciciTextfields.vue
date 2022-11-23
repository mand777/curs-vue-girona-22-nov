<template>
    <v-container>
        <v-row>
            <v-col col="12" md="6">
                <v-text-field
                label="Camp1"
                v-model="camp1">
                </v-text-field>

                <v-text-field
                label="Camp2"
                v-model="camp2">
                </v-text-field>
                <v-btn @click="mostraElsTextos()">mostrar a la consola</v-btn>
                <br>
                <v-btn @click="netejarElsTextos()">netejar camp de text</v-btn>
            </v-col>

            <v-col col="12" md="6">
                <div style="font-size:40px">{{camp1}}</div>
                <div style="font-size:40px" v-text="camp2"></div>
                <div style="font-size:40px" v-html="camp1.toLowerCase()+camp2"></div>

            </v-col>
        </v-row>
    </v-container>
</template>

<script>

//function emplenarElsTextos(){console.log('...')}

export default{
    data(){
        return{
            camp1:"",
            camp2:""
        }
    },
    methods:{
        //ES5borrarElsTextos:function(){console.log("---")}
        //ES6
        mostraElsTextos(){
            console.log("Estic dins")
            console.log("El camp 1 és",this.camp1)
            console.log("El camp 2 és",this.camp2)
        },
        netejarElsTextos(){
            this.camp1=""
            this.camp2=""
        }
    }
}


</script>