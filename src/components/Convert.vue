<template>
  <div class="convert">
    <h2>{{coinA}} To {{coinB}}</h2>
    <input type="text" v-model="coinA_value" v-bind:placeholder="coinA">
    <button v-on:click="converter">Convert</button>
    <h2>{{coinB_value}}</h2>
  </div>
</template>

<script>
export default {
  name: 'Convert',
  props: ["coinA","coinB"],
  data(){
      return{
          coinA_value : "",
          coinB_value : 0
      }
  },
  methods:{
      converter(){
          let to = this.coinA+","+this.coinB;
          let url = "https://api.exchangeratesapi.io/latest?symbols=" + to;
          fetch(url).then(res =>{return res.json()}).then(json =>{
              console.log(json);
              let price = json["rates"][this.coinB];
              this.coinB_value = (price * parseFloat(this.coinA_value)).toFixed(2);
          });
      }
  }
}
</script>


<style scoped>
.convert{
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);

}
</style>