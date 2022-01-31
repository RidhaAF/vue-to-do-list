<template>
  <div id="app">
    <div class="container">
      <div class="row header mb-5 p-3">
        <div class="col-lg-12">
          <h2 class="fw-bold">What I do Today?</h2>
        </div>
      </div>
      <div class="row content">
        <div class="col-lg-12">
          <div class="homework">
            <div class="row">
              <div
                v-for="task in tasks"
                v-bind:key="task.id"
                class="task mb-4 col-lg-12 text-start"
              >
                <div class="form-check">
                  <input
                    class="form-check-input"
                    onclick=""
                    type="checkbox"
                    value=""
                    id="flexCheckDefault"
                  />
                  <label
                    class="form-check-label item"
                    v-bind:class="{ 'item-completed': task.status }"
                    for="flexCheckDefault"
                  >
                    {{ task.title }}
                  </label>
                </div>
              </div>
            </div>
          </div>
        </div>
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
          status: false,
        },
        {
          id: 2,
          title: "Ngoding Flutter",
          status: false,
        },
        {
          id: 3,
          title: "Beli Macbook Pro M1",
          status: false,
        },
        {
          id: 4,
          title: "Belajar Vue.js",
          status: false,
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

.header {
  background: #1abc9c;
}

.header h2 {
  margin: 0;
}

.task .item {
  font-size: 20px;
}

.item-completed {
  color: #1abc9c;
}
</style>
