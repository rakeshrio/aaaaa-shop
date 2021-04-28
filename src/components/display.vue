<template>
 <div class="col-md-12 m-0 p-0" >
  <div class="col-md-8  m-auto py-5 p-0">
      <div class="col-md-12  row m-0 p-0">
        <div class="col-md-6 px-3 m-0 p-0">
          <div class="col-md-12 border p-0 ">
            <div class="col-md-12 px-3 row justify-content-between m-0 p-0" style="background:#ECEBF2">
              <h5 class="m-0 p-0 mt-2 ">{{vehicle.make}} {{vehicle.model}}</h5>
              <!-- <h6 class="mb-0">
                <transition name="fade">
                  <div class="col-md-12 m-0 p-0" v-if="variant">
                    
                    <span
                      v-for="(data, index) in selectColor"
                      :key="index"
                      @click="chooseColor(data.id, data.hex_color)"
                      v-bind:style="{ 'background-color': data.hex_color }"
                      class="dot mr-2 mt-2"
                    ></span>
                  </div>
                </transition>
              </h6> -->
            </div>
            <img class="onHover" width="100%" :src="currentImage" alt="" />
          </div>
        </div>
        <div class="col-md-6 px-3 container m-0 p-0">
          <div class="col-md-12 p-3 border p-0 ">
           
            <h5 class="text-left mb-5 h11">Specification</h5>
            <div class="col-md-12 row m-0 p-0 fgh" >
              <div class="col-md-4 col-4 m-0 mb-5 p-0">
                <div class="col-md-12 row m-0 p-0">
                  <div class="m-0 p-0 col-md-3 text-left box-data" >
                    <img src="https://book.on-track.in/assets/images/displacement-icon.svg" alt="" width="100%" >
                  </div>
                  <div class="m-0 p-0 col-md-9  pl-2 ali text-left">
                    <p class="classa" style="font-size:12px; padding-bottom:4px">Displacement</p>
                    <p class="classp" style="font-size:13px;color:#4e44d8">{{ vehicle.displacement}}  CC</p>
                  </div>
                </div>
              </div>
              <div class="col-md-4 col-4 m-0 mb-5 p-0">
                <div class="col-md-12 row m-0 p-0">
                  <div class="m-0 p-0 col-md-3 text-left box-data" >
                    <img src="https://book.on-track.in/assets/images/power-icon.svg" alt="" width="100%" >
                  </div>
                  <div class="m-0 p-0 col-md-9 pl-2  ali pl-1 vbn text-left">
                    <p class="classa" style="font-size:12px; padding-bottom:4px">Kerb Weight</p>
                    <p class="classp" style="font-size:13px;color:#4e44d8">{{ vehicle.weight }} Kg</p>
                  </div>
                </div>
              </div>
              <div class="col-md-4 col-4 m-0 mb-5 p-0">
                <div class="col-md-12 row m-0 p-0">
                  <div class="m-0 p-0 col-md-3 text-left box-data" >
                    <img src="https://book.on-track.in/assets/images/ignition-icon.svg" alt="" width="100%" >
                  </div>
                  <div class="m-0 p-0 col-md-9 pl-2  pl-1 ali text-left">
                    <p class="classa" style="font-size:12px; padding-bottom:4px">Ignition</p>
                    <p class="classp" style="font-size:13px;color:#4e44d8">{{ vehicle.start_type }}</p>
                  </div>
                </div>
              </div>
              <div class="col-md-4 col-4 m-0 p-0">
                <div class="col-md-12 row m-0 p-0">
                  <div class="m-0 p-0 col-md-3 text-left box-data" >
                    <img src="https://book.on-track.in/assets/images/top-speed-icon.svg" alt="" width="100%" >
                  </div>
                  <div class="m-0 p-0 col-md-9 pl-2  pl-1 ali text-left">
                    <p class="classa" style="font-size:12px; padding-bottom:4px">Fuel Type</p>
                    <p class="classp" style="font-size:13px;color:#4e44d8; text-transform:capitalize" >{{ vehicle.fuel_type }}</p>
                  </div>
                </div>
              </div>
              <div class="col-md-4 col-4 m-0 p-0">
                <div class="col-md-12 row m-0 p-0">
                  <div class="m-0 p-0 col-md-3 text-left box-data" >
                    <img src="https://book.on-track.in/assets/images/fuel-icon.svg" alt="" width="100%" >
                  </div>
                  <div class="m-0 p-0 col-md-9 pl-2  pl-1 ali text-left">
                    <p class="classa" style="font-size:12px; padding-bottom:4px">Mileage</p>
                    <p class="classp" style="font-size:13px;color:#4e44d8">{{ vehicle.mileage}} Kmpl</p>
                  </div>
                </div>
              </div>
              <div class="col-md-4 col-4 m-0 p-0">
                <div class="col-md-12 row m-0 p-0">
                  <div class="m-0 p-0 col-md-3 text-left box-data" >
                    <img src="https://book.on-track.in/assets/images/mileage-icon.svg" alt="" width="100%" >
                  </div>
                  <div class="m-0 p-0 col-md-9 pl-2  pl-1 ali text-left">
                    <p class="classa" style="font-size:12px; padding-bottom:4px">Fuel Capacity</p>
                    <p class="classp" style="font-size:13px;color:#4e44d8">{{ vehicle.tank_capacity }} L</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-12 mt-3 border p-3 m-0 p-0 ">
            <div class="col-md-12 ml-0 pl-0 text-left">
              <h6 class="h11">Product Highlights</h6>
                <li style="font-family:gilroy !important">All pictures shown are for pictorial illustration purpose only. Actual product may vary due to product enhancement.</li>
            </div>
            <div class="col-md-12 mt-5 p-2" style="background:#4e44d8" @click="bookNow()">
              <button style="border:none; background:transparent;color:white" >Proceed</button>
            </div>
          </div>
        </div>
        
      </div>
  </div>
        <section class="mobi-bg-white " >
          <div class="container-fluid box-container-fluid pt-4">
            <div class="container mt-4 pt-5">
              <div class="" style="font-family:gilroy !important">
                <div class="row pt-3 pb-5">
                  <div class="col-lg-12 ">
                    <h4 class="head-text text-center text-white mt-4 pt-5 pb-2 " style="font-family:gilroyf">Our Services</h4>
                  </div>
                  <div class="dash"></div>
                </div>
                <div class="row pt-5">
                  <div class="col-md-3 col-6 col-sm-12 text-center pt-2 pb-3 mt-1 mb-1 animated pulse infinite service-block">
                    <div class="service-icons mb-2">
                      <img src="https://book.on-track.in/assets/images/unlimited-kms.png" class="">
                    </div>
                    <div class="service-text text-white mt-2 ">Avoid<br>Financing Paperwork</div>
                  </div>

                  <div class="col-md-3 col-6 col-sm-12 text-center pt-2 pb-3 mt-1 mb-1 animated pulse infinite service-block">
                    <div class="service-icons mb-2">
                      <img src="https://book.on-track.in/assets/images/insurance.png" class="">
                    </div>
                    <div class="service-text text-white mt-2 ">Get It<br>Home Delivered</div>
                  </div>

                  <div class="col-md-3 col-6 col-sm-12 text-center pt-2 pb-3 mt-1 mb-1 animated pulse infinite service-block">
                    <div class="service-icons mb-2">
                      <img src="https://book.on-track.in/assets/images/maintainance.png" class="">
                    </div>
                    <div class="service-text text-white mt-2 ">Avail<br>Credit Card EMI</div>
                  </div>

                  <div class="col-md-3 col-6 col-sm-12 text-center pt-2 pb-3 mt-1 mb-1 animated pulse infinite service-block">
                    <div class="service-icons mb-2">
                      <img src="https://book.on-track.in/assets/images/assistance.png" class="" style="transform: rotate(90deg);">
                    </div>
                    <div class="service-text text-white mt-2 ">24/7 Road Side<br>Assistance</div>
                  </div>
                </div>

              </div>
            </div>
          </div>
        </section>


        <section class="white" >
          <div class="container col-md-8 m-auto px-3  pt-2  ">
            <div class="row pb-3">
              <div class="col-lg-12 ">
                <h4 class="head-text text-center mt-2 pt-2 pb-2 h11">About the Bike</h4>
              </div>
              <div class="dash blue"></div>
            </div>
            <div class="row pb-4">
              <div class="col-lg-6 col-md-6 col-sm-12 ">
                <p  style="line-height:25px; text-align:justify; font-family:gilroy">
                 {{vehicle.about_vehicle}}  <a :href="''+vehicle.manufacturer_url+''">Know More</a></p>
                    <a :href="''+vehicle.manufacturer_url+''"><img style="" class="image" :src="vehicle.brand_logo" width="5%" alt=""></a>
                
              </div>
              <div class="col-lg-6 col-md-6 col-sm-12 text-center" >
                <img :src="currentImage" class="img-fluid" style="width:320px">
              </div>
            </div>
          </div>
        </section>

        <!-- <section class=" " style="background-color:#3023AE; ">
          <div class="container  ">
            <div class="row order-footer">
              <div class="col-lg-3 col-md-3 col-sm-12 pt-2 text-center footer-1"><img src="https://book.on-track.in/assets/images/refer-footer.svg"
                  class="img-fluid img-mobi"></div>
              <div class="col-lg-7 col-md-6 col-sm-12 pt-3 footer-2 text-left ">
                <h5 class="white-text bold" style="color:white">Refer a Friend</h5>
                <p class="white-text" style="color:white">Click Here To Invite Your Friend To Book A Bike And Earn 250 Ontrack Points.</p>
              </div>
              <div class="col-lg-2 col-md-3 pt-3 text-center pb-2 footer-3">
                <button class="refer-btn animated bounceIn hoverable mt-3" routerLink="/referral">Refer Now</button>
              </div>
            </div>
          </div>
        </section> -->

  </div>
