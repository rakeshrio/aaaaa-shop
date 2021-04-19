<template>
    <div class="col-md-12 mt-5 p-0">
       <div class="col-md-12 m-0 p-0">
            <div class="col-md-4 mb-5 py-3  mt-5 " style="background-image: linear-gradient(240deg, #3322D3 0%, #A55BEC 100%); border-radius:0px 15px 15px 0px; color:white">
                <h3 class="pb-0 ml-4 pl-2 mb-0" style="font-size:36px;font-family: Gilroyf">New Two Wheeler Loans</h3>
                <p class="text-left pl-5" style="font-size:15px;font-family: Gilroy">Easy. Fast. Financed by those you trust.</p>
            </div>
            <div class="col-md-12 col-12 m-0 p-0" >
                    <div class="bg-img col-md-12 pt-3 col-12 m-0 p-0" >
                        <div class="col-10 m-auto ">
                        <div class="container col-12 m-0 p-3" style="    box-shadow: 0 3px 20px 0 rgba(0,0,0,.1); border-radius:25px;">
                            <div v-if="hasBeenSubmitted" style="top:50px !" >
                                <h3 class="mt-5"><strong>Thanks for filling this lovely form</strong></h3>
                                <h6 class="mt-5">Your request has been registered.</h6>
                                <h6>Our team will get in touch with you shortly.</h6>
                                <img class="mt-5" src="https://www.flaticon.com/svg/static/icons/svg/3587/3587986.svg" alt="" width="30%">
                            </div>
                            <div v-else  class="form row pt-3 px-3" >
                                <p><strong style="font-size:20px;font-family:gilroyf">" Sign Up to get " Low Rate of Interest Bike Loan”</strong></p>                               
                                <div class="col-md-12 m-0 p-0 text-center justify-center" >    
                                    <div class="col-md-12 m-0 p-0 text-center col-12 mb-4 " v-if="step == 1">
                                        <img src="../assets/multi4.png" alt="" width="70%" height="auto">
                                        <p class="text-center" style="font-size:20px; font-family:gilroyf; color:#4e44e8" >Step 1</p>
                                        <div class=" col-md-12 mb-4 text-left">  
                                            <label>Full Name</label>
                                            <input type="text" placeholder="Eg. Rahul Gupta" maxlength="50" @blur="$v.fullname.$touch" class="form-control" v-model.trim = "$v.fullname.$model"
                                            :class="{'is-invalid':$v.fullname.$error, 'is-valid':!$v.fullname.$invalid}" style="text-transform: capitalize;">
                                            <div class="valid-feedback">Your Name is valid!</div>
                                            <div class="invalid-feedback">
                                                <span v-if="!$v.fullname.required"> fullname is required</span>
                                                <span v-if="!$v.fullname.minLength"> fullname must have at least {{$v.fullname.$params.minLength.min}} letters</span>                
                                                <span v-if="!$v.fullname.maxLength"> fullname must have at most {{$v.fullname.$params.maxLength.max}} letters</span>
                                            </div>
                                        </div>
                                         
                                        <div class=" col-md-12 mb-4 text-left">
                                            <label>Date of Birth</label>
                                            <input list="hosting-plan2" type="date" class="form-control" placeholder=""  @blur="$v.dob.$touch"  v-model.trim = "$v.dob.$model"
                                            :class="{'is-invalid':$v.dob.$error, 'is-valid':!$v.dob.$invalid}" required>      
                                        </div>
                                        <div class="col-md-12 mb-4 text-left"> 
                                                <label >Gender</label>
                                                <select class="form-control smal" id="exampleFormControlSelect1 "  @blur="$v.gender.$touch" v-model.trim = "$v.gender.$model" :class="{'is-invalid':$v.gender.$error, 'is-valid':!$v.gender.$invalid}">
                                                    <option disabled value="">Select Gender</option>
                                                    <option value="Male">Male</option>
                                                    <option value="Female">Female</option>
                                                    <option value="Other">Other</option>      
                                                </select>
                                                <!-- <div class="valid-feedback">gender is Valid</div> -->
                                                <div class="invalid-feedback">
                                                    <span v-if="!$v.gender.required">Gender is required</span>
                                                </div>
                                        </div>
                                        <div class=" col-md-12 mb-4 text-left">  
                                            <label>Vehicle Name</label>
                                            <input type="text" placeholder="Honda Dio" maxlength="50" @blur="$v.know_two_wheeler.$touch" class="form-control" v-model.trim = "$v.know_two_wheeler.$model"
                                            :class="{'is-invalid':$v.know_two_wheeler.$error, 'is-valid':!$v.know_two_wheeler.$invalid}" style="text-transform: capitalize;">
                                            <div class="valid-feedback">Vehicle name is valid!</div>
                                            <div class="invalid-feedback">
                                                <span v-if="!$v.know_two_wheeler.required"> Vehicle name is required</span>
                                                <span v-if="!$v.know_two_wheeler.minLength"> vehicle name must have at least {{$v.know_two_wheeler.$params.minLength.min}} letters</span>                
                                                <span v-if="!$v.know_two_wheeler.maxLength"> vehicle name must have at most {{$v.know_two_wheeler.$params.maxLength.max}} letters</span>
                                            </div>
                                        </div>
                                        
                                        <p v-if="vbn" style="font-size:12px; color:red">{{vbn}}</p>
                                        <div class="col-md-12 col-12 row text-center" style="justify-content:center">
                                            <div class="col-md-4 col-6 m-auto">
                                                <button class="btun1" @click="next">Next</button>
                                            </div>   
                                        </div>
                                    </div>

                                    <div class="col-md-12 col-12 text-center justify-center m-0 p-0" v-if="step === 2">
                                        <img src="../assets/multi5.png" alt="" width="70%" height="auto">
                                        <p class="text-center" style="font-size:20px; font-family:gilroyf; color:#4e44e8" >Step 2</p>    
                                        <div class=" col-md-12 mb-4 text-left">
                                            <label>Mobile</label>
                                            <input placeholder="+91-9XXXXXXX9" type="number" @blur="$v.mobile.$touch" maxlength="10" oninput="javascript: if (this.value.length > this.maxLength) this.value = this.value.slice(0, this.maxLength);"  class="form-control required" v-model.trim = "$v.mobile.$model"
                                            :class="{'is-invalid':$v.mobile.$error, 'is-valid':!$v.mobile.$invalid}">
                                            <div class="valid-feedback">Mobile No is Valid</div>
                                            <div class="invalid-feedback">
                                                <span v-if="!$v.mobile.required">mobile no is required</span>
                                                <!-- <span v-if="!$v.mobile.numeric">mobile no is must number</span> -->
                                                <span v-if="!$v.mobile.minLength">mobile no must have  {{$v.mobile.$params.minLength.min}} letters</span>                
                                                <span v-if="!$v.mobile.maxLength">mobile no must not exceed {{$v.mobile.$params.maxLength.max}} letters</span>
                                            </div>
                                            <p class="mb-0 my-2" v-if="cvb" style="font-size:12px; color:red"> {{cvb}}</p> 
                                        </div>
                                        <div class="col-md-12 mb-4 text-left ">
                                            <label >City</label>   
                                            <select class="form-control smal" id="exampleFormControlSelect1"  @blur="$v.city.$touch" v-model.trim = "$v.city.$model" :class="{'is-invalid':$v.city.$error, 'is-valid':!$v.city.$invalid}">
                                                <option disabled value="">Select City</option>
                                                <option value="Bengaluru">Bengaluru</option>
                                                <option value="Hyderabad">Hyderbabad</option>
                                                <option value="Delhi">Delhi</option>      
                                            </select>
                                        </div>
                                        <div class=" col-md-12 mb-4 text-left" >
                                            <label>Pancard No</label>
                                            <input placeholder="BQXXXXXX79" type="text" @blur="$v.pancard_no.$touch" maxlength="10" oninput="javascript: if (this.value.length > this.maxLength) this.value = this.value.slice(0, this.maxLength);"  class="form-control required" v-model.trim = "$v.pancard_no.$model"
                                            :class="{'is-invalid':$v.pancard_no.$error, 'is-valid':!$v.pancard_no.$invalid}" style="text-transform:uppercase">
                                            <div class="valid-feedback">Pancard No is Valid</div>
                                            <div class="invalid-feedback">
                                                <span v-if="!$v.pancard_no.required">Pancard No is required</span>
                                                <span v-if="!$v.pancard_no.minLength">Pancard No must have  {{$v.pancard_no.$params.minLength.min}} letters</span>                
                                                <span v-if="!$v.pancard_no.maxLength">Pancard No must not exceed {{$v.pancard_no.$params.maxLength.max}} letters</span>
                                            </div>
                                        </div>
                                        <div class=" col-md-12 mb-4 text-left"  >
                                            <label>Aadhar Card No</label>
                                            <input placeholder="2XXX 3XXX 5XX6" type="number" @blur="$v.aadharcard_no.$touch" maxlength="12" oninput="javascript: if (this.value.length > this.maxLength) this.value = this.value.slice(0, this.maxLength);"  class="form-control required" v-model.trim = "$v.aadharcard_no.$model"
                                            :class="{'is-invalid':$v.aadharcard_no.$error, 'is-valid':!$v.aadharcard_no.$invalid}">
                                            <div class="valid-feedback">Aadhar Card is Valid</div>
                                            <div class="invalid-feedback">
                                                <span v-if="!$v.aadharcard_no.required">Aadhar Card No is required</span>
                                                <span v-if="!$v.aadharcard_no.minLength">Aadhar Card No must have  {{$v.aadharcard_no.$params.minLength.min}} letters</span>                
                                                <span v-if="!$v.aadharcard_no.maxLength">Aadhar Card No must not exceed {{$v.aadharcard_no.$params.maxLength.max}} letters</span>
                                            </div>
                                        </div>
                                        <!-- <div class=" col-md-12 mb-4 text-left" >
                                            <label>Aadhar card No</label>
                                            <input placeholder="XXXX XXXX XXXX" type="string" @blur="$v.aadharcard_no.$touch" maxlength="12" oninput="javascript: if (this.value.length > this.maxLength) this.value = this.value.slice(0, this.maxLength);"  class="form-control required" v-model.trim = "$v.aadharcard_no.$model"
                                            :class="{'is-invalid':$v.aadharcard_no.$error, 'is-valid':!$v.aadharcard_no.$invalid}">
                                            <div class="valid-feedback">Aadhar Card No is Valid</div>
                                            <div class="invalid-feedback">
                                                <span v-if="!$v.aadharcard_no.required">Aadhar Card No is required</span>

                                                <span v-if="!$v.aadharcard_no.minLength">Aadhar Card No must have  {{$v.aadharcard_no.$params.minLength.min}} letters</span>                
                                                <span v-if="!$v.aadharcard_no.maxLength">Aadhar Card No must not exceed {{$v.aadharcard_no.$params.maxLength.max}} letters</span>
                                            </div>
                                        </div> -->
                                        <!-- <div class=" col-md-12 mb-4 text-left" v-if="aadhar_card == 'yes' ">
                                            <label>Aadhar Card No</label>
                                            <input placeholder="2413 2653 2365" type="number" @blur="$v.aadharcard_no.$touch" maxlength="12" oninput="javascript: if (this.value.length > this.maxLength) this.value = this.value.slice(0, this.maxLength);"  class="form-control required" v-model.trim = "$v.aadharcard_no.$model"
                                            :class="{'is-invalid':$v.aadharcard_no.$error, 'is-valid':!$v.aadharcard_no.$invalid}">
                                            <div class="valid-feedback">Aadhar Card is Valid</div>
                                            <div class="invalid-feedback">
                                                <span v-if="!$v.aadharcard_no.required">Aadhar Card No is required</span>
                                                <span v-if="!$v.aadharcard_no.minLength">Aadhar Card No must have  {{$v.aadharcard_no.$params.minLength.min}} letters</span>                
                                                <span v-if="!$v.aadharcard_no.maxLength">Aadhar Card No must not exceed {{$v.aadharcard_no.$params.maxLength.max}} letters</span>
                                            </div>
                                        </div>
                                        <div class=" col-md-12 mb-4 text-left" v-if="aadhar_card == 'yes' ">
                                            <label>Aadhar card No</label>
                                            <input placeholder="XXXX XXXX XXXX" type="string" @blur="$v.aadharcard_no.$touch" maxlength="12" oninput="javascript: if (this.value.length > this.maxLength) this.value = this.value.slice(0, this.maxLength);"  class="form-control required" v-model.trim = "$v.aadharcard_no.$model"
                                            :class="{'is-invalid':$v.aadharcard_no.$error, 'is-valid':!$v.aadharcard_no.$invalid}">
                                            <div class="valid-feedback">Aadhar Card No is Valid</div>
                                            <div class="invalid-feedback">
                                                <span v-if="!$v.aadharcard_no.required">Aadhar Card No is required</span>

                                                <span v-if="!$v.aadharcard_no.minLength">Aadhar Card No must have  {{$v.aadharcard_no.$params.minLength.min}} letters</span>                
                                                <span v-if="!$v.aadharcard_no.maxLength">Aadhar Card No must not exceed {{$v.aadharcard_no.$params.maxLength.max}} letters</span>
                                            </div>
                                        </div> -->
                                        <!-- <div class="form col-12 m-0  px-4 row">
                                            <div class=" col-6 text-left pr-3 mt-3 m-0 p-0" >
                                                <p class=""><strong style="color:grey">Aadhar Card</strong></p>
                                                <div class="form-check-inline">
                                                    <label class="form-check-label">
                                                        <input type="radio" v-model="aadhar_card" value="yes" class="form-check-input" name="optradio1">Yes
                                                    </label>
                                                </div>
                                                <div class="form-check-inline">
                                                    <label class="form-check-label">
                                                        <input type="radio" v-model="aadhar_card" value="no" class="form-check-input" name="optradio1">No
                                                    </label>
                                                </div>
                                            </div>
                                            <div class="col-md-6 col-6 p-0 cvb mt-3 m-0" style="padding-left:20px">
                                                <p class=""><strong style="color:grey">PAN Card</strong></p>
                                                <div class="form-check-inline">
                                                    <label class="form-check-label">
                                                        <input type="radio" v-model="pancard" class="form-check-input1" value="yes" name="optradio"> Yes
                                                    </label>
                                                </div>
                                                <div class="form-check-inline">
                                                    <label class="form-check-label">
                                                        <input type="radio" v-model="pancard" class="form-check-input1" value="no" name="optradio" > No
                                                    </label>
                                                </div>
                                            </div>                                          
                                        </div> -->

                                          
                                         <p class="mb-0" style="font-size:12px; color:red"> {{response_message}}</p>
                                        <div class="col-md-12 text-center">
                                            <p class="text-center pb-0 mb-0 mt-3"  style="color:red" v-if="message">{{message}}</p>
                                        </div>
                                        <div class="col-md-12 col-12 mt-3  fgh  row text-center" style="justify-content:center; margin-top:0px">
                                            <div class="col-md-5 col-6">
                                                <button class="btun1" @click.prevent="step--">Previous</button>
                                            </div>
                                           
                                            <div class="col-md-4 col-6">
                                                <button class="btun2" @click="signup" >Next</button>
                                            </div>
                                        </div>  
                                    </div>

                                        <div id="myModal" class="modalss" v-if="otp_sent">
                                            <!-- modals content -->
                                            <div class="modalss-content text-left">
                                                <span class="close" v-on:click="otp_sent =! otp_sent">&times;</span>
                                                  <p class="mt-5 m-0 p-0" style="font-weight:700">OTP has been sent to {{mobile}}</p>
                                                <div class="col-md-12 mb-4 mt-5 p-0">
                                                            <input type="number" v-model="otp" class="inputText form-control" required />
                                                            <span class="floating-label" >Enter OTP and Verify</span>
                                                </div>
                                                <div class="col-md-12 text-center p-4">
                                                                <button class="action-button"  v-on:click="otpverify">
                                                                    <span v-if="!otp_load">Verify</span>
                                                                <div v-else class="spinner-border spinner-border-sm"></div>
                                                                </button>
                                                     <p style="color:red" class="mt-3">{{otp_message}}</p>
                                                </div>
                                            </div>
                                        </div>

                            </div>      
                        </div>
                        </div>
                    </div>
            </div>
            </div>
       </div>
        <div class="col-md-12 col-12 text-left m-0 p-0" style="border-top:15px solid red">
            <div class="col-md-9 col-10 py-5 m-auto">
                    <h3 class="mb-3" style="font-family:gilroyf">Features</h3>
                    <p  class="pb-0 " style="font-family:gilroy">Quick Loan Processing</p>
                    <p  class="pb-0 " style="font-family:gilroy">Minimum Documentation</p>
                    <p  class="pb-0 " style="font-family:gilroy">Low Rate of Interest</p>
                    <p style="font-family:gilroy">Multiple modes of Repayment - Direct Bank Debit, Online Booking, Payment Wallets & EMI by Cash.</p>
            </div>
        </div>
        <div class="col-md-12  col-12 text-left m-0 p-0 py-5" style="background:linear-gradient(240deg, #3322D3 0%, #A55BEC 100%); color:white">
            <div class="col-md-9 col-10 m-auto">
                    <h3 class="mb-3" style="font-family:gilroyf">Loan Eligibity Criteria</h3>
                    <p class="" style="font-family:gilroy">Salaried Professionals & Self-Employed over the age of 18 years and below 65 years by the end of the loan tenure.</p>
                    <p style="font-family:gilroy">Employment Stability of at least 3 months in case of Salaried Professionals; & 12 months in case of Self-Employed.</p>
                    
            </div>
        </div>
        
    </div>
