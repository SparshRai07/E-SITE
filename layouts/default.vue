<template>
  <v-card>
    <v-layout>
      <!-- <v-system-bar color="deep-purple darken-3"></v-system-bar> -->

      <v-app-bar
        color="#1d4ed8"
        prominent
      >
        <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

        
        <v-toolbar-title class="logo-title">
          <span class="logo-highlight"></span>ⒺⓈⒽⓄⓅ®
        </v-toolbar-title>

        <v-spacer></v-spacer>

        
        

        <v-btn variant="text" icon="mdi-magnify"></v-btn>

        <v-btn variant="text" icon="mdi-cart" ></v-btn>

        <v-btn variant="text" icon="mdi-dots-vertical"></v-btn>
          

            <v-btn 
            
       variant = "text"
       prepend-icon="mdi-login"
       text="Logout"
       
       
       >
       Logout
       <v-progress-circular
       indeterminate
       color="primary">
       </v-progress-circular>
       </v-btn>



        <v-btn
          variant="text"
          class="login-button"
          @mouseenter="buttonHovered = true"
          @mouseleave="buttonHovered = false"
          :class="{ 'hovered':buttonHovered }"
          @click="$router.push('/login')"
             
        >
          LOGIN
        </v-btn>


      </v-app-bar>

      <v-navigation-drawer
        v-model="drawer"
        location="left"
        temporary
      >
        <v-list
          :items="items"
        ></v-list>
      </v-navigation-drawer>

      <v-main>
        <!-- CHANGEABLE PART -->
        <slot />
        <!-- CHANGEABLE PART -->
      </v-main>
    </v-layout>
  </v-card>
</template>


<script>

export default {
  data() {
    return {
      drawer: false, // Assuming 'drawer' is a boolean
      buttonHovered: false, // Assuming 'buttonHovered' is a boolean
      items: [], // Assuming 'items' is an array
    };
  },
  // other options...
}


</script>






<style scoped>

.login-button {
  color: #fff; 
  border: 1px solid #fff; 
  border-radius: 20px; 
  padding: 8px 20px; 
  transition: background-color 0.3s ease; 
}

.login-button:hover {
  background-color: #fff;
  color: #000; 
}

.logo-title {
  font-family: 'Arial', sans-serif; 
  font-size: 24px; 
}

.logo-highlight {
  color: black
}

.hovered {
  background-color: #84cc16 !important; 
}
.main-container {
  
  background-image: url('~/static/topography.svg');
  
  background-repeat: no-repeat;
  background-size: cover; 
}
</style>