<template>
  <div class="col-md-12 m-0 p-0" style="font-family:gilroy">
    <div class="col-md-12  web m-0 p-0">
        <div class="col-md-12 navbar py-4 m-0 p-0">
            <div class="col-md-8  m-auto row justify-content-between">
                <div>
                    <img src="https://on-track.in/wp-content/uploads/2018/10/logo.svg" alt="">
                </div>
                <div class="d-flex">
                    <p class="mb-0 mt-1" :class="{'ifselected':step = 1}">Bag  </p>
                     <p class="mb-0 mt-1 px-3"> ----- </p>
                    <p class="mb-0 mt-1" :class="{'ifselected':step == 2}"> Address  </p>
                        <p class="mb-0 mt-1 px-3"> ----- </p>
                    <p class="mb-0 mt-1" :class="{'ifselected':step == 3}"> Payment </p>
                </div>
                <div>
                    <p class="mb-0"><span><img class="mr-2" src="../assets/shield.png" alt="" width="25px" height="100%"></span> 100% Secure</p>
                </div>
            </div>
        </div>
        <div class="col-md-12 m-0 p-0 py-1" style="background:#4e44d8; color:white; font-family:gilroyf; font-size:14px">
            As per govt guidelines, we are following all the protocols regarding sanitization
        </div>

        <div class="col-md-12 m-0 p-0" style="background:#F3F2FA">
            <div class="col-md-8 py-4 m-auto row p-0" >
                <div class="col-md-5 mt-2">
                    <div class="col-md-12 my-2   m-0 p-0" style="background:#FFF1EC">
                        <div class="col-md-12 p-0 p-2 m-0 row justify-content-between">
                            <div>
                                <h6 class="mb-0 " style="font-family:gilroyf; font-size:px">{{ cartdata[0].make_model }}</h6>
                            </div>
                            <div>
                                <p  class="mb-4" style="font-size:12px">{{cartdata[0].selectedItem.color}}, {{ cartdata[0].selectedItem.variant }} Variant</p>
                            </div>
                        </div>
                        <img :src="cartdata[0].selectedItem.image" alt="" width="70%">
                    </div>
                    <div class="col-12 m-0 py-1 p-0 mb-5" style="background:white">
                        <p class="ml-3 mb-2 mt-1 text-left" style="font-family:gilroyf">Order Summary</p>
                        <hr class="mx-3 p-0 m-0 my-2 mb-3">
                        <div class="col-md-12 row m-0 p-0 mt-3"  v-if="currentSelected[0].additional_cost.length>1">
                            
                            <div class="col-md-12 col-12 d-flex" style="justify-content:space-between"  v-for="(data, index) in currentSelected[0].additional_cost" :key="index">
                                <P class="mb-2" style="font-family:gilroy">{{ data.name }} </P>
                                <p class="mb-2" style="font-family:gilroy; font-size:13px">{{ data.price | currency }}</p>
                            </div>
                            <div class="col-md-12 col-12 d-flex" style="justify-content:space-between" v-for="(data, index) in cartdata[0].addons" :key="index">
                                <P class="mb-2" style="font-family:gilroy">{{ data.name }} </P>
                                <p class="mb-1" style="font-family:gilroy; font-size:13px">{{ data.description  }}</p>
                            </div>
                            <div class="col-md-12 mt-1 col-12 d-flex" style="justify-content:space-between;  color:">
                                <P class="mb-2" style="font-family:gilroy">Convenience Fee</P>
                                <p class="mb-1" style="font-family:gilroy">{{convenienceAmount | currency}}</p>
                            </div>  
                        </div>   
                        <hr class="mx-3 p-0 m-0 my-2 mb-3">
                        <div class="col-md-12  col-12 d-flex" style="justify-content:space-between;font-family:gilroyf"  >
                            <P class="mb-1" style="font-family:gilroyf">Your Total</P>
                            <p class="mb-1" style="font-family:gilroyf; font-size:13px">{{checkOutPrice | currency}}</p>
                        </div>   
                        <!-- <div class="col-md-12 mt-2 col-12" >
                                <p class="mb-1"><span class="badge badge-danger">{{booking_type.booking_type}}</span></p>
                                <p class="badge">Amount payable at store {{priceToPayAtStore | currency}} at the 	time of delivery</p>
                        </div> -->
                    </div>
                </div>
                <div class="col-md-7 p-0 mt-3">
                    <div class="col-md-12 m-0 py-2 p-0 " style="background:white">
                        <div class="col-md-12 mb-2 pl-4 m-0 row justify-content-between">
                            <div>
                                <P class="mb-0" style="font-family:gilroyf">Add Address</P>
                            </div>
                            <div>
                              <img class="mr-4" src="https://www.flaticon.com/svg/vstatic/svg/109/109618.svg?token=exp=1619174246~hmac=bf5ddd53dbb8a3a706e23f757a1af8b7" alt="" width="25px" height="auto">  
                            </div>
                        </div>
                        <hr class="m-0 p-0">
                            <div class="m-0 p-0 my-4" v-if="step==1 ">
                                <div class="form-row mx-3 my-3" >
                                    <div class="form__group mb-3 col-md-6 col-12">
                                        <input type="text" v-model="first_name" class="form__input" id="name" placeholder="First Name" required="" />
                                        
                                    </div>
                                    <div class="form__group mb-3 col-md-6 col-12">  
                                        <input type="text" v-model="last_name" class="form__input" id="inputPassword4" placeholder="Last name">
                                    </div>
                                    <div class="form__group  col-md-6 col-12">    
                                        <input type="number" v-model="phone_number" placeholder="Mobile" class="form__input" id="inputZip">    
                                    </div>
                                    <div class="form__group mb-3   col-md-6 col-12"> 
                                        <input type="email" v-model="email"  class="form__input" placeholder="Email Address" > 
                                    </div>
                                    <div class="col-md-4 ml-1 py-2" style="background:#4e44e8;color:white;border:none; border-radius:3px" >
                                        <button @click="step++"  style="background:#4e44e8;color:white;border:none; font-family:gilroyf">Continue</button>
                                    </div>         
                                </div>
                            </div>
                            <div class="m-0 p-0" v-if="step==2 ">
                                <div class="form-row my-3 mx-2" >
                                    <div class="form__group col-md-6 mb-3  col-12">    
                                        <input type="text" v-model="street_address"  class="form__input" placeholder="Street Address">
                                        
                                    </div>
                                    <div class="form__group col-md-6 mb-3  col-12">                                   
                                        <input type="text" v-model="city"  class="form__input" id="inputZip" placeholder="City/Town">
                                    </div>
                                    <div class="form__group  col-md-6 mb-3   col-12">
                                        <input type="text" v-model="state"  class="form__input" id="inputZip" placeholder="State">
                                    </div>
                                    <div class="form__group mb-5 col-md-6 mb-3  col-12">    
                                        <input type="number" v-model="post_code"  class="form__input" id="inputZip" placeholder="Pincode">
                                    </div>
                                    <div class="col-md-4 ml-1 py-2" style="background:#4e44e8;color:white;border:none; border-radius:3px" >
                                        <button @click="step++"  style="background:#4e44e8;color:white;border:none; font-family:gilroyf">Continue</button>
                                    </div>                   
                                </div>  
                            </div>
                            <div class="m-0 p-0" v-if="step==3">
                            <div class="form-row mx-3 my-3 " >
                                <div class="col-md-12 my-2">
                                    <label for="rto" class="labe" >
                                        <input type="checkbox" id="rto" v-model="rtoSameAsDelivery">
                                        RTO Address Same As Delivery Address
                                    </label>
                                </div>
                                <div class="form__group  col-md-6 mb-3   col-12">                                  
                                    <input type="text" v-model="rto_street_address"  class="form__input" id="inputZip" placeholder="Street Address">
                                </div>
                                <div class="form__group   col-md-6 mb-3  col-12">
                                    <input type="text" v-model="rto_city"  class="form__input" id="inputZip" placeholder="City/Town">
                                </div>
                                <div class="form__group   col-md-6 mb-3 col-12">
                                    <input type="text" v-model="rto_state"  class="form__input" id="inputZip" placeholder="State">
                                </div>
                                <div class="form__group  mb-5 col-md-6 mb-3  col-12">                                   
                                    <input type="number" v-model="rto_post_code"  class="form__input" id="inputZip" placeholder="Pincode">
                                </div> 
                                <div class="py-3 col-12 m-0 px-4 text-center " style="position:fixed !important; bottom:0; background:white; border:none; box-shadow: 0 -1px 4px 0 rgb(0 0 0 / 15%);  border-top: 1px solid #f6f6f6;">
                                  <div class="col-12 py-2" style="background:#FF3F6C;color:white;border:none; ">
                                    <button @click="placeOrder"  style="background:#FF3F6C;color:white;border:none">Place Order</button>
                                    </div>
                                </div>  
                            </div>
                                
                            </div> 
                    </div>
                </div>
            </div>
        </div>

        <div class="col-md-12 m-0 py-2 p-0" style="bottom:0 !important; background:#E6E6E6">
            <div class="col-md-8 m-auto row justify-content-between">
                <div>
                    <img src="../assets/visa.png" alt="">
                </div>
                <div > 
                    <p class="mb-0 mt-4" style="font-family:gilroy !important; font-size:14px;; cursor:pointer">Need Help ? Contact Us</p>
                </div>
            </div>
        </div>


    </div>


