<template>
  <section class="container">
    <div>
      <div>adfasfhk</div>
      <div v-for="item in posts" :key="item.id">
        <span>{{item.title}}</span>
      </div>
    </div>
  </section>
</template>

<script>
  import axios from 'axios'

  export default {
    components: {},
    asyncData(conttxt){
      return axios.get('https://jsonplaceholder.typicode.com/posts')
        .then((res) => {
          return { posts: res.data.slice(0, 5) }
        })
    },
    head: {
      title: 'List of posts'
    }
  }
</script>

<style>
  .container {
    margin: 0 auto;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }

  .title {
    font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
    display: block;
    font-weight: 300;
    font-size: 100px;
    color: #35495e;
    letter-spacing: 1px;
  }

  .subtitle {
    font-weight: 300;
    font-size: 42px;
    color: #526488;
    word-spacing: 5px;
    padding-bottom: 15px;
  }

  .links {
    padding-top: 15px;
  }
</style>
