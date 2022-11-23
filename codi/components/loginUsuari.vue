<template>
    <v-container>
        <v-row>
            <v-col style="margin-top:30vh" cols="12 md=4" offset-md="4">
                <v-text-field
                    label="usuari"
                    v-model="usuari">
                </v-text-field>

                <v-text-field
                    label="password"
                    type="password"
                    v-model="contrasenya">

                </v-text-field>
                <div v-if="siHiHaMajusculesMinuscules" style="color:green">Molt bé, tens majúscules i minúscules</div>
                <div v-else style="color:red">Ep, cal posar alguna majúscula i minúscula</div>
                <div v-if="siHiHaMesDe6Caracters" style="color:green">Molt bé, tens més de 6 caràcters</div>
                <div v-else style="color:red">Cal posar mínim 6 caràcters</div>
                <div v-if="siHiHaCaractersEspecials" style="color:green">Molt bé, tens algun símbol d'exclamació</div>
                <div v-else style="color:red">Cal posar algun símbol d'exclamació</div>
                <v-btn>login</v-btn>

            </v-col>
        </v-row>
    </v-container>
</template>

<script>

export default{
    data(){
        return{
            usuari:"",
            contrasenya:""

        }
    },
    methods:{
        conteLletres(str){
            return /[a-zA-Z]/.test(str)
        }

    },

    computed:{
        siHiHaMajusculesMinuscules(){
            let textOriginal=this.contrasenya
            let hihaMajuscules=false
            let hihaMinuscules=false

            for(var i=0;i<textOriginal.length;i++){
                let caracter=textOriginal[i]

                if(this.conteLletres(caracter)){

                if(caracter.toUpperCase()===caracter){
                    hihaMajuscules=true
                }else{
                    hihaMinuscules=true
                }
            }
        
            }
            return hihaMajuscules&&hihaMinuscules
 
        },
        siHiHaMesDe6Caracters(){
            // fem algo i tornem a true si hi ha mes de 6 car
            if(this.contrasenya
            &&typeof(this.contrasenya)=="string"
            &&this.contrasenya.length>=6){
                return true}
             //tornem fals
            return false

        },
        siHiHaCaractersEspecials(){
            let textOriginal=this.contrasenya
            let hiHaUnSimboldExclamacio=false
            //per cada lletra de la cadena de text mirem si 
            for(let i=0;i<textOriginal.length;i++){
                let caracter=textOriginal[i]
                //la lletra es un simbol dexclamacio i 
                if(caracter=="!"){
                //si ho es, canviem la variable boleana
                    hiHaUnSimboldExclamacio=true
                }    
            }
            return hiHaUnSimboldExclamacio
        }
    } 
}
</script>