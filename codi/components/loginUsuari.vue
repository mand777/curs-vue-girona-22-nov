<template>
    <v-container>
        <v-row>
            <v-col style="margin-top:30vh" cols="12 md=4" offset-md="4">
                <v-text-field
                    label="usuari">
                </v-text-field>


                <v-text-field
                    label="password"
                    type="password">
                </v-text-field>
                <div style="color:green">Molt bé, tens majúscules i minúscules</div>
                <div style="color:red">Ep, cal posar alguna majúscula i minúscula</div>
                <div style="color:green">Molt bé, tens més de 6 caràcters</div>
                <div style="color:red">Cal posar mínim 6 caràcters</div>
                <div style="color:green">Molt bé, tens algun caràcter especial</div>
                <div style="color:red">Cal posar algun caràcter especial</div>

            </v-col>
        </v-row>
    </v-container>
   
    
</template>