</template>

<script>
const axios = require("axios");
 
import * as _ from "lodash";
export default {
  data() {
    return {
      navs:['aa','bb','<a>cc</a>'], 
        selectionSelecotr:'sections', 
        showButton:false,
        scrollAnimate:true,
        scrollShow:false,
        disable:false,
        scrollDownHide:false,
        zIndex:1000,
        stickyTop:-1,
        threshold:0,
      vehicle: [],
      value: "",
      currentImage: "",
      color: "",
      currentSelected: [],
      currentPrice: 0,
      variant: "",
      loading: true,
      selectColor: [],
      colorCheck: "",
      variantsList: [],
      selectedColor: "",
      showDetailDealer:false,
      selectedaddons:[],
      make_model:'',
      mfg:'',
      name:'',
      number:'',
      submitted:false,
      books:'full'
    };
  },
  components:{

  },
  created() {
     window.addEventListener('scroll', this.handleScroll);
    window.scrollTo({
      top: 0,
      left: 0,
      behavior: "smooth",
    });

   
  
    axios
      .get(
        "https://backend-bikex.herokuapp.com/api/otr_models/model-data-with-dealer/" +
          this.$route.params.id
      )
      .then((result) => {
        this.vehicle = result.data;
        this.variantsList = _.uniqBy(this.vehicle.superset, "variant");
        this.currentImage = this.vehicle.hero_image;
        this.make_model = this.vehicle.make +' '+ this.vehicle.model
        this.currentSelected.push(this.vehicle.superset[0]);
        this.loading = false;
      })
      .catch((error) => {
        throw new Error(`API ${error}`);
      });
  },
  watch: {
    color() {
      this.setImage();
    },
    variantsList(){
      this.variant = this.variantsList[0].variant
      this.setVariant()
    },
    selectColor(){
      this.selectedColor = this.selectColor[0].hex_color
      this.chooseColor(this.selectColor[0].id,this.selectColor[0].hex_color)
    }
  },
  methods: {
    chooseColor(id, color) {
      this.color = id;
      this.selectedColor = color;
    },  
   
    popip() {
      var popup = document.getElementById("myPopup");
      popup.classList.toggle("show");
    },
    bookNow(){
      // let cartData=[{
      //   "addons":this.selectedaddons,
      //   "selectedItem": {"dealer":this.currentSelected[0].dealer,"color":this.currentSelected[0].color,
      //   "id":this.currentSelected[0].id,"variant":this.currentSelected[0].variant,"image":this.currentSelected[0].image,
      //   "price":this.currentSelected[0].price,"model":this.make_model
      //   },
      //   "_id":this.vehicle._id,
      //   "make_model":this.make_model
      // }]
      
      // localStorage.setItem("cart", JSON.stringify(cartData))
      // this.$router.push(
      //   "/cart/" + this.$route.params.id + "/" + this.currentSelected[0].id
      // );
      this.$router.push({ path: "/displaynext/" + this.$route.params.id })
    },
    submit(){
                    this.loading = true
                    this.$http.post('https://backend-bikex.herokuapp.com/api/otr_customer_interest',{
                        
                          name:this.name,
                          number:this.number

                        },
                        {
                        headers: { 'Authorization': 'YwMiRtYxQpVcMsVy1w3Z9==' }
                        }).
            then(response=>{
            this.submitted = true;
            this.response = response.body;
            
           
            }).catch(error => { 
                this.message = error.body.msg;
                this.loading= false
            })   
    },
    setImage() {
      this.currentSelected = this.vehicle.superset.filter((x) => {
        return x.id == this.color;
      });
      this.colorCheck = this.currentSelected[0].color;
      this.currentImage = this.currentSelected[0].image;
    },
    proceed() {
      let cartData=[{
        "addons":this.selectedaddons,
        "selectedItem": {"dealer":this.currentSelected[0].dealer,"color":this.currentSelected[0].color,
        "id":this.currentSelected[0].id,"variant":this.currentSelected[0].variant,"image":this.currentSelected[0].image,
        "price":this.currentSelected[0].price,"model":this.make_model
        },
        "_id":this.vehicle._id,
        "make_model":this.make_model
      }]
      
      localStorage.setItem("cart", JSON.stringify(cartData))
      if(this.books == 'full'){
        this.$router.push(
        "/cart/" + this.$route.params.id + "/" + this.currentSelected[0].id
      );
      }else{
        this.bookNow(this.books)
      }
    },
    setVariant() {
      this.colorCheck = "";
      this.selectColor = this.vehicle.superset.filter((x) => {
        return x.variant == this.variant;
      });
    },
  },
  computed: {
    totalPrice(){
      
        if(this.selectedaddons.length ==0){
          return this.currentSelected[0].price
        }else{
          var x = 0
          for(var i in this.selectedaddons){
            x+=Number(this.selectedaddons[i].price)
          }
          return Number(this.currentSelected[0].price) + Number(x)
        }
     
    }
    // variantList() {
    //   if (!this.variant) {
    //     return this.vehicle
    //   } else {
    //     return this.vehicle.filter(x=>{
    //         return x.id == this.variant
    //     })
    //   }
    // },
  },
};
</script>

