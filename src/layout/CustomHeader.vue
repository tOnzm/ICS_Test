<template>
  <div class="header">
    <RouterLink to="/"> <font-awesome-icon icon="fa-solid fa-bell" /> </RouterLink>
    <img src="/src/assets/images/user.png" alt="user" />
    <a href=""> Akkarapol</a>
  </div>
</template>

<script setup></script>

<style scoped>
.header {
  background-color: var(--primary-color);
  color: var(--white);
  display: flex;
  align-items: center;
  gap: 16px;
  justify-content: end;
  height: 60px;
  padding: 0px 16px 0px 16px;
  z-index: 1;
}

img {
  border-radius: 50%;
  width: 32px;
  height: 32px;
}
</style>