<!-- mobile -->

    <div class="mob col-12 m-0 p-0">
       <div class="col-md-12 col-12 m-0 pl-3 py-3 navbar p-0 text-left" style="box-shadow: 0 1px 2px 0 rgb(148 150 159 / 30%); ">
          <p class="mb-0" style="font-size:14px; font-family:gilroyf"><span><img class="mr-4" src="https://www.flaticon.com/svg/vstatic/svg/109/109618.svg?token=exp=1619174246~hmac=bf5ddd53dbb8a3a706e23f757a1af8b7" alt="" width="16px" height="auto"></span>CHECKOUT</p>
       </div>
        <div class="col-md-8  row col-12 m-0 p-0">
           <div class="col-md-12 m-0 p-0">
            <div class="col-12 m-0 p-2" style="background:#F8F2E2">
                <p class="text-left pl-2 mb-3" style="font-size:12px">ORDER SUMMARY</p>
                <div class="col-12 m-0 p-0 row">
                    <div class="col-4 m-0 p-0">
                        <img :src="cartdata[0].selectedItem.image" alt="" width="100%">
                    </div>
                    <div class="col-8 text-left pl-2 m-0 p-0">
                        <h6 class="mb-0 " style="font-family:gilroyf; font-size:px">{{ cartdata[0].make_model }}</h6>
                        <p  class="mb-4" style="font-size:12px">{{cartdata[0].selectedItem.color}}, {{ cartdata[0].selectedItem.variant }} Variant</p>
                        <p style="font-size:10px">Estimated Delivery, Thur 22 Apr 2021</p>
                    </div> 
            </div>
            <div class="row col-12 m-0 px-3 py-2" style="justify-content:space-between !important;font-size:12px; background:#f4f4f5">
                        <p class="mb-0 mt-1">Total amount to pay</p>
                        <p style="font-family:gilroyf; font-size:13px !important">{{checkOutPrice | currency}}</p>
            </div>
            <h6 class="text-left pl-3 mt-2 my-3" style="font-family:gilroyf">Price Details</h6>
            <hr class="mx-3 m-0 p-0">
            <div class="col-12 m-0 p-0  ">
                        <div class="col-md-12 row m-0 p-0 mt-3"  v-if="currentSelected[0].additional_cost.length>1">
                            <div class="col-md-12 col-12 d-flex" style="justify-content:space-between"  v-for="(data, index) in currentSelected[0].additional_cost" :key="index">
                                <P class="mb-2" style="font-family:gilroy">{{ data.name }} </P>
                                <p class="mb-2" style="font-family:gilroy; font-size:13px">{{ data.price | currency }}</p>
                            </div>
                            <div class="col-md-12 col-12 d-flex" style="justify-content:space-between" v-for="(data, index) in cartdata[0].addons" :key="index">
                                <P class="mb-2" style="font-family:gilroy">{{ data.name }} </P>
                                <p class="mb-1" style="font-family:gilroy; font-size:13px">{{ data.description  }}</p>
                            </div>
                            <div class="col-md-12 mt-1 col-12 d-flex" style="justify-content:space-between;  color:">
                                <P class="mb-2" style="font-family:gilroy">Convenience Fee</P>
                                <p class="mb-1" style="font-family:gilroy">{{convenienceAmount | currency}}</p>
                            </div>  
                        </div>   
                        <hr class="mx-3 p-0 m-0 my-2 mb-3">
                        <div class="col-md-12  col-12 d-flex" style="justify-content:space-between;font-family:gilroyf"  >
                            <P class="mb-1" style="font-family:gilroyf">Your Total</P>
                            <p class="mb-1" style="font-family:gilroyf; font-size:13px">{{checkOutPrice | currency}}</p>
                        </div>   
                        <!-- <div class="col-md-12 mt-2 col-12" >
                                <p class="mb-1"><span class="badge badge-danger">{{booking_type.booking_type}}</span></p>
                                <p class="badge">Amount payable at store {{priceToPayAtStore | currency}} at the 	time of delivery</p>
                        </div>    -->
            </div>
            </div> 
            <div class="col-12 m-0 p-0">
            <div class="col-12 py-2  d-flex" style="background:#F4F4F5; justify-content:space-between !important">
                <div>
                    <p>Add Address</p>
                </div>
                <div v-if="step==3 || step==2">
                    <p @click="step--"><img class="mr-4" src="https://www.flaticon.com/svg/vstatic/svg/109/109618.svg?token=exp=1619174246~hmac=bf5ddd53dbb8a3a706e23f757a1af8b7" alt="" width="16px" height="auto"></p>
                </div>            
            </div>          
                            <div class="m-0 p-0" v-if="step==1 ">
                                <div class="form-row mx-3 my-3" >
                                    <div class="form__group mb-3 col-md-6 col-12">
                                        <input type="text" v-model="first_name" class="form__input" id="name" placeholder="First Name" required="" />
                                        
                                    </div>
                                    <div class="form__group mb-3 col-md-6 col-12">  
                                        <input type="text" v-model="last_name" class="form__input" id="inputPassword4" placeholder="Last name">
                                    </div>
                                    <div class="form__group mb-3 col-md-6 col-12">    
                                        <input type="number" v-model="phone_number" placeholder="Mobile" class="form__input" id="inputZip">    
                                    </div>
                                    <div class="form__group mb-5   col-md-6 col-12"> 
                                        <input type="email" v-model="email"  class="form__input" placeholder="Email Address" > 
                                    </div>         
                                </div>
                                <div class="py-3 col-12 m-0 px-4 text-center " style="position:fixed !important; bottom:0; background:white; border:none; box-shadow: 0 -1px 4px 0 rgb(0 0 0 / 15%);  border-top: 1px solid #f6f6f6;">
                                  <div class="col-12 py-2" style="background:#4e44e8;color:white;border:none; " >
                                    <button @click="step++" :disabled="error"  style="background:#4e44e8;color:white;border:none">Continue</button>
                                    </div>
                                </div>  
                            </div>
                            <div class="m-0 p-0" v-if="step==2 ">
                            <div class="form-row my-3 mx-2" >
                                <div class="form__group col-md-6 mb-3  col-12">    
                                    <input type="text" v-model="street_address"  class="form__input" placeholder="Street Address">
                                    
                                </div>
                                <div class="form__group col-md-6 mb-3  col-12">                                   
                                    <input type="text" v-model="city"  class="form__input" id="inputZip" placeholder="City/Town">
                                </div>
                                <div class="form__group  col-md-6 mb-3   col-12">
                                    <input type="text" v-model="state"  class="form__input" id="inputZip" placeholder="State">
                                </div>
                                <div class="form__group mb-5 col-md-6 mb-3  col-12">    
                                    <input type="number" v-model="post_code"  class="form__input" id="inputZip" placeholder="Pincode">
                                </div>                  
                            </div>
                                <div class="py-3 col-12 m-0 px-4 text-center " style="position:fixed !important; bottom:0; background:white; border:none; box-shadow: 0 -1px 4px 0 rgb(0 0 0 / 15%);  border-top: 1px solid #f6f6f6;">
                                  <div class="col-12 py-2" style="background:#4e44e8;color:white;border:none; ">
                                    <button @click="step++" style="background:#4e44e8;color:white;border:none">Continue</button>
                                    </div>
                                </div> 
                            </div>
                            <div class="m-0 p-0" v-if="step==3">
                            <div class="form-row mx-3 my-3 " >
                                <div class="col-md-12 my-2">
                                    <label for="rto" class="labe" >
                                        <input type="checkbox" id="rto" v-model="rtoSameAsDelivery">
                                        RTO Address Same As Delivery Address
                                    </label>
                                </div>
                                <div class="form__group  col-md-6 mb-3   col-12">                                  
                                    <input type="text" v-model="rto_street_address"  class="form__input" id="inputZip" placeholder="Street Address">
                                </div>
                                <div class="form__group   col-md-6 mb-3  col-12">
                                    <input type="text" v-model="rto_city"  class="form__input" id="inputZip" placeholder="City/Town">
                                </div>
                                <div class="form__group   col-md-6 mb-3 col-12">
                                    <input type="text" v-model="rto_state"  class="form__input" id="inputZip" placeholder="State">
                                </div>
                                <div class="form__group  mb-5 col-md-6 mb-3  col-12">                                   
                                    <input type="number" v-model="rto_post_code"  class="form__input" id="inputZip" placeholder="Pincode">
                                </div> 
                            </div>
                                <div class="py-3 col-12 m-0 px-4 text-center " style="position:fixed !important; bottom:0; background:white; border:none; box-shadow: 0 -1px 4px 0 rgb(0 0 0 / 15%);  border-top: 1px solid #f6f6f6;">
                                  <div class="col-12 py-2" style="background:#FF3F6C;color:white;border:none; ">
                                    <button @click="placeOrder" :disabled="!error" style="background:#FF3F6C;color:white;border:none">Place Order</button>
                                    </div>
                                </div>  
                            </div>                
            </div>
            </div>
        </div>
      </div>
  </div>
