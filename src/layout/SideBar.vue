<template>
  <div class="sidebar">
    <img src="/src/assets/images/logo.png" alt="" />
    <hr class="solid" />
    <div>
      <div class="place"></div>
      <p style="text-align: center">Place</p>
    </div>
    <hr class="solid" />
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.sidebar {
  position: absolute;
  left: 0;
  top: 0;
  background-color: var(--white);
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 100vh;
  width: 90px;
  z-index: 100;
  border-radius: 0px 50px 50px 0px;
  padding-top: 25px;
  gap: 24px;
  box-shadow: #00000025 0px 10px 10px 0px;
}
.sidebar img {
  width: 53px;
  height: 53px;
}

.place {
  background-color: var(--primary-color);
  width: 36px;
  height: 36px;
  border-radius: 10px;
}
hr.solid {
  border-top: 1px solid #e5e5e5;
  width: 100%;
}
</style>
