<template>
    <div class="col-md-12 m-0 p-0">
    <div class="col-md-12 my-5 m-0 p-0" style="font-family:gilroy ;">
      <div class="col-md-8 p-0 m-auto">
          <div class="col-md-12 m-0 p-0">
              <div class="col-md-12 m-0 p-0 row">
                    <div class="col-md-7 px-3 m-0 p-0">
                        <div class="col-md-12 border m-0 p-0 row" >
                                <div class="col-md-12 px-3 py-2 p-0 d-flex justify-content-between border-bottom">
                                    <h6 class="m-0 p-0 mt-2 fontbada">{{vehicle.make}} {{vehicle.model}}</h6>
                                    <h6 class="mb-0">
                                        <transition name="fade">
                                        <div class="col-md-12 m-0 p-0" v-if="variant">
                                            <!-- <p class="m-0 p-0">Select Color :</p> -->
                                            <span
                                            v-for="(data, index) in selectColor"
                                            :key="index"
                                            @click="chooseColor(data.id, data.hex_color)"
                                            v-bind:style="{ 'background-color': data.hex_color }"
                                            class="dot mr-2 mt-2"
                                            ></span>
                                        </div>
                                        </transition>
                                    </h6>
                                </div>
                                <div class="col-md-6 m-0 p-0" style="background:#F5F5FA">
                                        <img class="" width="100%" :src="currentImage" alt="" />
                                </div>
                                <div class="col-md-6 m-0 p-0 border-left" style="background:#F5F5FA"  >
                                    <div class="col-md-12  text-left bnc" style="margin-top:85px"> 
                                        <h3 class="mb-0 fontbada" style="font-size:13px">Buy For</h3>
                                        <h2 class="fontbada"><strong>₹ {{ currentSelected[0].price }}</strong></h2>
                                    </div>
                                </div>
                        </div>
                        <div class="col-lg-12 gray-block p-2 pt-3 pb-3 mt-3 d-none d-sm-none d-md-block border" style="background:#F5F5FA">
                            <div class="container">
                            <h4 class=" pt-2 pb-2 fontbada">You get more than just a bike! </h4>
                            <div class="row">
                                <div class="col-lg-6 col-md-6 col-sm-12 ticks pt-2">
                                <ul class="">
                                    <li>zero security deposit</li>
                                    <li>lucrative lock-in </li>
                                    <li>pick-up and delivery</li>
                                    <li>unlimited km</li>
                                </ul>
                                </div>
                                <div class="col-lg-6 col-md-6 col-sm-12 ticks pt-2">
                                <ul>
                                    <li>free maintenance</li>
                                    <li>insurance covered bikes</li>
                                    <li>helmet</li>
                                    <li>roadside assistance</li>
                                </ul>
                                </div>
                            </div>
                             
                            </div>
                        </div>
                    </div>
                    <div class="col-md-5 px-3 m-0 p-0">
                            <div class="col-md-12 margin-lap border p-0">
                                <div class="col-md-12 m-0 p-0">
                                    <!-- <div class="col-md-12 my-2 m-0 p-0 row">
                                        <div class="col-md-5 ">
                                            <div class="col-md-12 p-2 border">
                                                <p class="mb-0" style="font-size:13px">Standard</p>
                                            </div>
                                        </div>
                                        <div class="col-md-5 m-0 p-0">
                                            <div class="col-md-12 p-2 border">
                                                <p class="mb-0" style="font-size:13px">Deluxe</p>
                                            </div>
                                        </div>
                                    </div> -->
                                    <div class="col-md-6 mb-2">
                                      <p class="mb-1 mt-2 text-left fontbada">Select Variant</p>
                                      <select class="form-control mt-2 " v-model="variant" @change="setVariant()"  >
                                        <option :value="data.variant " v-for="(data, index) in variantsList" :key="index">
                                          {{ data.variant }}
                                        </option>
                                      </select>
                                    </div>
                                    <div class="col-md-12 col-12  text-left" v-if="currentSelected && variant && currentSelected[0].description  && colorCheck">
                                        <p style="font-size:12px">{{currentSelected[0].description}}</p>
                                    </div>
                                </div>
                                <div class="col-md-12 ml-3 m-0 p-0">
                                    <P class="mb-1 text-left fontbada" style="font-size:14px">ADD-ONS</P>
                                    <div class="col-md-12 my-2 m-0 p-0 row" v-for="(data, index) in currentSelected[0].add_ons" :key="index" >
                                        <div class="col-md-5 col-7 m-0 p-0" >
                                            <div class="col-md-12 col-12 text-left p-0 m-0 " >
                                                <input type="checkbox" class="m-0 p-0" v-if="data.status == 'active'" :value="data" v-model="selectedaddons" > <span style="font-size:13px"> {{data.name}} at ₹{{data.price}}</span>
                                            </div>
                                        </div>
                                        <div class="col-md-12 ml-0 pl-0 text-left">
                                          <p style="font-size:12px">{{data.description}}</p>
                                        </div>
                                    </div>
  
                                </div>
                                <div class="col-md-12 m-0 p-0">
                                    <P class="ml-3 text-left fontbada" style="font-size:14px">BUYING OPTIONS</P>
                                    <div class="col-md-12 my-2 m-0 p-0 row">
                                        <div class="col-md-5 ml-0 text-left col-6">
                                            <button :class="{'ifselected':books == 'Thanks for choosing Ontrack'}">
                                            <div class="col-md-12 p-2  text-left" @click="bnm('Thanks for choosing Ontrack')">
                                                <p class="mb-0 fontbada " style="font-size:13px">Pay Full</p>
                                                <p class="mb-0 " style="font-size:10px">Get home delivered</p>
                                                <!-- <p class="mb-0 " style="font-size:10px">Pay once & covers all the cost</p> -->
                                            </div>
                                            </button>
                                        </div>
                                        <div class="col-md-5 col-5 text-left p-0">
                                            <button :class="{'ifselected':books == 'Book bike at Rs. 1000'}">
                                            <div class="col-md-12 p-2  text-left" @click="bnm('Book bike at Rs. 1000')">
                                                <p class="mb-0 fontbada" style="font-size:13px">Book Now (₹ 1000)</p>
                                                <p class="mb-0 " style="font-size:10px">Get home delivered</p>
                                                <!-- <p class="mb-0 " style="font-size:10px">Pay once & covers all the cost</p> -->
                                            </div>
                                            </button>
                                        </div>
                                    </div>
                                </div>
                                <div class="col-md-6 row">
                      <!-- <div class="col-12">
                        <button @click="bnm('Thanks for choosing Ontrack')">payfull</button>
                         <button @click="bnm('Book bike at Rs. 1000')">pay 1000</button>
                      </div> -->
                    </div>
                                <div class="col-md-12 mt-4 p-2" style="background:#4e44d8">
                                    <button style="border:none; background:transparent;color:white" :disabled="!variant"  @click="proceed">Proceed</button>
                                </div>
                            </div>
                        <div class="col-md-12  mt-3 p-3 text-left margin-lap border" style="font-size:14px">
                          
                            <p class="mb-2 fontbada">Fulfilled By : </p>
                            <p class="mb-0">{{ currentSelected[0].dealer.name}}</p>
                            <p class=""><span Address:>{{ currentSelected[0].dealer.address }}, {{ currentSelected[0].dealer.city }} - {{ currentSelected[0].dealer.pincode }}</span>  </p>
                        </div>
                    </div>
                    
              </div>
          </div>
      </div>
  </div>





























  

    
    <div v-if="loading" class="mt-4 pt-5">
      <b-row>
        <b-col class="mb-4">
          <b-skeleton-img></b-skeleton-img>
        </b-col>
        <b-col class="pt-4 pl-3">
        <b-skeleton type="button"></b-skeleton>
        <b-skeleton class="mt-2" animation="wave" width="85%"></b-skeleton>
         <b-skeleton class="mt-2" type="input"></b-skeleton>
        </b-col>
        <b-col cols="12" class="mt-3">
          <b-skeleton-img no-aspect height="150px"></b-skeleton-img>
        </b-col>
      </b-row>

    </div>
  </div>




