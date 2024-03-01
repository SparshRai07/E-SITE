<template>
  <v-card :loading="loading" class="mx-auto my-12" max-width="400">
    <template v-slot:loader="{ isActive }">
      <v-progress-linear
        :active="isActive"
        color="primary" 
        height="4"
        indeterminate
      ></v-progress-linear>
    </template>

    <v-img
      cover
      height="250"
      src="https://images.unsplash.com/photo-1546069901-ba9599a7e63c?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8M3x8Zm9vZHxlbnwwfHwwfHx8MA%3D%3D"
    ></v-img>

    <v-card-title class="text-h5 text-center pt-4">
    </v-card-title>

    <v-card-subtitle class="text-center">Local Favorite</v-card-subtitle>
 
    <v-card-text class="d-flex justify-center align-items-center flex-wrap">
      <div class="price-tag">
        PRICE: <span class="price">Rs.500</span>
        <span class="discounted-price">Rs.200</span>
      </div>
    </v-card-text>

    <div class="description">
      Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.
    </div>

    <v-divider class="mx-4 mb-1"></v-divider>

    <div class="action-buttons">
      <v-btn color="accent" class="white--text">
        <v-icon left>mdi-cart-plus</v-icon>
        ADD TO CART
      </v-btn>
    </div>

    <div class="quantity-selector">
      <v-btn color="secondary">
        <v-icon>mdi-minus</v-icon>
      </v-btn>
      <v-chip class="count-chip">1</v-chip>
      <v-btn color="secondary">
        <v-icon>mdi-plus</v-icon>
      </v-btn>
    </div>
  </v-card>
</template>

<script setup>
// Your script here
</script>

<style scoped>
.price-tag {
  background-color: #f0f0f0;
  padding: 5px 10px;
  border-radius: 10px;
  display: inline-flex;
  align-items: center;
}
.price {
  margin-right: 8px;
  color: #333;
}
.discounted-price {
  color: red;
  text-decoration: line-through;
}
.description, .action-buttons, .quantity-selector {
  text-align: center;
  margin: 10px 0;
}
.quantity-selector {
  display: flex;
  justify-content: center;
  align-items: center;
}
.count-chip {
  margin: 0 12px;
}
/* Adjust hover effect color to match your new scheme */
.hovered {
  background-color: #88aaff !important; /* Example: Lighter shade of your primary color */
}
</style>