<style scoped>
/* @font-face {
  font-family:rubik ;
  src: url(../assets/font/rubik/Rubik-VariableFont_wght.ttf);
}
@font-face {
  font-family:rubikw ;
  src: url(../assets/font/rubik/Rubik-VariableFont_wght.ttf);
  font-weight: 600;
}
@font-face {
 font-family:roboto ;
  src: url(../assets/font/roboto/Roboto-Black.ttf); 
} */
.fgh{
  font-family: gilroy !important;
}
@font-face {
  font-family: Gilroyf;
  src: url(../assets/font/Gilroy-ExtraBold.otf);
}
@font-face {
  font-family: Gilroy;
  src: url(../assets/font/Gilroy-Light.otf);
}
.dot {
  height: 25px;
  width: 25px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  cursor: pointer;
  border: 1px solid black;
}
.h11{
  font-family: gilroyf;
  font-family: 15px !important;
}
.dot:hover {
  transform: scale(1.2);
  transition: 0.5s;
}
/* .onHover:hover {
  transform: scale(1.1);
  transition: 1s;
} */
/* .classp{
  font-family: rubikw;
  margin-bottom:0
} */
.classa{
  font-family: gilroy;
  margin-bottom:0;
  color:#2A2A2A;
  font-weight: 300;
  font-size:12px
}
.refer-btn{background-color: #ccc; border-radius:25px; padding: 10px 25px;border:0; color: #3023AE; cursor: pointer; }
.dash{
    height: 3px;
    width: 50px;
    margin: 0 auto;
    background-color: #fff;
}
.box-container-fluid{
  background-image: url('https://book.on-track.in/our-services-bg.9250bdb03d84d5dc3594.svg') !important; background-size: cover
}
@media screen and (max-width: 600px) {
  .box-data img {
        width: 40%;
      
    }
    .box-data{
      text-align: center !important;
    }
    .ali{
      text-align: center !important;
    }
}

</style>