
<template>
    <div class="col-md-8 m-auto col-12 pt-5" style="font-family:gilroy">
        <h3 style="font-family:gilroyf">Thank you for your order!</h3>
        <p>Currently we are processing your order</p>
        <p style="font-family:gilroyf">ORDER ID: {{order_id}}</p>
        <img src="../assets/success.svg" alt="">
    </div>
</template>
<script>
export default {
    data(){
        return{
            order_id:''
        }
    },
    created(){
        this.order_id = this.$route.params.id
    }
}
</script>

<style scoped>
@font-face {
  font-family: Gilroyf;
  src: url(../assets/font/Gilroy-ExtraBold.otf);
}
@font-face {
  font-family: Gilroy;
  src: url(../assets/font/Gilroy-Light.otf);
}
</style>