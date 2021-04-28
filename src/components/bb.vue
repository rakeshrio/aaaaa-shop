<template>
<div class="col-md-12 mb-0 pb-0 top">
    <div class="col-md-4 mb-5 py-3  " style="background-image: linear-gradient(240deg, #3322D3 0%, #A55BEC 100%); border-radius:0px 15px 15px 0px; color:white">
        <h3 class="pb-0 ml-4 pl-2 mb-0" style="font-size:36px;font-family: Gilroyf">New Two Wheeler Loans</h3>
        <p class="text-left pl-5" style="font-size:15px;font-family: Gilroy">Easy. Fast. Financed by those you trust.</p>
    </div>
    <div class="card m-3 mt-4" style="box-shadow: 0 5px 10px 0 rgba(0,0,0,.07);">
        <div v-if="hasBeenSubmitted" style="top:50px " >
            <h3 class="mt-5"><strong>Thanks for filling this lovely form</strong></h3>
            <h6 class="mt-5">Your request has been registered.</h6>
            <h6>Our team will get in touch with you shortly.</h6>
            <img class="mt-5" src="https://www.flaticon.com/svg/static/icons/svg/3587/3587986.svg" alt="" width="30%">
        </div>  
        <div v-else class="col-md-12 col-12  pl-4 pr-4 pt-4 pb-0">
            <p class="newp " style="font-family:gilroyf">Sign Up to get " Low Rate of Interest "</p>
            <p class="text-center pb-1"  style="color:red" v-if="message">{{message}}</p>
            <div class="form row pt-3">
                <div class="col-md-3  text-center col-12 mb-4 " >
                    <div class="col-12 text-center " style="box-shadow: 2px 2px 12px #55555530;">
                        <input list="hosting-plan4" type="text" class="form-control" style="text-transform:capitalize" maxLength="30" oninput="javascript: if (this.value.length > this.maxLength) this.value = this.value.slice(0, this.maxLength);" v-model="fullname" required>  
                        <span class="floating-label">Name</span>
                    </div>
                </div>
                <!-- <div class="col-md-3 col-12 mb-4">
                    <div class="col-12 text-center " style="box-shadow: 2px 2px 12px #55555530;">
                        <input list="hosting-plan5" type="text" class="form-control" v-model="dob" required>
                        <span class="floating-label">Date Of Birth</span>
                    </div>
                </div> -->
                <div class="col-md-3 col-12 mb-4">
                    <div class="col-12 text-center " style="box-shadow: 2px 2px 12px #55555530;">
                        <input  type="number" class="form-control"  maxLength="10" oninput="javascript: if (this.value.length > this.maxLength) this.value = this.value.slice(0, this.maxLength);" v-model="mobile" required>
                        <span class="floating-label">Mobile Number</span>
                    </div>  
                </div>
                <!-- <div class="col-md-3 col-12 mb-4">
                    <div class="col-12 text-center " style="box-shadow: 2px 2px 12px #55555530;">   
                            <input list="hosting-plan10" type="text" class="form-control" v-model="gender" required>
                            <span class="floating-label">Gender</span>
                    </div>
                </div> -->
            </div>
            <div class="row form">
                <div class="col-md-4 col-12 mb-4">
                    <div class="col-12 text-center " style="box-shadow: 2px 2px 12px #55555530;">   
                        <input list="hosting-plan8" type="text" class="form-control" style="text-transform:capitalize" maxLength="25" oninput="javascript: if (this.value.length > this.maxLength) this.value = this.value.slice(0, this.maxLength);" v-model="know_two_wheeler" required>
                        <span class="floating-label">Which 2 wheeler you looking for?</span>
                    </div>
                </div>
                
                <div class="col-md-4 col-12 mb-4">  
                    <div class="col-12 text-center " style="box-shadow: 2px 2px 12px #55555530;">                
                        <input list="hosting-plan2" type="text" class="form-control" v-model="city" required>
                            <datalist id="hosting-plan2">
                                <option value="Bengaluru"></option>
                                <option value="Hyderabad"></option> 
                                <option value="Chennai"></option>
                                <option value="Kochi"></option>
                                <option value="Thiruvanthapuram"></option>  
                            </datalist>
                        <span class="floating-label">Type City</span>
                    </div>
                    <div class="text-center ml-5">
                        <div class="col-12 text-center xcv mt-5"  v-if="!success">
                            <button  type="button" class="btn  _2iiQB _3qpfi text-center" @click="submit" :disabled="error"> Apply Now </button>
                            <span v-if="loading" class="spinner-border spinner-border-sm"></span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="col-12 m-0 p-0 bg" >
        <div class="col-12 pl-4 mt-5">
            <p class="newp1 text-left rak mb-5">Features<span style="color:#fba500"></span></p>
        </div>
        <div class="col-12 m-0 p-0">  
            <div class="col-12 row m-0 p-0">
                <div class="col-6 mb-4 text-center m-0 p-0">
                    <img src="https://bikex.in/img/clock.a522f251.svg" alt="" width="30%" height="auto">
                    <p class="newp2">Quick Loan Processing</p>
                </div>
                <div class="col-6 mb-4 text-center m-0 p-0">
                    <img src="https://bikex.in/img/saveb.566c4c4f.svg" alt="" width="30%" height="auto">
                    <p class="newp2">Low Rate of Interest</p>
                </div>
                <div class="col-6  mb-4 text-center m-0 p-0">
                    <img src="../assets/document.png" alt="" width="30%" height="auto">
                    <p class="newp2">Minimum Documentation</p>
                </div>
                <div class="col-6 mb-4 text-center m-0 p-0">
                    <img src="../assets/debitcard.png" alt="" width="30%" height="auto">
                    <p class="newp2 ">Multiple Payment Modes</p>
                </div>
            </div>
        </div>
    </div>
    <div class="col-12 m-0 p-0 bg1" style="color:white; " >
        <div class="col-12 pl-4 pt-5">
            <p class="newp11 text-left rak mb-5">How it works?</p>
        </div>
        <div class="col-12 m-0 p-0">
           <div class="col-12 row m-0 p-0 ">
                <div class="col-4 text-center m-0 p-0">
                  <img src="../assets/cf.png" class="icon" alt="" width="30%" height="auto">  
                </div> 
                <div class="col-8 text-left  ml-0 pl-0">
                    <p class="newp11">Begins With Form</p>
                    <p class="newp22">Just provide basic details about your vehicle in the above form and then our team will follow up.</p>
                </div>    
            </div>
            <hr class="mx-5">
            <div class="col-12 row m-0 p-0 mt-4 ">
                <div class="col-4 text-center m-0 p-0">
                  <img src="../assets/incall.png" class="icon" alt="" width="30%" height="auto">  
                </div> 
                <div class="col-8  text-left ml-0 pl-0">
                    <p class="newp11">In Call Verification</p>
                    <p class="newp22">Our expert team call and verify regarding your application.</p>
                </div>    
            </div> 
            <hr class="mx-5">
            <div class="col-12 row m-0 p-0 mt-4 ">
                <div class="col-4 text-center m-0 p-0">
                  <img src="../assets/bikestep.png" class="icon" alt="" width="30%" height="auto">  
                </div> 
                <div class="col-8 text-left ml-0 pl-0">
                    <p class="newp11">Bike At Your Step</p>
                    <p class="newp22">Once we come to a decision on the price. Buying has never been easier !</p>
                </div>    
            </div> 
        </div>
    </div>
        <div class="col-12 m-0 p-0 ">
            <div class="col-12 pl-4 mt-5">
                <p class="newp1 text-left rak mb-5">Loan Eligibility Criteria</p>
                <img src="https://cashkumarcdn-etyacoltechnolog.netdna-ssl.com/img/frontend/backgrounds/personal-loan/personal-loan-tips.svg" alt="" width="80%" height="auto">
                <div class="col-12 d-flex m-0 mt-5 p-0">
                    <p ><i class="fa fa-check" style="font-size:15px;color:green"></i></p>
                    <p class="text-left newp2 pl-2">Salaried Professionals & Self-Employed over the age of 18 years and below 65 years by the end of the loan tenure.</p>
                </div>
                <div class="col-12 d-flex m-0 p-0">
                    <p ><i class="fa fa-check" style="font-size:15px;color:green"></i></p>
                    <p class=" text-left pl-2 newp2" >Employment Stability of at least 3 months in case of Salaried Professionals & 12 months in case of Self-Employed.</p>
                </div>
            </div>
        </div>     
      
