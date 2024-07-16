<template>
  <div class="header">
    <img src="/src/assets/images/logo.png" alt="logo" class="logo" />
    <div class="profile">
      <RouterLink to="/" class="noti"> <font-awesome-icon icon="fa-solid fa-bell" /> </RouterLink>
      <img src="/src/assets/images/user.png" alt="user" />
      <a class="user-name"> Akkarapol</a>
    </div>
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
  border-radius: 10px;
  width: 50px;
  height: 50px;
  object-fit: cover;
}
.profile {
  display: flex;
  align-items: center;
  gap: 8px;
}
.profile img {
  border-radius: 50%;
  width: 32px;
  height: 32px;
  object-fit: cover;
}
.noti {
  display: flex;
}
.user-name {
  display: flex;
}
.logo {
  display: none;
}

@media only screen and (max-width: 600px) {
  .header {
    justify-content: space-between;
    height: 65px;
  }
  .noti {
    display: none;
  }
  .user-name {
    display: none;
  }
  .logo {
    display: flex;
  }
  .profile img {
    border-radius: 50%;
    width: 40px;
    height: 40px;
    object-fit: cover;
  }
}
</style>