</template>

<script>
// import axios from 'axios'
import { required, minLength, maxLength, numeric} from 'vuelidate/lib/validators'
export default {
    data(){
        return{
                step:1,
                fullname:'',
                year_of_purchase:'', 
                dob:'',
                gender:'',
                pancard:'yes',
                pancard_no:'',
                aadhar_card:'yes',
                know_two_wheeler:'',
                aadharcard_no:'',
                city:'',
                mobile:'',
                loading:false,
                response:'',
                message:'',
                success:false,
                source: '',
                isLoading: null,
                hasBeenSubmitted: false,
                isActive: true,
                sendingRequest:false,
                phone:'',
                response_message:null,
                otp_sent:false,
                otp:'',
                otp_message:'',
                otp_load:false,
                vbn:null,
                cvb:null,
                }
            },
            validations: {
                fullname:{
                    required,
                    minLength: minLength(3),
                    maxLength: maxLength(50)
                },
                know_two_wheeler:{
                    required,
                    minLength: minLength(3),
                    maxLength: maxLength(50)
                },
                mobile:{
                    numeric,
                     required,
                     minLength:minLength(10),
                     maxLength: maxLength(10)
                },
                pancard_no:{
                    
                     required,
                     minLength:minLength(10),
                     maxLength: maxLength(10)
                },
                aadharcard_no:{
                     numeric,
                     required,
                     minLength:minLength(12),
                     maxLength: maxLength(12)
                },
                gender:{
                    required
                },
                city:{
                    required
                },
                vehicle_name:{
                    required
                },
                dob: {
                    required
                }
        },
           created(){
            var fbclid = this.$route.query.fbclid
            var gclid = this.$route.query.gclid
            var dclid= this.$route.query.dclid
            var gclsrc= this.$route.query.gclsrc
            
       
            if(fbclid){
            this.source = "facebook"
            }else if(gclid){
            this.source = 'google'
            }
            else if(dclid){
            this.source = 'google'
            }
            else if(gclsrc){
            this.source = 'google'
            }
            else{
            this.source = "New-Two-Wheelers-Loan(Organic)"
            }
            },
            methods:{   
                next(){
                    if(this.error){
                                 this.vbn = 'Please provide all the fields.'

                    }else{
                        this.step++
                    }
                },     
                signup(){
                    if(this.error2){
                        this.cvb = 'Please provide all the fields.'
                    }else{ 
                    this.$http.post('https://ontrack-backend-express-v1.herokuapp.com/api/bike_loan/sendotp',{
                    mobile:this.mobile,
                    }).
                    then(response=>{
                        if(response.body.type == 'success'){
                            this.loading = false
                            this.otp_sent = true
                            window.console.log(response)
                        }else{
                            this.response_message = 'Phone Number Already Exist';
                        }
                        }).catch(error => { 
                            this.response_message = error.body.msg;
                            console.log(error.body.msg)
                        })  
                    }                
                },

                otpverify(){
                    this.otp_load = true
                    this.$http.post('https://ontrack-backend-express-v1.herokuapp.com/api/bike_loan/verifyotp',{
                    mobile:this.mobile,
                    otp:this.otp
                    }).
                    then(response=>{
                        this.otp_load = false
                        // this.loading = false
                        // this.otp_sent = true
                        if(response.body.msg == 'Otp verified'){
                                this.submit()
                        }else{
                            response.body.msg = 'OTP verification failed'
                        }
                        window.console.log(response.body)
                        
                    }).catch(error => { 
                        window.console.log(error.body)
                        this.response_message = error.body.msg;
                        this.otp_load= false
                    })  
                    
                },

                submit(){
                    this.loading = true
                    this.sendingRequest = true
                    // this.$gtag.event('conversion', {
                    //     'send_to': 'AW-837104235/NwQhCIGVrvEBEOvklI8D',
                    // })
                    this.isLoading = true,
                    this.$http.post('https://ontrack-backend-express-v1.herokuapp.com/api/bike_loan',{       
                        fullname:this.fullname,
                        dob:this.dob,
                        gender:this.gender,
                        // pancard:this.pancard,
                        // aadhar_card:this.aadhar_card,
                        know_two_wheeler:this.know_two_wheeler,
                        mobile:this.mobile,
                        city:this.city,
                        source:this.source,
                        pancard_no:this.pancard_no,
                        aadharcard_no:this.aadharcard_no,
                        },
                        {
                            headers: { 'Authorization': 'YwMiRtYxQpVcMsVy1w3Z9==' },
                        }).
                            then(response=>{
                            setTimeout(() => {
                            this.sendingRequest = false
                        }, 3000);
                            this.hasBeenSubmitted = true;
                            this.response = response.body;
                            setTimeout(() => {
                                    this.isLoading = false
                                }, 1000)
                            this.loading = false
                            this.success = true
                                this.$router.push(
                                {path:'/thankyou_newtwowheelers'
                                })
                            }).catch(error => { 
                                this.message = error.body.msg;
                                this.loading= false
                                setTimeout(() => {
                                this.sendingRequest = false
                            }, 3000);
                            })   
                        }  
                },
     computed:{
     error(){
         if(this.fullname ==""||this.dob==""||this.gender==""||this.vehicle_name==""){
             return true
         }else{
             return false
         }
     },
      error2(){
         if(this.mobile ==""||this.pancard==""||this.aadhar_card==""||this.city==""){
             return true
         }else{
             return false
         }
     },
       watchsendingrequest(){
      return this.sendingRequest
    },
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
label{
        font-weight: 600;
        /* text-transform:capitalize; */
        font-size:13px;
        font-family:gilroyf
  }
  .form-control{
        border-radius: none !important;
        box-shadow: rgb(85 85 85 / 19%) 2px 2px 12px;
        border:0.5px solid black
    
    }
  .smal{
    font-weight: 200 !important;
    text-transform: capitalize;
    font-size: 13px;
    color: gray;
  }
  .smala{
        font-weight: 600;
        text-transform:capitalize;
        font-size:13px;
        font-family:gilroyf
  }
    input[type=date]:required:invalid::-webkit-datetime-edit {
       color: grey;
       /* text-transform:uppercase; */
       font-size:13px;
       font-weight: 200 !important;
  
       
    }
    .action-button{
        border:none;
        background:#4e44d8;
        color:white
    }
    input{
        color: grey;
       /* text-transform:uppercase; */
       font-size:13px;
       font-weight: 200 !important;
    }
    @font-face {
    font-family: Gilroyf;
    src: url(../assets/font/Gilroy-ExtraBold.otf);
    }
    @font-face {
    font-family: Gilroy;
    src: url(../assets/font/Gilroy-Light.otf);
    }
    ::placeholder { /* Chrome, Firefox, Opera, Safari 10.1+ */
    color:grey !important ;
        text-transform:capitalize;
        font-size:13px;
    font-weight: 200 !important;
    }
    .form-control{
        border-radius: none !important;
        box-shadow: rgb(85 85 85 / 19%) 2px 2px 12px;
    
    }

.modalss {
  position: fixed; /* Stay in place */
  z-index: 1; /* Sit on top */
  padding-top: 100px; /* Location of the box */
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgb(0,0,0); /* Fallback color */
  background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
}

/* modalss Content */
.modalss-content {
  background-color: #fefefe;
  margin: auto;
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
}

/* The Close Button */
.close {
  color: #aaaaaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
}
.bg-img {

  background-image: url("http://1-dot-sparksgokulgroups.appspot.com/images/banner9.jpg");
  min-height: 801px;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}

/* Add styles to the form container */
.container {
  position: absolute;
  right: 0;
  margin: 20px;
  max-width: 400px;
  padding: 16px;
  background-color: white;
  /* top:-100px; */
  

}
.btun1 {

    height:30px;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 1px;
    padding: 0.2rem;
    border-radius: 15px;
    background:#4E44D8;
    text-align: center;
    display: block;
    width: 100%;
    text-transform: uppercase;
    border: none;
    color:white;
    outline: none;
    -webkit-box-shadow: 0 4px 8px 0 rgba(237,108,13,.5);
    box-shadow: 0 4px 8px 0 rgba(237,108,13,.5);
}
.btun2 {

    height:30px;
    padding: 0.2rem;
    border-radius: 12px;
    background:#ff6000;
    letter-spacing: 1px;
    font-weight: 700;
    text-align: center;
    display: block;
    width: 100%;
    text-transform: uppercase;
    border: none;
    color:white;
    outline: none;
    font-size: 12px;
    -webkit-box-shadow: 0 4px 8px 0 rgba(237,108,13,.5);
    box-shadow: 0 4px 8px 0 rgba(237,108,13,.5);
}
.rak:after {
    margin-top: 8px;
    content: "";
    width: 41px;
    height: 4px;
    background-image: linear-gradient(261deg,#f69b12,#ed6a10);
    display: block;
    border-radius: 2px;
}


._3qpfi {
    color: #fff;
    font-weight: 700;
   
    background-image: linear-gradient(261deg,#f69b12,#ed6a10);
    font-size: 16px;
    letter-spacing: .4px;
}


.xcv {
    width: 202px;
    position: relative;
    cursor: pointer;
}
.bnm {
    color: #fff;
    font-weight: 700;
    background-color: #ed6c0d;
     background-image: linear-gradient(261deg,#f69b12,#ed6a10);
    font-size: 16px;
    letter-spacing: .4px;
}
.newp{
    font-size: 16px!important;
    line-height: 24px!important;
    width: 100%!important;
        font-weight: 500;
            color: #465166;
}
.newp2{
    font-size: 12px!important;
    line-height: 24px!important;
    width: 100%!important;
        font-weight: 500;
            color: #465166;
}
.newp1{
    font-size: 22px!important;
    line-height: 24px!important;
    width: 100%!important;
        font-weight: 500;
            color: #465166;
}

._1aEHs>div {

    display: flex;
    height: 48px;
    line-height: 48px;
}
._3dm64 {
    border: 1px solid #dde5eb;
    border-radius: 5px;

    box-sizing: border-box;
}
._1aEHs>div>div {
    display: inline-block;
    padding: 0 10px;
}
._1aEHs p {
    font-size: 16px;
    font-weight: 400;
    color: rgba(70,81,102,.5);
}
._3D60D {
    margin-bottom: 10px;
    border-radius: 5px;
    -webkit-box-shadow: 0 5px 10px 0 rgba(0,0,0,.07);
    box-shadow: 0 5px 10px 0 rgba(0,0,0,.07);
    background-color: #fff;
    margin-top: 5px;
}
.ghj{
    position: relative;
    width: 100%;
    min-height: 1px;
    padding-right: 15px;
    padding-left: 15px;
}
.textp:after {
    margin-top: 8px;
    content: "";
    width: 41px;
    height: 4px;
    background-image: linear-gradient(264deg,#f69b00,#ed6a00);
    display: block;
    border-radius: 2px;
}
h1 {
    font-size: 20px;
    font-weight: 500;
    line-height: 30px;
    color: #465166;
    width: 144px;
    margin-top: 0;
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
    border:0.5px solid #f6f6f6
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
}

/* Set a style for the submit button */
.btn {
  background-color: #4CAF50;
  color: white;
  padding: 16px 20px;
  border: none;
  cursor: pointer;
  width: 100%;
  opacity: 0.9;
}

.btn:hover {
  opacity: 1;
}
@media screen and (max-width: 600px) {
    .bg-img{
        min-height: 800px !important;
        background-size:cover !important
        
    }
    .container{
        top:0 !important;
        max-width: 332px !important;
        /* height: 500px !important; */
    
    }
    .floating-label {

    font-size: 14px !important;
}
.fgh{
    margin-top:10px !important;
}
}
</style>