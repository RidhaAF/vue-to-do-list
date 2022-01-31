<template>
  <div id="app">
    <h2>What I do Today?</h2>
    <div class="homework">
      <div v-for="task in tasks" v-bind:key="task.id" class="task">
        <p>{{ task.title }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data: function () {
    return {
      tasks: [
        {
          id: 1,
          title: "Membersihkan Toilet",
        },
        {
          id: 2,
          title: "Ngoding Flutter",
        },
        {
          id: 3,
          title: "Beli Macbook Pro",
        },
      ],
    };
  },
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