</template>

<script>
const axios = require('axios');

export default {
    data(){
        return{
            superset:'',
            superdata:[],
            first_name:'',
            last_name:'',
            phone_number:'',
            email:'',
            otr_order_id:'',
            razorpay_order_id:'',
            street_address:'',
            post_code:'',
            city:'',
            state:'',
            rto_street_address:'',
            rto_post_code:'',
            rto_city:'',
            rto_state:'',
            rtoSameAsDelivery :false,
            message:'',
            booking_type:[],
            step:1,
            currentSelected: [],
        }
    },
 

    methods: {
        next(){
            this.step++
        },
        prev(){
           this.step-- 
        },
        rtoSameAsDeliveryTrigger(){
            if(this.rtoSameAsDelivery){
                this.rto_street_address = this.street_address,
                this.rto_post_code = this.post_code,
                this.rto_city = this.city,
                this.rto_state =this.state

            }else{
                this.rto_street_address = '',
                this.rto_post_code = '',
                this.rto_city = '',
                this.rto_state = ''
            }
        },
        
        goto() {
            this.$router.push('/checkout')
        },
        updatedatabase(res){
            window.console.log(res)
            
            axios.put('https://ontrack-backend-express-v1.herokuapp.com/api/otr_purchase/confirmOrder/'+ this.otr_order_id , {
                razorpay_order_id: this.razorpay_order_id,
                razorpay_payment_id: res.razorpay_payment_id,
                payment_status:1,
                booking_status:1,
                comment:'No comment Yet'
            },
                        {
                        headers: { 'Authorization': 'YwMiRtYxQpVcMsVy1w3Z9==' }
                        }).
            then(()=> {
                this.$router.push('/success/' + this.otr_order_id)
            })
            .catch(x=>{
                window.console.log(x.response.data.msg)
                this.$bvToast.toast(`Some error Occured.`, {
                    title: 'Error',
                    autoHideDelay: 5000,
                })
            })
        },
        placeOrder(){
            axios.post('https://ontrack-backend-express-v1.herokuapp.com/api/otr_purchase/generateOrder' , {
                firstname: this.first_name,
                lastname: this.last_name,
                phone:this.phone_number,
                email:this.email,
                payment_status:0,
                booking_status:0,
                del_address:this.street_address,
                del_postalCode:this.post_code,
                del_city:this.city,
                del_state:this.state,
                rto_address:this.rto_street_address,
                rto_postalCode:this.rto_post_code,
                rto_city:this.rto_city,
                rto_state:this.rto_state,
                model_id: this.cartdata[0]._id,
                superset_data: this.cartdata[0].selectedItem,
                add_ons:this.cartdata[0].addons,
                vehicle_details: this.cartdata[0].selectedItem,
                amount: this.checkOutPrice
            },
            {
             headers: { 'Authorization': 'YwMiRtYxQpVcMsVy1w3Z9==' }
            }).
            then(response=> {
                window.console.log(response.data)
                this.otr_order_id = response.data._id
                this.makepayment(response.data._id)
                window.console.log('1st')
            })
            .catch(x=>{
                window.console.log(x.response)
                this.$bvToast.toast(x.response, {
                    title: 'Error',
                    autoHideDelay: 5000,
                })
            })  
            //   .catch(error => { 
            //     this.message = error;
            //     this.loading= false
            // }) 
        },
       makepayment(id){
            this.loading=true
            window.console.log('2nd')
            var options = {
                            "key": "rzp_live_kNjIpPzSMA4gHS", // rzp_live_Vi238TQEagSN3x Enter the Key ID generated from the Dashboard
                            // "key":"rzp_live_Vi238TQEagSN3x",
                            "amount": this.checkOutPrice * 100, // Amount is in currency subunits. Default currency is INR. Hence, 50000 refers to 50000 paise or INR 500.
                            "currency": "INR",
                            "name": this.cartdata[0].make_model ,
                            "email":this.email,
                            "phone":this.phone_number,
                            "order_id":id,
                            "description": "Purchase " + this.cartdata[0].make_model,
                            "payment_capture":1,    
                            "handler": ((res)=>{
                                 this.updatedatabase(res)
                            }),
                            "notes": {
                                "address": "note value",
                                "vehicle_id":this.cartdata[0]._id,
                                "superset_id": this.cartdata[0].selectedItem.id
                            },
                            "theme": { 
                                "color": "#ffb52f"
                            }
                        };
                        this.$http.post('https://ontrack-backend-express-v1.herokuapp.com/api/rzp/createOrder',{
                            "amount":this.checkOutPrice * 100,
                            "currency":"INR",
                            "payment_capture":1
                        },
                        {
                        headers: { 'Authorization': 'YwMiRtYxQpVcMsVy1w3Z9==' }
                        }).then((res)=>{
                            window.console.log(res)
                            this.razorpay_order_id = res.id
                            var rzp1 = new window.Razorpay({...options,order_id:res.order_id}); 
                            rzp1.open()
                            }).catch((err)=>{
                                window.console.log(err)
                            })
        },
        fetchDetail(){
            this.$store.dispatch('getModelsWithoutDealer',{"id":this.$route.params.id})
        }
    },
created(){
    this.fetchDetail()
    this.superset = this.$route.params.value
    if(this.$route.query){
    this.booking_type = this.$route.query
    }
     
    axios
      .get(
        "https://ontrack-backend-express-v1.herokuapp.com/api/otr_models/model-data-with-dealer/" +
          this.$route.params.id
        )
      .then((result) => {
        this.vehicle = result.data;
        // this.variantsList = _.uniqBy(this.vehicle.superset, "variant");
        this.currentImage = this.vehicle.hero_image;
        this.currentSelected.push(this.vehicle.superset[0]);
        this.loading = false;
      })
      .catch((error) => {
        throw new Error(`API ${error}`);
      });

     window.scrollTo({
      top: 0,
      left: 0,
      behavior: "smooth",
    });
},
watch:{
    cartdata(){
       this.superdata = 
        this.cartdata.superset.filter(x=>{
        return x.id == this.superset

        })
    },
     rtoSameAsDelivery(){
            this.rtoSameAsDeliveryTrigger()
        }
},
computed:{
    // cartdata(){
    //     return this.$store.state.getModelsWithoutDealer
    // },
    totalPrice(){
        var addonsPrice = 0
        if(this.cartdata[0].addons.length > 0){
            for(var i in this.cartdata[0].addons){
                addonsPrice = addonsPrice + Number(this.cartdata[0].addons[i].price)
            }
        }
        return Number(this.cartdata[0].selectedItem.price) + Number(addonsPrice)
    },
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
    convenienceAmount(){
        if(this.booking_type.booking_type == 'Book bike at Rs. 1000'){
        return 0
      }
      else if(this.booking_type.booking_type == 'book bike at rupees Rs. 20000'){
        return 0
      }
      else if(this.booking_type.booking_type == 'book bike at rupees Rs. 30000'){
        return 0
      }else{
        return  Math.round(0.03*this.totalPrice)
      }
       
    },
    checkOutPrice(){
        if(this.booking_type.booking_type == 'Book bike at Rs. 1000'){
        return Number(1000)
      }
      else if(this.booking_type.booking_type == 'book bike at rupees Rs. 20000'){
        return Number(20000)
      }
      else if(this.booking_type.booking_type == 'book bike at rupees Rs. 30000'){
        return Number(30000)
      }else{
        return Number(this.totalPrice) + Number(this.convenienceAmount)
      }
       
    },
    error(){
        if(this.first_name == "" && this.last_name=="" && this.phone_number=="" && this.email==""){
            return true
        }else{
            return false
        }
    },
    cartdata() {
      return JSON.parse(localStorage.getItem('cart'))
    },
}

}
</script>


