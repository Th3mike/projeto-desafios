<template>
    <div class="conversor">

        <h2>{{moedaA}} para {{moedaB}}</h2>
        <input type="text"  v-model="moedaA_value" :placeholder="moedaA">
        <input type="button" value="Converter"  v-on:click="converter">
        <h2>{{moedaB_value}}</h2>
    </div>
</template>

<script>
    export default {
        name : "Conversor",
        props: ["moedaA","moedaB"],
        data(){
            return {
                moedaA_value: "",
                moedaB_value: 0
            };
        },
        methods:{
            converter() {
                let de_para = this.moedaA + "_" + this.moedaB;
                var apiKey = 'a7bb3a7df16277a000c1';
                let url = "https://api.currconv.com/api/v7/convert?q=" + de_para + '&compact=ultra&apiKey=' + apiKey;
                fetch(url).then(res => {
                    return res.json();
                }).then(json => {
                        let cotacao = json[de_para].val;
                        this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
                    })
            }
        }
    };
</script>

<style scoped>
    .conversor{
        max-width: 300px;
        padding: 20px;
        box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    }
</style>