</div>
</template>

<script>
// import axios from 'axios'

export default {
    data(){
        return{
            step:1,
                fullname:'',
                year_of_purchase:'', 
                dob:'123',
                gender:'def',
                pancard:'yes',
                pancard_no:'',
                aadhar_card:'yes',
                know_two_wheeler:'',
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
                submit(){
                 
                    this.loading = true
                    this.sendingRequest = true
                    this.$gtag.event('conversion', {
                        'send_to': 'AW-837104235/NwQhCIGVrvEBEOvklI8D',
                    })
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
                        // pancard_no:this.pancard_no
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
                // setTimeout(() => {
                //         this.isLoading = false
                //     }, 1000)
                this.loading = false

                
                // this.$swal({
                // title:'Your request has been registered.',
                // text:'Our team will get in touch with you shortly.'
                // })
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
         if(this.fullname ==""&&this.mobile==""&&this.know_two_wheeler==""&&this.fullname==""){
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
.xcv button {
    width: 100%;
    
}
@font-face {
  font-family: Gilroy;
  src: url(../assets/font/Gilroy-Light.otf);
}
@font-face {
  font-family: Gilroyf;
  src: url(../assets/font/Gilroy-ExtraBold.otf);
}
.bg{
    background: #fff url(https://cdn.bimbimbikes.com/images/icons/skyline.svg) repeat-x bottom center;
    background-size: 1000px;
}
/* s */
.rak:after {
    margin-top: 8px;
    content: "";
    width: 41px;
    height: 4px;
    background-image: linear-gradient(
240deg
, #3322D3 0%, #A55BEC 100%);
    display: block;
    border-radius: 2px;
}


._3qpfi {
    color: #fff;
    font-weight: 700;
  background-image: linear-gradient(
240deg
, #3322D3 0%, #A55BEC 100%);
    
    font-size: 16px;
    letter-spacing: .4px;
}

._2iiQB {
    position: relative;
    height: 48px;
    padding: 0 .75rem;
    /* border-radius: 5px; */
    text-align: center;
    display: block;
    width: 100%;
    text-transform: uppercase;
    border: none;
    outline: none;
    -webkit-box-shadow: 0 4px 8px 0 rgba(237,108,13,.5);
    box-shadow: 0 4px 8px 0 rgba(237,108,13,.5);
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
.newp22{
    font-size: 12px!important;
    line-height: 24px!important;
    width: 100%!important;
        font-weight: 500;
            color: black;
}
.newp11{
    font-size: 22px!important;
    line-height: 24px!important;
    width: 100%!important;
        font-weight: 500;
            color: black;
}
._2iiQB {
    position: relative;
    height: 48px;
    padding: 0 .75rem;
    /* border-radius: 5px; */
    text-align: center;
    display: block;
    width: 100%;
    text-transform: uppercase;
    border: none;
    outline: none;
    -webkit-box-shadow: 0 4px 8px 0 rgba(237,108,13,.5);
    box-shadow: 0 4px 8px 0 rgba(237,108,13,.5);
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
    border:none !important
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
  box-shadow: none !important;
  color:grey
}
input{
    font-family:gilroy;
    font-size: 15px;
}
.floating-label {
  position: absolute;
  pointer-events: none;
  left: 30px;
  top: 8px;
  transition: 0.2s ease all;
  font-family:gilroy
}
.top {
    padding: 36px 0 48px;
    background: #fff url('https://www.cars24.com/js/06e98e5be5add15ebe97e86aaf7fe008.svg');
    background-image: url('https://www.cars24.com/js/06e98e5be5add15ebe97e86aaf7fe008.svg');
    background-position-x: center;
    background-position-y: top;
    background-size: 100% auto;
    background-repeat-x: no-repeat;
    background-repeat-y: no-repeat;
    background-attachment: initial;
    background-origin: initial;
    background-clip: initial;
    background-color: rgb(255, 255, 255);
    background-repeat: no-repeat;
    background-position: top;
    background-size: 100% auto;
    position: relative;
}
.container {
    width: 100%;
    padding-right: 15px;
    padding-left: 15px;
    margin-right: auto;
    margin-left: auto;
}
.row {
    display: -ms-flexbox;
    display: flex;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
    margin-right: -15px;
    margin-left: -15px;
}
</style>