<style scoped>
.ifselected{
    color: #20BD99;
    border-bottom: 2px solid #20BD99;
    font-family:gilroyf
}
.widt{
    width:4%
}
.cvbb{
    margin-left:50px
}
.web{
    display: block !important;
}
.mob{
    display: none !important;
}
.dot {
  height: 25px;
  width: 20px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  cursor: pointer;
  border: 1px solid black;
}
:disabled {
  background: #dddddd;
}
.form__label {
  font-family: 'Roboto', sans-serif;
  font-size: 12px;
  margin-left: 2rem;
  margin-top: 0.7rem;
  display: block;
  transition: all 0.3s;
  transform: translateY(0rem);
}

.form__input {
  width: 100%;
    font-size: 14px;
    padding: 12px;
    border: 1px solid #d4d5d9;
    background-color: transparent;
    font-weight: 300;
    border-radius: 4px;
    line-height: 14px;

}

.form__input:placeholder-shown + .form__label {
  opacity: 0;
  visibility: hidden;
  -webkit-transform: translateY(-4rem);
  transform: translateY(-4rem);
  font-size: 8px;
}
a{
    color:#4E44D8 !important
}
.button:disabled{
    opacity: 0.2 !important;
}
 @font-face {
  font-family: Gilroy;
  src: url(../assets/font/Gilroy-Light.otf);
 }
@font-face {
  font-family: Gilroyf;
  src: url(../assets/font/Gilroy-ExtraBold.otf);
}
.font2{
    font-size: 18px;
    font-weight: bold;
    font-family: Gilroyf;
    color: #484848;
  }
  p{
      margin:0;
      padding: 0;
  }
@media all and (max-width:600px){
 .ghj{
     text-align:center !important
 }
 .web{
    display: none !important;
}
.mob{
    display: block !important;
}
 .cvbb{
    margin-left:10px !important
}
.labe{
    font-size:12px;
    color:grey
}
 .vbnm{
     padding-top: 25px;
 }
 .bnm{
     font-size:14px
 }
 .font3{
         font-size: 14px;
    color: black;
    font-weight: 500;
 }
 .cvb{
     padding-left: 0  !important;
 }
 .widt{
    width:15%
}
}
</style>