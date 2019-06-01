<template> 
<div class="conversor">
    
    <h2> {{moedaA}} Para {{moedaB}} </h2>
    <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA">
    <input type="button" value="Converter" v-on:click="converter">
    <h2>{{moedaB_value}}</h2>

</div>
</template>

<script>
export default {
    name: "Conversor",
    props: ["moedaA", "moedaB"],
        data(){
            return {
                moedaA_value :"",
                moedaB_value :0
            };
        },
    methods:{

        converter(){
            let de_para = this.moedaA + "_" + this.moedaB;
            let url = "https://free.currconv.com/api/v7/convert?q="+ de_para +"&compact=y&apiKey=56b89a9dd51ce9c215f6";

            fetch(url).then(res => {
                return res.json();
            })
                      .then(json => {
                          let cotacao = json[de_para].val;
                          this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
                      });

        }
    }
};
</script>

<style scoped> 

.conversor {
    max-width: 300px;
    border-left: 6px solid blue;
    border-radius: 3px;
    background-color: lightgrey;
    padding: 20px;
    box-shadow: 3px 3px 6px gray;
}

</style>
