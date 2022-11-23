<template>
  <v-app>
    <v-container> 
      <v-row>
        <v-col style="background-color:black">
          <v-btn dark to="/">inici</v-btn>
          <v-btn dark to="/todolist">to do list</v-btn>
          <v-btn dark to="/textfields">exercici textfields</v-btn>
          <v-btn dark to="/login">login</v-btn>
        </v-col>
      </v-row>
    </v-container>
    <v-main>
      <nuxt/>
    </v-main>
  </v-app>
</template>

<script>
</script>