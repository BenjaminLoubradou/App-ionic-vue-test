<template>
  <div class="hello">
    <ion-label>Label</ion-label>
    <div>
      <ion-button @click="handleClick">Default</ion-button>
    </div>
    
    <ion-item>
      <ion-label position="floating">Floating Label</ion-label>
      <ion-input :value="myInput" @input="myInput=$event.target.value"></ion-input>
      <!-- on récupère la valeur que l'utilisateur va taper dans l'input -->
  </ion-item>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  // la fonction data() permet d'affecter l'input "myInput" et non d'autre input
  // myInput est initilaisé à la valeur de base > vide.
  data(){
    return {
      myInput:''
    }
  },
  methods: {
    handleClick() {
      alert(this.myInput);
      // this.myInput permet de préciser que l'on veut spécifiquement la valeur de myInput qui a été modifié par le handleClick
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
