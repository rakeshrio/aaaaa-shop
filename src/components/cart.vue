<template>
  <div class="col-md-12 pb-5  m-0 p-0" style="background:#F2F2F2">
      <div class="fixed-bottom display-mobile mobile-panel col-12 m-0 p-0 ">
        <div class="col-md-12 m-0 p-0 py-2" style="background:#4e44e8"  @click="goto">
          <button style="letter-spacing:2px; border:none; background:transparent; color:white; letter-spacing:2px; font-family:gilroy">CHECKOUT</button>
        </div>
      </div>
      <div class="col-md-10 pt-0 row m-auto p-0">
            <div class="col-md-8 mar">
                <div class="col-md-12 p-2" style="background:white">
                    <div class="col-md-12 border-bottom position-sticky d-flex m-auto pb-3" style="justify-content:space-between">
                        <div><p class="mb-0"  style="font-family:gilroyf; font-size:20px; letter-spacing:1px">MY BAG</p></div>
                        <div><p class="mb-0" style="font-size:12px; font-family:gilroy">Items are Available</p></div>    
                    </div>
                    <div class="col-md-12 row">
                        <div class="col-md-4"><img :src="cartdata[0].selectedItem.image" alt="" width="100%"></div>
                        <div class="col-md-8 mt-4" style="font-family:gilroy">
                            <div class="col-md-12 text-left">
                                <h1 class="font2 mb-2 m-0 p-0" style="">
                                {{ cartdata[0].selectedItem.price | currency }}
                                </h1>
                                <p class="mb-0 pb-2" style="">{{ cartdata[0].make_model }}</p>
                                <div class="d-flex">
                                  <p class="mb-0 pb-2" style="font-size:12px">Color: {{ cartdata[0].selectedItem.color }}</p>
                                  <p class="mb-0 pb-2 pl-3" style="font-size:12px">Variant:  {{ cartdata[0].selectedItem.variant }}</p>
                                </div>
                                <p>Qty : 1</p>
                            </div>
                            <div class="col-md-12 text-right">
                                <P> <strong>Subtotal</strong>  : {{ cartdata[0].selectedItem.price | currency }}</P>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="col-md-12 m-0 mt-3 p-0" style="background:white">
                    <div class="col-md-12 row p-4">
                        <div class="col-md-2 col-2 m-0 p-0">
                            <img class="wid" src="../assets/truck.png" alt="" >
                        </div>
                        <div class="col-md-10 col-10 text-left ">
                            <p class="mb-0" style="font-family:gilroyf">FREE STANDARD DELIVERY</p>
                            <P class="mb-0" style="font-family:gilroy">Faster delivery options are available for local Zones.</P>
                        </div>
                    </div>
                </div>
                <div class="col-md-12 m-0 mt-3 p-0" style="background:white">
                    <div class="col-md-12 row p-4">
                        <div class="col-md-2 m-0 p-0 col-2">
                            <img class="wid" src="../assets/time.png" alt="" >
                        </div>
                        <div class="col-md-10 col-10 text-left ">
                            <p class="mb-0" style="font-family:gilroyf">48 hrs commitment Promise</p>
                            <P class="mb-0" style="font-family:gilroy">Vehicles delivered within the promised time. </P>
                        </div>
                    </div>
                </div>
                <div class="col-md-12 m-0 mt-3 p-0" style="background:white">`
                  `
                    <div class="col-md-12 row p-4">
                        <div class="col-md-2 m-0 p-0 col-2">
                            <img class="wid " src="../assets/corona.png" alt="" >
                        </div>
                        <div class="col-md-10  col-10 text-left ">
                            <p class="mb-0" style="font-family:gilroyf">Beyond Clean and more than just shine</p>
                            <P class="mb-0" style="font-family:gilroy">All vehicles are sanitised and free from corona virus !  </P>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-md-4 mar">
                <div class="col-md-12 p-3 " style="background:white">
                   <div class="col-md-12 m-0 p-0 border-bottom">
                       <p class="m-0 mb-2 text-left " style="font-family:gilroyf;font-size:20px; letter-spacing:1px">Total</p>
                   </div>
                   <!-- <div class="col-md-12 mt-2 m-0 p-0 text-left">
                       <p>Subtotal</p>   
                    </div> -->
                    <div class="col-md-12 row p-3 mt-2" style="justify-content:space-between" v-if="currentSelected[0].additional_cost.length>1">
                     
                          <div class="col-md-12 col-12 d-flex" style="justify-content:space-between"  v-for="(data, index) in currentSelected[0].additional_cost" :key="index">
                              <P class="mb-2" style="font-family:gilroyf">{{ data.name }} </P>
                              <p class="mb-2" style="font-family:gilroy; font-size:13px">{{ data.price | currency }}</p>
                          </div>
                          
                          <div class="col-md-12 col-12 d-flex" style="justify-content:space-between" v-for="(data, index) in cartdata[0].addons" :key="index">
                              <P class="mb-2" style="font-family:gilroyf">{{ data.name }} </P>
                              <p class="mb-2" style="font-family:gilroy; font-size:13px">{{ data.description  }}</p>
                          </div>

                          <div class="col-md-12 mt-2 col-12 d-flex" style="justify-content:space-between">
                              <P class="mb-2" style="font-family:gilroyf">Your Total</P>
                              <p class="mb-2" style="font-family:gilroy; font-size:13px">{{ totalPrice | currency }}</p>
                          </div>
                          
                          <div class="col-md-12 mt-2 col-12" >
                            <p class="mb-1"><span class="badge badge-danger">{{booking_type.booking_type}}</span></p>
                            <p class="badge">Amount payable at store {{priceToPayAtStore | currency}} at the 	time of delivery</p>
                          </div> 
                    </div>
                    <div class="col-md-12 m-0 p-2" style="background:#4e44e8"  @click="goto">
                        <button style="letter-spacing:2px; border:none; background:transparent; color:white; letter-spacing:2px; font-family:gilroy">CHECKOUT</button>
                    </div> 
                    <div class="col-md-12 mt-5 m-0 p-0 text-left">
                        <p class="mb-0" style="font-family:gilroy">We Accept all types of cards</p>
                        <img src="https://2giacm20c02m4btu7z2sal9f-wpengine.netdna-ssl.com/wp-content/uploads/2018/12/accepted-payment-methods-2.png" width="90%" height="auto" alt="">
                    </div>
                </div>
                <div class="col-md-12 border mt-2 p-3 text-left" style="background:white;">
                    <p class="mb-2 " style="font-size:14px;font-family:gilroy">Fulfilled By :</p>
                    <p class="mb-0" style="font-family:gilroyf; letter-spacing:1px" >{{ cartdata[0].selectedItem.dealer.name}}</p>
                </div>

            </div>
      </div>
  </div>
