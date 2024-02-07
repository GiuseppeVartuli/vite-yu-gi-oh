<script>
export default {
  name: "AppHeader",
};
</script>

<template>
  <header>
    <div class="container">
      <img
        src="https://i.pinimg.com/originals/7f/7b/1d/7f7b1dea480069cfa587e5fd24eea4f9.jpg"
        alt="logo_yugioh"
      />
      <h1>Yu-Gi-OH! Api</h1>
    </div>
  </header>
</template>

<style scoped>
.container {
  display: flex;
  align-items: center;
  margin-left: 35px;
  & img {
    height: 100px;
    width: 150px;
  }
  & h1 {
    margin-left: 20px;
  }
}
header {
  width: 100%;
  height: 105px;

  background: white;
}
</style>
