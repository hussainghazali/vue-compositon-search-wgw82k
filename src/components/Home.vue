<template>
<div>
  <h1>Search Example</h1>
  <input type="text" v-model="search" placeholder="Search in blog title" />

  <div id="blog-conteiner">
    <div class="card" v-for="title in searchFunction" :key="title">
      {{title.title}}
    </div>
  </div>
<div id="blog-conteiner">
<div class="card" v-for="user in user" :key="user">
  {{user.username}}
</div>
</div>
</div>
</template>

<script>
import { ref, computed } from "vue";
import User from '../data/user.json'
export default {
  name: 'Home',
  setup() {

    const user = User

    const search = ref("")

    const blogs = ref([
      {
        id: 1,
        title: "Lorem ipsum dolor sit amet",
      },
      {
        id: 2,
        title: "consectetur adipisicing elit",
      },
      {
        id: 3,
        title: "Commodi qui, ex omnis laboriosam at",
      },
      {
        id: 4,
        title: "quisquam nostrum consequatur iure incidunt aut erro",
      },
      {
        id: 5,
        title: "molestias cupiditate quaerat doloremque",
      },
      {
        id: 6,
        title: " assumenda numquam magnam architecto non",
      },
      {
        id: 7,
        title: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
      },
    ]);

    const searchFunction = computed(() => {
      return blogs.value.filter((item) => {
        return item.title.toLowerCase().includes(search.value);
      })
    })

    return {
      search, blogs, searchFunction, user
    }
  }
}
</script>

<style>
  #blog-container {
    display: flex;
    flex-wrap: wrap;
  }
  .card {
  border-radius: 5px;
  box-shadow: rgba(0, 0, 0, 0.3) 0 5px 10px;
  margin: 10px;
  width: 40%;
  }
</style>