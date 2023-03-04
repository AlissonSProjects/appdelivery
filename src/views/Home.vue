<template>
  <div>
    <NavbarVue />
    <h1 class="title"></h1>
    <img src="../assets/fast-delivery.png" alt="Fast Delivery" class="image">
  </div>
</template>

<script>
import NavbarVue from '../components/Navbar.vue'

export default {
  components: {
    NavbarVue
  }
}
</script>

<style>
.title {
  font-size: 3rem;
  text-align: left;
  color: #2c3e50;
  text-shadow: 2px 2px #ecf0f1;
}

.image {
  display: block;
  margin: 0 auto;
  max-width: 100%;
  height: auto;
  padding: 20px;
}
</style>