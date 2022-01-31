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
              <div class="col-md-3">
                <form @submit.prevent="submitForm" class="d-flex mb-3 gap-2">
                  <input
                    type="text"
                    class="form-control"
                    name="title"
                    placeholder="Add task"
                  />
                  <input type="submit" class="btn btn-success" value="Add" />
                </form>
              </div>
              <div
                v-for="task in tasks"
                v-bind:key="task.id"
                class="task mb-4 col-lg-12 text-start"
              >
                <div class="form-check">
                  <input
                    class="form-check-input"
                    type="checkbox"
                    :checked="task.status"
                    @change="task.status = !task.status"
                  />
                  <label
                    class="form-check-label item"
                    :class="{ itemCompleted: task.status }"
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
  methods: {
    submitForm(event) {
      let title = event.target.elements.title.value;

      this.tasks.push({
        id: this.tasks.length + 1,
        title: title,
        status: false,
      });

      event.target.elements.title.value = "";
    },
  },
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

.itemCompleted {
  color: #1abc9c;
}
</style>
