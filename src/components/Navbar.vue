<template>
  <div>
    <nav>
      <router-link class="nav-item" to="/">Home</router-link>
      <router-link class="nav-item" to="/novo-produto">Novo produto</router-link>
      <router-link class="nav-item" to="/novo-pedido">Novo pedido</router-link>
    
    </nav>
  </div>
</template>
<script>
export default {
  
}
</script>
<style scoped>
  nav {
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 20px;
  }

  .nav-item {
    padding: 15px 20px;
    text-decoration: none;
    color: #e3e3e3;
    background: #df2f07;
    margin-left: 20px;
    border-radius: 15px;
  }

  .nav-item:hover {
    color: #eafcea;
    background: #5e9fb3;
  }

</style>