</template>


<script>
const axios = require("axios");
import * as _ from "lodash";
export default {
  data() {
    return {
      superset: "",
      superdata: [],
      currentSelected: [],
      currentPrice: 0,
       loading: false,
       booking_type:[]
    };
  },
  methods: {
    goto() {
      // this.$router.push(
      //   "/checkout/" + this.$route.params.id + "/" + this.booking_type.booking_type
      // );

      this.$router.push({ path: "/checkout/" + this.$route.params.id + "/" + this.currentSelected[0].id, query: { booking_type: this.booking_type.booking_type }})
    },
    fetchDetail() {
      this.$store.dispatch("getModelsWithoutDealer", {
        id: this.$route.params.id,
      });
    },
  },

  created() {
    window.console.log(this.cartdata);
    this.fetchDetail();
    this.superset = this.$route.params.value;
    this.booking_type = this.$route.query

    axios
      .get(
        "https://ontrack-backend-express-v1.herokuapp.com/api/otr_models/model-data-with-dealer/" +
          this.$route.params.id
        )
      .then((result) => {
        this.vehicle = result.data;
        this.variantsList = _.uniqBy(this.vehicle.superset, "variant");
        this.currentImage = this.vehicle.hero_image;
        this.currentSelected.push(this.vehicle.superset[0]);
        this.loading = false;
      })
      .catch((error) => {
        throw new Error(`API ${error}`);
      });
      
  },
  watch: {
    cartdata() {
      //    this.superdata =
      //     this.cartdata.superset.filter(x=>{
      //     return x.id == this.superset
      //     })
    },
  },
  computed: {
    priceToPayAtStore(){
      if(this.booking_type.booking_type == 'Book bike at Rs. 1000'){
        return this.totalPrice - Number(1000)
      }
      else if(this.booking_type.booking_type == 'book bike at rupees Rs. 20000'){
        return this.totalPrice - Number(20000)
      }
      else if(this.booking_type.booking_type == 'book bike at rupees Rs. 30000'){
        return this.totalPrice - Number(30000)
      }else{
        return 0
      }
    },
    cartdata() {
      return JSON.parse(localStorage.getItem('cart'))
    },
    totalPrice(){
        var addonsPrice = 0
        if(this.cartdata[0].addons.length > 0){
            for(var i in this.cartdata[0].addons){
                addonsPrice = addonsPrice + Number(this.cartdata[0].addons[i].price)
            }
        }
        return Number(this.cartdata[0].selectedItem.price) + Number(addonsPrice)
    }
  },
};
</script>

<style scoped>
@font-face {
  font-family: Gilroy;
  src: url(../assets/font/Gilroy-Light.otf);
}
@font-face {
  font-family: Gilroyf;
  src: url(../assets/font/Gilroy-ExtraBold.otf);
}
.wid{
  width: 45%;
}
.display-mobile{
  display: none ;
}
.font2 {
  font-size: 18px;
  font-weight: bold;
  font-family: Gilroyf;
  color: #484848;
}
.start-purchase{
  border: 1px solid hsl(28, 91%, 54%);
  background-color: #F75D34;
  padding: 0px 20px;
  width: 90%;
  font-size: 12px;
  border-radius: 0px;
  color:white;
  font-weight: 700;
}
.reserve{
  border: 1px solid #f5821f;
  background-color: #ffffff;
  padding: 0px 20px;
  width: 90%;
  font-size: 12px;
  border-radius: 0px;
  font-weight: 700;

}



@media all and (max-width: 600px) {
  .bnm {
    display: none !important;
  }
  .wid{
    width: 100% !important;
    height: auto;
  }
  .mar{
    padding: 0;
  }
  .display-mobile{
  display: block !important;
  }
  /* .display-mobile1{
    display: block !important;
  } */
}
.labels {
  font-size: 13px;
  color: gray;
}
.top-head{
    background-color: #4E44D8;
}
.btn{
    background-color: black;
    border: 1px solid black;
    color: white;
}
</style>
