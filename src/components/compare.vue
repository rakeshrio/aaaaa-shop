<template>
        <div class="col-md-10  m-auto p-0">
            <div class="col-12 position-sticky text-left pl-2">
                <p style="font-size:14px; font-weight:600;"><span><img src="https://www.flaticon.com/svg/vstatic/svg/106/106729.svg?token=exp=1614172791~hmac=75241d992b439fbde09d0adcb95dbb45" width="5%" alt=""></span> Compare</p>
            </div>
         
            <p v-if="compareData => 3" class="my-5" @click="$router.push('/models')">
                <button class="p-2 px-3" style="background:#4e44d8; color:white; letter-spacing:1px; border:none">Add New Item</button>
            </p>
            <div class="col-md-12 m-0 p-0">
                <div class="col-md-8 m-auto p-0">
                    <div class="col-md-12 m-0 p-0 row">
                        <div class="col-md-4 m-0 p-0 col-4 card border-left-0 border-top-0 border-bottom-0 border-right" style="border-radius:0"  v-for="(data, index) in compareData" :key="index"> 
                            <!-- <p>{{index + 1}}</p> -->       
                            <div class="col-md-12" style="background:#F2F3F5;text-align: center;">
                                <img :src="data.hero_image" width="100%" alt="">  
                            </div>
                            <div class="col-md-12 py-2 text-left">
                                <p><strong style="font-size:0.6rem">{{data.make}} {{data.model}}</strong></p>
                            </div>    
                            <div class="col-md-12 py-2 text-left" style="background:#F2F3F5">
                                <p class="font9">Tank Capacity</p>
                                <p>{{data.tank_capacity}}L</p>
                            </div>
                            <div class="col-md-12 py-2 text-left">
                                <p class="font9">Fuel Type</p>
                                <p>{{data.fuel_type}}</p>
                            </div>
                            <div class="col-md-12 py-2 text-left" style="background:#F2F3F5">
                                <p class="font9">Start Type</p>
                                <p>{{data.start_type}}</p>
                            </div>
                            <div class="col-md-12 py-2 text-left">
                                <p class="font9">Engine CC</p>
                                <p>{{data.displacement}}CC</p>
                            </div>
                            <div class="col-md-12 py-2 text-left" style="background:#F2F3F5">
                                <p class="font9">Tyre Type</p>
                                <p>{{data.tyre_type}}</p>
                            </div>
                            <div class="col-md-12 py-2 text-left">
                                <p class="font9">Braking System</p>
                                <p>{{data.breaking_system}}</p>
                            </div>
                            <div class="col-md-12 py-2 text-left" style="background:#F2F3F5">
                                <p class="font9">Brake Type</p>
                                <p>{{data.brakes}}</p>
                            </div>
                            <div class="col-md-12 py-2 text-left">
                                <p class="font9">Speedometer</p>
                                <p>{{data.odometer}}</p>
                            </div>
                            <div class="col-md-12 py-2 text-left" style="background:#F2F3F5">
                                <p class="font9">Kerb Weight</p>
                                <p>{{data.weight}} KG</p>
                            </div>
                            <div class="col-md-12 py-2 text-left ">
                                <p class="font9">Mileage</p>
                                <p>{{data.mileage}} KM</p>
                            </div>
                            <div class="cross-container">
                                <p style="cursor:pointer
                                " @click="remove(index)"><i class="fa fa-times-circle" aria-hidden="true"></i></p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
</template>

<script>
export default {
    data(){
        return{
            compareData : ''
        }
    },
    computed:{
        // compareData(){
        //     return this.$store.state.compare
        // }
    },
    created(){
        this.compareData = JSON.parse(localStorage.compare)
        window.scrollTo(0,0);
    },
    methods:{
        remove(index){
            var data = this.compareData
            data.splice(index, 1)
            localStorage.compare = JSON.stringify(data)
            this.compareData = JSON.parse(localStorage.compare)
        }
    }
}
</script>

<style scoped>
p{
    margin-bottom: 0;
    font-size:10px
}
.position-sticky{
  position: -webkit-sticky;
  position: sticky;
  top: 0;
  background-color: #fff;
  padding: 20px;
  font-size: 20px;
  position: sticky !important;
    z-index: 999999;
    top: 0;
}
.font9{
    color:#C7B5BA;
    font-size:10px !important
}
.cross-container{
    position: absolute;
    right:30px;
  top:7px;
  z-index: 9999;
}
.cross-container .i{
    font-size:35px !important
}
</style>