<template>
  <div class="hello">
      <ion-list>
        <ion-item v-for="post in posts" :key="post.data.id">
          <img :src="post.data.thumbnail" alt="thumb" class="thumbnail">
          <ion-label>{{ post.data.title }}</ion-label>
        </ion-item>
      </ion-list>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted() {
    axios.get('https://www.reddit.com/r/aww.json?raw_json=1')
      .then(response =>{
        // console.log(response.data.data.children);
        this.posts = response.data.data.children
      })
  },
  // la fonction data() permet d'affecter l'input "myInput" et non d'autre input
  // myInput est initilaisé à la valeur de base > vide.
  data(){
    return {
      posts: [],
      // myInput:''
    }
  },
  methods: {
    // handleClick() {
    //   alert(this.myInput);
      // this.myInput permet de préciser que l'on veut spécifiquement la valeur de myInput qui a été modifié par le handleClick
    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .thumbnail{
    width: 60px;
    height: 60px;
    border-radius: 30px;
    margin-right: 16px;
    margin-top: 10px;
    margin-bottom: 10px;
  }
</style>