</template>
<script>
const axios = require("axios");
 
import * as _ from "lodash";
export default {
  data() {
    return {
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
      books:'Thanks for choosing Ontrack'
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
      .get("https://ontrack-backend-express-v1.herokuapp.com/api/otr_models/model-data-with-dealer/" +this.$route.params.id).then((result) => {
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
    checkIfSelected(data){
      var x = this.selectedaddons.filter(x=>{
        return x == data
      })
      if(x.length > 0){
      return true
      }else{
        return false
      }
    },
   
    popip() {
      var popup = document.getElementById("myPopup");
      popup.classList.toggle("show");
    },
    bnm(id){
        this.books = id
    },
    bookNow(uid){
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
    //   this.books = uid
      this.$router.push({ path: "/checkout/" + this.$route.params.id + "/" + this.currentSelected[0].id, query: { booking_type: uid }})
    },
    submit(){
                    this.loading = true
                    this.$http.post('https://ontrack-backend-express-v1.herokuapp.com/api/otr_customer_interest',{
                        
                          name:this.name,
                          number:this.number,
                          

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
        "/checkout/" + this.$route.params.id + "/" + this.currentSelected[0].id
      );
      }else{
        this.bookNow(this.books)
      }
    },
    startpurchase() {
      this.books = 'full'
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
        "/checkout/" + this.$route.params.id + "/" + this.currentSelected[0].id
      );
      }else{
        this.bookNow(this.books)
      }
    },
    reserve() {
      this.books = 'Book bike at Rs. 1000'
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
        "/checkout/" + this.$route.params.id + "/" + this.currentSelected[0].id
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
.ifselected{
  border: 1px solid #4E44D8;
  color:#4E44D8;
  background:#EDECFB;
}
.margin-lap{
    margin-left:15px
}
.fontbada{
    font-family:gilroyf !important
}
.select-btn .self-icon{
        background-image: url(../assets/self-icon.svg);
        background-repeat: no-repeat;
        padding: 17px;
        padding-left: 20px !important;
        background-position: 10px 10px;
    }
    .ticks ul{list-style: none; padding: 0; margin: 0}
.ticks li {
  background-image: url("../assets/tick.png");
  background-repeat: no-repeat;
  background-position: 0 0.6em;
  padding-left: 1.9em;
  text-transform: unset;
  line-height: 38px;
  text-transform: capitalize;
  color: #2a2a2a;
  font-size:15px;
  text-align: left;
}
.position-sticky{
  position: -webkit-sticky;
  position: sticky;
  top: 0;
  background-color: #fff;
  /* padding-top: 20px; */
  padding-top:10px;
  padding-bottom:10px;
  font-size: 10px !important;
  position: sticky !important;
    z-index: 999999;
    top: 0;
    
}
button{
   
    outline:none !important;
    border:1px solid #cccccc;
    background:transparent
}
.addonsCheckbox{
  padding:10px;
  position: absolute;
  right:0 !important;
  top:0;

}

.display-mobile{
  display: none;
}
/* Popup container */
.popup {
  position: relative;
  display: inline-block;
  cursor: pointer;
}

/* The actual popup (appears on top) */
.popup .popuptext {
  visibility: hidden;
  width: 170px;
  background-color: #555;
  color: #fff;
  text-align: left;
  border-radius: 6px;
  padding: 8px 0;
  position: absolute;
  z-index: 1;
  bottom: 125%;
  left: 50%;
  margin-left: -104px;
}

/* Popup arrow */
.popup .popuptext::after {
  content: "";
  position: absolute;
  top: 100%;
  left: 50%;
  margin-left: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: #555 transparent transparent transparent;
}

/* Toggle this class when clicking on the popup container (hide and show the popup) */
.popup .show {
  visibility: visible;
  -webkit-animation: fadeIn 1s;
  animation: fadeIn 1s
}

/* Add animation (fade in the popup) */
@-webkit-keyframes fadeIn {
  from {opacity: 0;}
  to {opacity: 1;}
}

@keyframes fadeIn {
  from {opacity: 0;}
  to {opacity:1 ;}
}
/* Style the header */
.header {
  padding: 10px 16px;
  background: #555;
  color: #f1f1f1;
}

/* Page content */
.content {
  padding: 16px;
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
@font-face {
  font-family: Gilroyf;
  src: url(../assets/font/Gilroy-ExtraBold.otf);
}
@font-face {
  font-family: Gilroy;
  src: url(../assets/font/Gilroy-Light.otf);
}
input:focus ~ .floating-label,
input:not(:focus):valid ~ .floating-label{
  top: -7px;
  padding: 0px 5px 0px 5px;
  background-color: #fefefe;
  left: 20px;
  font-size: 11px;
  opacity: 1;
  z-index: 1;
  outline: none !important;
  box-shadow: none !important
}
.form-control{
    /* border:none !important */
}
textarea:focus ~ .floating-label,
textarea:not(:focus):valid ~ .floating-label{
  top: -7px;
  padding: 0px 5px 0px 5px;
  background-color: #fefefe;
  left: 20px;
  font-size: 11px;
  opacity: 1;
  z-index: 1;
  outline: none !important;
  box-shadow: none !important
}
select:focus ~ .floating-label,
select:not(:focus):valid ~ .floating-label{
  top: -7px;
  padding: 0px 5px 0px 5px;
  background-color: #fefefe;
  left: 20px;
  font-size: 11px;
  opacity: 1;
  z-index: 1;
  outline: none !important;
  box-shadow: none !important
}

.inputText {
outline: none !important;
}
input:focus, textarea:focus, select:focus{
  outline: none !important;
  box-shadow: none !important
}
.floating-label {
  position: absolute;
  pointer-events: none;
  left: 30px;
  top: 8px;
  transition: 0.2s ease all;
  font-size:14px
}
.nav-tabs .nav-link.active{
    color: #495057;
    background-color: red !important;

}

.labels {
  color: gray;
    font-size: 15px;
    font-weight: normal;
    font-family: "Gilroy"
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

.display {
  min-height: 300px;
  transition: 2s;
  font-family: "Gilroy";
    font-size: 17px;
    font-weight: normal;
    font-family: "Gilroy"
}
.link{
  color: #4E44D8;
  cursor:pointer
}
.title{
    font-size: 17px;
    font-weight: normal;
    font-family: "Gilroy"
}
.heading-title{
    color: #2A2A2A;
    font-size: 20px;
    font-weight: bold;
    font-family: "Gilroyf"
}
.heading-title-sm{
    color: #2A2A2A;
    font-size: 15px;
    font-weight: bold;
    font-family: "Gilroyf"
}
.heading-title-md{
    color: #2A2A2A;
    font-size: 17px;
    font-weight: bold;
    font-family: "Gilroyf"
}
.nav-link .a{
    color: red !important;
}

.transit {
  transition: 2s;
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
.dot:hover {
  transform: scale(1.2);
  transition: 0.5s;
}
.onHover:hover {
  transform: scale(1.1);
  transition: 1s;
}
.mobile-margin-left{
  margin-left:10px
}

.dot:focus{
 background-color:yellow;    
}
@media only screen and (max-width: 600px) {
  .mobile-margin-right{
    margin:0  !important
  }
  .mobile-margin-left{
    margin:0  !important
  }
  .bnc{
    margin-top:25px !important
  }
  .margin-lap{
    margin-left:0px !important;
    margin-top:50px
}
.ssc{
  width: auto;
  height: 30px;
}
.display-mobile{
  display: block !important;
}
.aks{
  padding-left:35px
}
.pd2{
  padding-left:0 !important;
  
}
.image{
    width:25%;
  }
.pd1{
  padding-right:0 !important;
  padding-bottom:0 !important;
  /* padding-left: 2rem !important */
}
.pd3{
   padding-left: 1rem !important
}
.fontp{
  font-size: 8px  !important;
}
.fontp1{
  font-size: 13px  !important;
}
  
}
</style>
