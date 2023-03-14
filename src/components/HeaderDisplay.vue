<template>
  <header class="header">
    <h2>weather app</h2>
    <p>{{ username }}님 반갑습니다!</p>
  </header>
</template>

<script>
export default {
  username: "jin",
};
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
  background: linear-gradient(to right, #ee9ca7, #ffdde1);
}
.header h2 {
  color: #fff;
}
</style>
