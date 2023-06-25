<template>
  <div class="about">
    <h1>This is an about page</h1>
    {{ userInfo }}
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>

<script>
export default {
  data() {
    return {
      userInfo: {},
    }
  },
  mounted() {
    console.log(import.meta.env.VITE_NAME);
    console.log(import.meta.env.VITE_TEXT);

    this.axios.get('https://randomuser.me/api/')
    .then((res) => {
      console.log(res);
      this.userInfo = res.data.results[0];
    })
  },
}
</script>